**Problem**: For a work project I'm setting up an OAuth2 client in Spring Boot. We're using a NetIQ Access Manager for authorization. During the OAuth2 flow it redirect the user to our backend with a code param. However the request is formatted like so "`http://localhost:8045/backend/api/v1/login/oauth2/code/your-login??code=/CODE"` with 2 question marks. Spring Boots OAuth client implementation does not like this.

**Solution**: The long term solution should obviously be to fix the Access Manager. As a quick workaround I rewrite the request like so:

```java
public class FixQuestionableOAuthCodeRequestFilter implements Filter {

    @Override
    public void doFilter(ServletRequest request, ServletResponse response, FilterChain chain)
      throws IOException, ServletException {
        HttpServletRequest req = (HttpServletRequest) request;
        HttpServletResponse res = (HttpServletResponse) response;

        if (req.getParameterMap().containsKey("?code")) {
            Map<String, String[]> editableMap = new HashMap<>(request.getParameterMap());
            String[] code = editableMap.get("?code");
            editableMap.put("code",code);
            System.out.println("Fixed questionable OAuth Code Request..");

            req = new HttpServletRequestWrapper((HttpServletRequest) request) {
                @Override
                public Map<String, String[]> getParameterMap() {
                    return editableMap;
                }
            };
        }

        chain.doFilter (req, res);
    }
}
```

This filter can then be configured in the Spring Boot Security Chain to run before the code is handled:

<pre class="language-java"><code class="lang-java"><strong>http.oauth2Login(Customizer.withDefaults())
</strong>  .addFilterBefore(new FixQuestionableOAuthCodeRequestFilter(), OAuth2LoginAuthenticationFilter.class)
</code></pre>
