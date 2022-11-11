# Spring Boot OAuth2 Client

Configuring a Spring Boot backend as a OAuth2 Client. The idea being that a frontend application (e.g. Angular UI) does not handle any of the oauth stuff. It simply has a active session with the backend via a session cookie (JSESSIONID).

## Basic flow

1. The user open the frontend unauthenticated.
   1. FE calls some backend endpoints
   2. BE endpoints return 401 unauthenticated
2. Frontend handles 401 response and redirects user to specific authorization endpoint in backend.
   1. Backend redirects user to login server
   2. Users logs in
   3. Login redirects user to call BE endpoint with CODE
   4. BE gets token & priviledges from login server
3. User is now authenticated and has session with backend

## Configuration

### application.yaml

```yaml
  security:
    oauth2:
      client:
        registration:
          your-login:
            provider: your-login
            client-id: some-id-string
            client-secret: some-client-secret
            scope: profile, email, phone, address
        provider:
          your-login:
            issuer-uri: https://server.your-.ch/nidp/oauth/nam
```

Trigger auth for testing: [http://localhost:8045/backend/api/v1/oauth2/authorization/your-login](http://localhost:8045/backend/api/v1/oauth2/authorization/your-login)



### Spring Security

#### Minimal

A minimal starting configuration looks like this:

```java
@Configuration
@EnableGlobalMethodSecurity(securedEnabled = true)
public class SecurityConfig {
   
    @Bean(name = "your-login")
    public SecurityFilterChain oidcSecurityConfiguration(HttpSecurity http) throws Exception {
        http.antMatcher("/**");

        http.oauth2Login(Customizer.withDefaults())
          .exceptionHandling()
          .authenticationEntryPoint(new HttpStatusEntryPoint(HttpStatus.UNAUTHORIZED));

        http.authorizeRequests(c -> c.anyRequest().authenticated());

        return http.build();
    }
}
```

