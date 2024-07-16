# Getting started

## Project Setup

Use IntelliJ "Create new project" with Spring Initializer, Gradle, JDK11 and Cloud Function dependency to setup new project. Beware that your chosen cloud platform may no support functions for the latest version of java. E.g. AWS only support Java 8 and Java 11 at the time of writing (8.11.2021).

## Create a function

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

## Test a function

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

## Platform specific dependencies

Spring Cloud Functions are cloud agnostic. They can be deployed on any major cloud platform without changing their business logic. However to deploy them on a specific cloud platform we need to add an adapter dependency as well as dependencies of the cloud provider for their "function" implementation. In the case of AWS this feature is called "AWS Lambda".

```groovy
    // Spring AWS adapter dependencies
    implementation 'org.springframework.cloud:spring-cloud-function-adapter-aws'

    // AWS dependencies
    implementation 'com.amazonaws:aws-lambda-java-events:3.10.0'
    implementation 'com.amazonaws:aws-lambda-java-core:1.2.1'
```

## Create deployment package

To upload an artefact with our function to AWS we need to setup packaging of the compiled code. For maven it's recommended to use the maven shade plugin (see Note 1). For gradle we're adding a buildZip task. This task creates a zip in the build/distributions folder.

```groovy
task buildZip(type: Zip) {
    from compileJava
    from processResources
    into('lib') {
        from configurations.runtimeClasspath
    }
}
```

## Setup AWS Lambda in Console

1. Create Function
   1. Enter function name "reverseString"
   2. Choose Java runtime
   3. Create
2. Code Source -> Upload from -> choose .zip file in distributions folder

In order to set the correct handler for the function we need to go to Runtime Settings -> Edit. There we can replace the example handler "example.Hello::handleRequest" with our own. "com.sixtymeters.springcloudfunction.SpringCloudFunctionApplication::reverseString"

# Notes

* [Github Repo with demo code from this wiki entry](https://github.com/aerobless/zuhlke-camp-aws/tree/main/spring-cloud-function)
* [Tutorial: Create Spring Cloud Function & Deploy it to AWS](https://www.baeldung.com/spring-cloud-function) (1)
* [Spring Cloud function examples](https://codetinkering.com/spring-cloud-function-aws-lambda/)
* [AWS: Deploy Java Lambda functions](https://docs.aws.amazon.com/en\_us/lambda/latest/dg/java-package.html#java-package-maven) (1)
* [Documentation](https://spring.io/projects/spring-cloud-function#overview)
