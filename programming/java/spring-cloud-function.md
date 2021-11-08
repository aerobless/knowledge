# Spring Cloud Function

## Getting started

#### Project Setup

Use IntelliJ "Create new project" with Spring Initializer, Gradle, JDK17 and Cloud Function dependency to setup new project.

#### Create a function

```java
@SpringBootApplication
public class SpringCloudFunctionApplication {

    public static void main(String[] args) {
        SpringApplication.run(SpringCloudFunctionApplication.class, args);
    }

    @Bean
    public Function<String, String> reverseString() {
        return value -> new StringBuilder(value).reverse().toString();
    }
}
```

#### Test a function

```java
@SpringBootTest
class SpringCloudFunctionApplicationTests {

    private final SpringCloudFunctionApplication app = new SpringCloudFunctionApplication();

    @Test
    void text_reverseString_textIsReversed() {
        String output = app.reverseString().apply("hello world");
        assertThat(output).isEqualTo("dlrow olleh");
    }
}
```

#### Deploy to AWS

Spring Cloud Functions are cloud agnostic. They can be deployed on any major cloud platform without changing their business logic. However to deploy them on a specific cloud platform we need to add an adapter dependency as well as dependencies of the cloud provider for their "function" implementation. In the case of AWS this feature is called "AWS Lambda".

```groovy
    // Spring AWS adapter dependencies
    implementation 'org.springframework.cloud:spring-cloud-function-adapter-aws'

    // AWS dependencies
    implementation 'com.amazonaws:aws-lambda-java-events:3.10.0'
    implementation 'com.amazonaws:aws-lambda-java-core:1.2.1'
```





## Notes

* [Github Repo with demo code from this wiki entry](https://github.com/aerobless/zuhlke-camp-aws/tree/main/spring-cloud-function)
* [Tutorial: Create Spring Cloud Function & Deploy it to AWS](https://www.baeldung.com/spring-cloud-function)
* [Documentation](https://spring.io/projects/spring-cloud-function#overview)
