# boot-native

- For https://github.com/baomidou/dynamic-datasource/issues/597.

- Use `sdkman!` in Ubuntu 22.04.3 LTS.
```shell
sdk install maven
sdk install java 21.0.1-graalce
sdk use java 21.0.1-graalce

mvn -PgenerateMetadata -DskipNativeTests -T1C clean test native:metadata-copy
mvn -PnativeTest -T1C clean test
```

- Log.

```shell
$ mvn -PnativeTest -T1C clean test
[INFO] Scanning for projects...
[INFO] 
[INFO] Using the MultiThreadedBuilder implementation with a thread count of 6
[INFO] 
[INFO] ----------------------< com.example:boot-native >-----------------------
[INFO] Building boot-native 0.0.1-SNAPSHOT
[INFO]   from pom.xml
[INFO] --------------------------------[ jar ]---------------------------------
[INFO] 
[INFO] --- clean:3.2.0:clean (default-clean) @ boot-native ---
[INFO] Deleting /home/linghengqian/TwinklingLiftWorks/git/public/boot-native/target
[INFO] 
[INFO] --- resources:3.3.1:resources (default-resources) @ boot-native ---
[INFO] Copying 1 resource from src/main/resources to target/classes
[INFO] Copying 9 resources from src/main/resources to target/classes
[INFO] 
[INFO] --- compiler:3.11.0:compile (default-compile) @ boot-native ---
[INFO] Changes detected - recompiling the module! :source
[INFO] Compiling 8 source files with javac [debug release 17] to target/classes
[INFO] 
[INFO] --- resources:3.3.1:testResources (default-testResources) @ boot-native ---
[INFO] skip non existing resourceDirectory /home/linghengqian/TwinklingLiftWorks/git/public/boot-native/src/test/resources
[INFO] 
[INFO] --- compiler:3.11.0:testCompile (default-testCompile) @ boot-native ---
[INFO] Changes detected - recompiling the module! :dependency
[INFO] Compiling 1 source file with javac [debug release 17] to target/test-classes
[INFO] 
[INFO] --- spring-boot:3.1.4:process-test-aot (process-test-aot) @ boot-native ---
19:38:07.998 [main] INFO org.springframework.test.context.aot.TestClassScanner -- Scanning for Spring test classes in all packages in classpath roots [/home/linghengqian/TwinklingLiftWorks/git/public/boot-native/target/test-classes]
19:38:08.345 [main] INFO org.springframework.test.context.support.AnnotationConfigContextLoaderUtils -- Could not detect default configuration classes for test class [com.example.bootnative.BootNativeApplicationTests]: BootNativeApplicationTests does not declare any static, non-private, non-final, nested classes annotated with @Configuration.
19:38:08.441 [main] INFO org.springframework.boot.test.context.SpringBootTestContextBootstrapper -- Found @SpringBootConfiguration com.example.bootnative.BootNativeApplication for test class com.example.bootnative.BootNativeApplicationTests

  .   ____          _            __ _ _
 /\\ / ___'_ __ _ _(_)_ __  __ _ \ \ \ \
( ( )\___ | '_ | '_| | '_ \/ _` | \ \ \ \
 \\/  ___)| |_)| | | | | || (_| |  ) ) ) )
  '  |____| .__|_| |_|_| |_\__, | / / / /
 =========|_|==============|___/=/_/_/_/
 :: Spring Boot ::                (v3.1.4)

2023-11-28T19:38:08.841+08:00  INFO 9419 --- [           main] c.e.b.BootNativeApplicationTests         : Starting BootNativeApplicationTests using Java 21.0.1 with PID 9419 (/home/linghengqian/TwinklingLiftWorks/git/public/boot-native/target/test-classes started by linghengqian in /home/linghengqian/TwinklingLiftWorks/git/public/boot-native)
2023-11-28T19:38:08.843+08:00  INFO 9419 --- [           main] c.e.b.BootNativeApplicationTests         : No active profile set, falling back to 1 default profile: "default"
[INFO] 
[INFO] --- surefire:3.0.0:test (default-test) @ boot-native ---
[WARNING]  Parameter 'systemProperties' is deprecated: Use systemPropertyVariables instead.
[INFO] Using auto detected provider org.apache.maven.surefire.junitplatform.JUnitPlatformProvider
[INFO] 
[INFO] -------------------------------------------------------
[INFO]  T E S T S
[INFO] -------------------------------------------------------
[INFO] Running com.example.bootnative.BootNativeApplicationTests
19:38:12.779 [main] INFO org.springframework.test.context.support.AnnotationConfigContextLoaderUtils -- Could not detect default configuration classes for test class [com.example.bootnative.BootNativeApplicationTests]: BootNativeApplicationTests does not declare any static, non-private, non-final, nested classes annotated with @Configuration.
19:38:12.885 [main] INFO org.springframework.boot.test.context.SpringBootTestContextBootstrapper -- Found @SpringBootConfiguration com.example.bootnative.BootNativeApplication for test class com.example.bootnative.BootNativeApplicationTests

  .   ____          _            __ _ _
 /\\ / ___'_ __ _ _(_)_ __  __ _ \ \ \ \
( ( )\___ | '_ | '_| | '_ \/ _` | \ \ \ \
 \\/  ___)| |_)| | | | | || (_| |  ) ) ) )
  '  |____| .__|_| |_|_| |_\__, | / / / /
 =========|_|==============|___/=/_/_/_/
 :: Spring Boot ::                (v3.1.4)

2023-11-28T19:38:13.275+08:00  INFO 9455 --- [           main] c.e.b.BootNativeApplicationTests         : Starting BootNativeApplicationTests using Java 21.0.1 with PID 9455 (started by linghengqian in /home/linghengqian/TwinklingLiftWorks/git/public/boot-native)
2023-11-28T19:38:13.278+08:00  INFO 9455 --- [           main] c.e.b.BootNativeApplicationTests         : No active profile set, falling back to 1 default profile: "default"
2023-11-28T19:38:14.209+08:00  INFO 9455 --- [           main] trationDelegate$BeanPostProcessorChecker : Bean 'spring.datasource.dynamic-com.baomidou.dynamic.datasource.spring.boot.autoconfigure.DynamicDataSourceProperties' of type [com.baomidou.dynamic.datasource.spring.boot.autoconfigure.DynamicDataSourceProperties] is not eligible for getting processed by all BeanPostProcessors (for example: not eligible for auto-proxying)
2023-11-28T19:38:14.211+08:00  INFO 9455 --- [           main] trationDelegate$BeanPostProcessorChecker : Bean 'com.baomidou.dynamic.datasource.spring.boot.autoconfigure.DynamicDataSourceAopConfiguration' of type [com.baomidou.dynamic.datasource.spring.boot.autoconfigure.DynamicDataSourceAopConfiguration$$SpringCGLIB$$0] is not eligible for getting processed by all BeanPostProcessors (for example: not eligible for auto-proxying)
2023-11-28T19:38:14.218+08:00  INFO 9455 --- [           main] trationDelegate$BeanPostProcessorChecker : Bean 'dsProcessor' of type [com.baomidou.dynamic.datasource.processor.DsJakartaHeaderProcessor] is not eligible for getting processed by all BeanPostProcessors (for example: not eligible for auto-proxying)
2023-11-28T19:38:14.290+08:00  INFO 9455 --- [           main] c.b.d.d.DynamicRoutingDataSource         : dynamic-datasource - add a datasource named [master] success
2023-11-28T19:38:14.291+08:00  INFO 9455 --- [           main] c.b.d.d.DynamicRoutingDataSource         : dynamic-datasource initial loaded [1] datasource,primary datasource named [master]
2023-11-28T19:38:14.308+08:00  INFO 9455 --- [           main] com.zaxxer.hikari.HikariDataSource       : master - Starting...
2023-11-28T19:38:14.458+08:00  INFO 9455 --- [           main] com.zaxxer.hikari.pool.HikariPool        : master - Added connection conn0: url=jdbc:h2:mem:test user=SA
2023-11-28T19:38:14.459+08:00  INFO 9455 --- [           main] com.zaxxer.hikari.HikariDataSource       : master - Start completed.
 _ _   |_  _ _|_. ___ _ |    _ 
| | |\/|_)(_| | |_\  |_)||_|_\ 
     /               |         
                        3.5.4.1 
2023-11-28T19:38:15.233+08:00  INFO 9455 --- [           main] c.e.b.BootNativeApplicationTests         : Started BootNativeApplicationTests in 2.215 seconds (process running for 3.123)
Message[id=1, message=Hello World on run!]
Message[id=2, message=Hello World! on runWithXmlMapper]
------------演示insert-----------------
2023-11-28T19:38:15.309+08:00  INFO 9455 --- [           main] c.e.bootnative.MyMetaObjectHandler       : 进入insertFill填充了
------------演示select-----------------
simple query:Messages{id=3, message='Hello MybatisPlus', messageType=VOICE}
query wrapper:Messages{id=1, message='Hello World on run!', messageType=null}
------------演示update-----------------
2023-11-28T19:38:15.355+08:00  INFO 9455 --- [           main] c.e.bootnative.MyMetaObjectHandler       : 进入updateFill填充了
2023-11-28T19:38:15.364+08:00  INFO 9455 --- [           main] c.e.bootnative.MyMetaObjectHandler       : 进入updateFill填充了
------------演示delete-----------------
------------演示page-----------------
total:2,records[Messages{id=1, message='Hello MybatisPlus', messageType=TEXT}, Messages{id=2, message='Hello World! on runWithXmlMapper', messageType=null}]
------------演示lambda-----------------
lambda query:null
2023-11-28T19:38:15.430+08:00  INFO 9455 --- [           main] c.e.bootnative.MyMetaObjectHandler       : 进入updateFill填充了
lambda update:1
lambda delete:1
OpenJDK 64-Bit Server VM warning: Sharing is only supported for boot loader classes because bootstrap classpath has been appended
WARNING: A Java agent has been loaded dynamically (/home/linghengqian/.m2/repository/net/bytebuddy/byte-buddy-agent/1.14.8/byte-buddy-agent-1.14.8.jar)
WARNING: If a serviceability tool is in use, please run with -XX:+EnableDynamicAgentLoading to hide this warning
WARNING: If a serviceability tool is not in use, please run with -Djdk.instrument.traceUsage for more information
WARNING: Dynamic loading of agents will be disallowed by default in a future release
test
[INFO] Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 3.588 s - in com.example.bootnative.BootNativeApplicationTests
[INFO] 
[INFO] Results:
[INFO] 
[INFO] Tests run: 1, Failures: 0, Errors: 0, Skipped: 0
[INFO] 
[INFO] 
[INFO] --- native:0.9.27:test (test-native) @ boot-native ---
[INFO] ====================
[INFO] Initializing project: boot-native
[INFO] ====================
[INFO] Found GraalVM installation from JAVA_HOME variable.
[INFO] Downloaded GraalVM reachability metadata repository from file:/home/linghengqian/.m2/repository/org/graalvm/buildtools/graalvm-reachability-metadata/0.9.27/graalvm-reachability-metadata-0.9.27-repository.zip
[INFO] [graalvm reachability metadata repository for com.h2database:h2:2.1.214]: Configuration directory not found. Trying latest version.
[INFO] [graalvm reachability metadata repository for com.h2database:h2:2.1.214]: Configuration directory is com.h2database/h2/2.1.210
[INFO] [graalvm reachability metadata repository for com.zaxxer:HikariCP:5.0.1]: Configuration directory is com.zaxxer/HikariCP/5.0.1
[INFO] [graalvm reachability metadata repository for io.undertow:undertow-core:2.3.8.Final]: Configuration directory not found. Trying latest version.
[INFO] [graalvm reachability metadata repository for io.undertow:undertow-core:2.3.8.Final]: Configuration directory is io.undertow/undertow-core/2.2.19.Final
[INFO] [graalvm reachability metadata repository for org.jboss.logging:jboss-logging:3.5.3.Final]: Configuration directory not found. Trying latest version.
[INFO] [graalvm reachability metadata repository for org.jboss.logging:jboss-logging:3.5.3.Final]: Configuration directory is org.jboss.logging/jboss-logging/3.5.0.Final
[INFO] [graalvm reachability metadata repository for jakarta.servlet:jakarta.servlet-api:6.0.0]: Configuration directory not found. Trying latest version.
[INFO] [graalvm reachability metadata repository for jakarta.servlet:jakarta.servlet-api:6.0.0]: Configuration directory is jakarta.servlet/jakarta.servlet-api/5.0.0
[WARNING] Properties file at 'jar:file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar!/META-INF/native-image/org.graalvm.polyglot/native-image.properties' does not match the recommended 'META-INF/native-image/org.graalvm.sdk/graal-sdk/native-image.properties' layout.
[WARNING] Properties file at 'jar:file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar!/META-INF/native-image/org.graalvm.home/native-image.properties' does not match the recommended 'META-INF/native-image/org.graalvm.sdk/graal-sdk/native-image.properties' layout.
[INFO] [graalvm reachability metadata repository for ch.qos.logback:logback-classic:1.4.11]: Configuration directory not found. Trying latest version.
[INFO] [graalvm reachability metadata repository for ch.qos.logback:logback-classic:1.4.11]: Configuration directory is ch.qos.logback/logback-classic/1.4.1
[INFO] [graalvm reachability metadata repository for com.fasterxml.jackson.core:jackson-databind:2.15.2]: Configuration directory is com.fasterxml.jackson.core/jackson-databind/2.15.2
[INFO] [graalvm reachability metadata repository for org.apache.tomcat.embed:tomcat-embed-core:10.1.13]: Configuration directory not found. Trying latest version.
[INFO] [graalvm reachability metadata repository for org.apache.tomcat.embed:tomcat-embed-core:10.1.13]: Configuration directory is org.apache.tomcat.embed/tomcat-embed-core/10.0.20
[INFO] [graalvm reachability metadata repository for org.mockito:mockito-core:5.3.1]: Configuration directory not found. Trying latest version.
[INFO] [graalvm reachability metadata repository for org.mockito:mockito-core:5.3.1]: Configuration directory is org.mockito/mockito-core/4.8.1
[INFO] Executing: /home/linghengqian/.sdkman/candidates/java/21.0.1-graalce/bin/native-image -cp /home/linghengqian/TwinklingLiftWorks/git/public/boot-native/target/classes:/home/linghengqian/TwinklingLiftWorks/git/public/boot-native/target/test-classes:/home/linghengqian/.m2/repository/com/h2database/h2/2.1.214/h2-2.1.214.jar:/home/linghengqian/.m2/repository/com/zaxxer/HikariCP/5.0.1/HikariCP-5.0.1.jar:/home/linghengqian/.m2/repository/org/slf4j/slf4j-api/2.0.9/slf4j-api-2.0.9.jar:/home/linghengqian/.m2/repository/com/baomidou/dynamic-datasource-spring-boot3-starter/4.2.0/dynamic-datasource-spring-boot3-starter-4.2.0.jar:/home/linghengqian/.m2/repository/com/baomidou/dynamic-datasource-spring-boot-common/4.2.0/dynamic-datasource-spring-boot-common-4.2.0.jar:/home/linghengqian/.m2/repository/com/baomidou/dynamic-datasource-spring/4.2.0/dynamic-datasource-spring-4.2.0.jar:/home/linghengqian/.m2/repository/com/baomidou/dynamic-datasource-creator/4.2.0/dynamic-datasource-creator-4.2.0.jar:/home/linghengqian/.m2/repository/org/springframework/boot/spring-boot-starter-aop/3.1.4/spring-boot-starter-aop-3.1.4.jar:/home/linghengqian/.m2/repository/org/aspectj/aspectjweaver/1.9.20/aspectjweaver-1.9.20.jar:/home/linghengqian/.m2/repository/org/springframework/boot/spring-boot-starter-undertow/3.1.4/spring-boot-starter-undertow-3.1.4.jar:/home/linghengqian/.m2/repository/io/undertow/undertow-core/2.3.8.Final/undertow-core-2.3.8.Final.jar:/home/linghengqian/.m2/repository/org/jboss/logging/jboss-logging/3.5.3.Final/jboss-logging-3.5.3.Final.jar:/home/linghengqian/.m2/repository/org/jboss/xnio/xnio-api/3.8.8.Final/xnio-api-3.8.8.Final.jar:/home/linghengqian/.m2/repository/org/wildfly/common/wildfly-common/1.5.4.Final/wildfly-common-1.5.4.Final.jar:/home/linghengqian/.m2/repository/org/wildfly/client/wildfly-client-config/1.0.1.Final/wildfly-client-config-1.0.1.Final.jar:/home/linghengqian/.m2/repository/org/jboss/xnio/xnio-nio/3.8.8.Final/xnio-nio-3.8.8.Final.jar:/home/linghengqian/.m2/repository/org/jboss/threads/jboss-threads/3.5.0.Final/jboss-threads-3.5.0.Final.jar:/home/linghengqian/.m2/repository/io/undertow/undertow-servlet/2.3.8.Final/undertow-servlet-2.3.8.Final.jar:/home/linghengqian/.m2/repository/jakarta/servlet/jakarta.servlet-api/6.0.0/jakarta.servlet-api-6.0.0.jar:/home/linghengqian/.m2/repository/io/undertow/undertow-websockets-jsr/2.3.8.Final/undertow-websockets-jsr-2.3.8.Final.jar:/home/linghengqian/.m2/repository/jakarta/websocket/jakarta.websocket-api/2.1.1/jakarta.websocket-api-2.1.1.jar:/home/linghengqian/.m2/repository/jakarta/websocket/jakarta.websocket-client-api/2.1.1/jakarta.websocket-client-api-2.1.1.jar:/home/linghengqian/.m2/repository/org/apache/tomcat/embed/tomcat-embed-el/10.1.13/tomcat-embed-el-10.1.13.jar:/home/linghengqian/.m2/repository/com/baomidou/mybatis-plus-spring-boot3-starter/3.5.4.1/mybatis-plus-spring-boot3-starter-3.5.4.1.jar:/home/linghengqian/.m2/repository/com/baomidou/mybatis-plus/3.5.4.1/mybatis-plus-3.5.4.1.jar:/home/linghengqian/.m2/repository/com/baomidou/mybatis-plus-core/3.5.4.1/mybatis-plus-core-3.5.4.1.jar:/home/linghengqian/.m2/repository/com/baomidou/mybatis-plus-annotation/3.5.4.1/mybatis-plus-annotation-3.5.4.1.jar:/home/linghengqian/.m2/repository/com/baomidou/mybatis-plus-extension/3.5.4.1/mybatis-plus-extension-3.5.4.1.jar:/home/linghengqian/.m2/repository/org/mybatis/mybatis/3.5.13/mybatis-3.5.13.jar:/home/linghengqian/.m2/repository/com/github/jsqlparser/jsqlparser/4.6/jsqlparser-4.6.jar:/home/linghengqian/.m2/repository/org/mybatis/mybatis-spring/3.0.2/mybatis-spring-3.0.2.jar:/home/linghengqian/.m2/repository/com/baomidou/mybatis-plus-spring-boot-autoconfigure/3.5.4.1/mybatis-plus-spring-boot-autoconfigure-3.5.4.1.jar:/home/linghengqian/.m2/repository/org/springframework/boot/spring-boot-autoconfigure/3.1.4/spring-boot-autoconfigure-3.1.4.jar:/home/linghengqian/.m2/repository/org/springframework/boot/spring-boot/3.1.4/spring-boot-3.1.4.jar:/home/linghengqian/.m2/repository/org/springframework/boot/spring-boot-starter-jdbc/3.1.4/spring-boot-starter-jdbc-3.1.4.jar:/home/linghengqian/.m2/repository/org/springframework/spring-jdbc/6.0.12/spring-jdbc-6.0.12.jar:/home/linghengqian/.m2/repository/org/springframework/spring-tx/6.0.12/spring-tx-6.0.12.jar:/home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar:/home/linghengqian/.m2/repository/org/springframework/boot/spring-boot-starter-web/3.1.4/spring-boot-starter-web-3.1.4.jar:/home/linghengqian/.m2/repository/org/springframework/boot/spring-boot-starter/3.1.4/spring-boot-starter-3.1.4.jar:/home/linghengqian/.m2/repository/org/springframework/boot/spring-boot-starter-logging/3.1.4/spring-boot-starter-logging-3.1.4.jar:/home/linghengqian/.m2/repository/ch/qos/logback/logback-classic/1.4.11/logback-classic-1.4.11.jar:/home/linghengqian/.m2/repository/ch/qos/logback/logback-core/1.4.11/logback-core-1.4.11.jar:/home/linghengqian/.m2/repository/org/apache/logging/log4j/log4j-to-slf4j/2.20.0/log4j-to-slf4j-2.20.0.jar:/home/linghengqian/.m2/repository/org/apache/logging/log4j/log4j-api/2.20.0/log4j-api-2.20.0.jar:/home/linghengqian/.m2/repository/org/slf4j/jul-to-slf4j/2.0.9/jul-to-slf4j-2.0.9.jar:/home/linghengqian/.m2/repository/jakarta/annotation/jakarta.annotation-api/2.1.1/jakarta.annotation-api-2.1.1.jar:/home/linghengqian/.m2/repository/org/yaml/snakeyaml/1.33/snakeyaml-1.33.jar:/home/linghengqian/.m2/repository/org/springframework/boot/spring-boot-starter-json/3.1.4/spring-boot-starter-json-3.1.4.jar:/home/linghengqian/.m2/repository/com/fasterxml/jackson/core/jackson-databind/2.15.2/jackson-databind-2.15.2.jar:/home/linghengqian/.m2/repository/com/fasterxml/jackson/core/jackson-annotations/2.15.2/jackson-annotations-2.15.2.jar:/home/linghengqian/.m2/repository/com/fasterxml/jackson/core/jackson-core/2.15.2/jackson-core-2.15.2.jar:/home/linghengqian/.m2/repository/com/fasterxml/jackson/datatype/jackson-datatype-jdk8/2.15.2/jackson-datatype-jdk8-2.15.2.jar:/home/linghengqian/.m2/repository/com/fasterxml/jackson/datatype/jackson-datatype-jsr310/2.15.2/jackson-datatype-jsr310-2.15.2.jar:/home/linghengqian/.m2/repository/com/fasterxml/jackson/module/jackson-module-parameter-names/2.15.2/jackson-module-parameter-names-2.15.2.jar:/home/linghengqian/.m2/repository/org/springframework/boot/spring-boot-starter-tomcat/3.1.4/spring-boot-starter-tomcat-3.1.4.jar:/home/linghengqian/.m2/repository/org/apache/tomcat/embed/tomcat-embed-core/10.1.13/tomcat-embed-core-10.1.13.jar:/home/linghengqian/.m2/repository/org/apache/tomcat/embed/tomcat-embed-websocket/10.1.13/tomcat-embed-websocket-10.1.13.jar:/home/linghengqian/.m2/repository/org/springframework/spring-web/6.0.12/spring-web-6.0.12.jar:/home/linghengqian/.m2/repository/org/springframework/spring-beans/6.0.12/spring-beans-6.0.12.jar:/home/linghengqian/.m2/repository/io/micrometer/micrometer-observation/1.11.4/micrometer-observation-1.11.4.jar:/home/linghengqian/.m2/repository/io/micrometer/micrometer-commons/1.11.4/micrometer-commons-1.11.4.jar:/home/linghengqian/.m2/repository/org/springframework/spring-webmvc/6.0.12/spring-webmvc-6.0.12.jar:/home/linghengqian/.m2/repository/org/springframework/spring-aop/6.0.12/spring-aop-6.0.12.jar:/home/linghengqian/.m2/repository/org/springframework/spring-context/6.0.12/spring-context-6.0.12.jar:/home/linghengqian/.m2/repository/org/springframework/spring-expression/6.0.12/spring-expression-6.0.12.jar:/home/linghengqian/.m2/repository/org/springframework/boot/spring-boot-starter-test/3.1.4/spring-boot-starter-test-3.1.4.jar:/home/linghengqian/.m2/repository/org/springframework/boot/spring-boot-test/3.1.4/spring-boot-test-3.1.4.jar:/home/linghengqian/.m2/repository/org/springframework/boot/spring-boot-test-autoconfigure/3.1.4/spring-boot-test-autoconfigure-3.1.4.jar:/home/linghengqian/.m2/repository/com/jayway/jsonpath/json-path/2.8.0/json-path-2.8.0.jar:/home/linghengqian/.m2/repository/jakarta/xml/bind/jakarta.xml.bind-api/4.0.1/jakarta.xml.bind-api-4.0.1.jar:/home/linghengqian/.m2/repository/jakarta/activation/jakarta.activation-api/2.1.2/jakarta.activation-api-2.1.2.jar:/home/linghengqian/.m2/repository/net/minidev/json-smart/2.4.11/json-smart-2.4.11.jar:/home/linghengqian/.m2/repository/net/minidev/accessors-smart/2.4.11/accessors-smart-2.4.11.jar:/home/linghengqian/.m2/repository/org/ow2/asm/asm/9.3/asm-9.3.jar:/home/linghengqian/.m2/repository/org/assertj/assertj-core/3.24.2/assertj-core-3.24.2.jar:/home/linghengqian/.m2/repository/net/bytebuddy/byte-buddy/1.14.8/byte-buddy-1.14.8.jar:/home/linghengqian/.m2/repository/org/hamcrest/hamcrest/2.2/hamcrest-2.2.jar:/home/linghengqian/.m2/repository/org/junit/jupiter/junit-jupiter/5.9.3/junit-jupiter-5.9.3.jar:/home/linghengqian/.m2/repository/org/junit/jupiter/junit-jupiter-api/5.9.3/junit-jupiter-api-5.9.3.jar:/home/linghengqian/.m2/repository/org/junit/jupiter/junit-jupiter-params/5.9.3/junit-jupiter-params-5.9.3.jar:/home/linghengqian/.m2/repository/org/junit/jupiter/junit-jupiter-engine/5.9.3/junit-jupiter-engine-5.9.3.jar:/home/linghengqian/.m2/repository/org/mockito/mockito-core/5.3.1/mockito-core-5.3.1.jar:/home/linghengqian/.m2/repository/net/bytebuddy/byte-buddy-agent/1.14.8/byte-buddy-agent-1.14.8.jar:/home/linghengqian/.m2/repository/org/objenesis/objenesis/3.3/objenesis-3.3.jar:/home/linghengqian/.m2/repository/org/mockito/mockito-junit-jupiter/5.3.1/mockito-junit-jupiter-5.3.1.jar:/home/linghengqian/.m2/repository/org/skyscreamer/jsonassert/1.5.1/jsonassert-1.5.1.jar:/home/linghengqian/.m2/repository/com/vaadin/external/google/android-json/0.0.20131108.vaadin1/android-json-0.0.20131108.vaadin1.jar:/home/linghengqian/.m2/repository/org/springframework/spring-core/6.0.12/spring-core-6.0.12.jar:/home/linghengqian/.m2/repository/org/springframework/spring-jcl/6.0.12/spring-jcl-6.0.12.jar:/home/linghengqian/.m2/repository/org/springframework/spring-test/6.0.12/spring-test-6.0.12.jar:/home/linghengqian/.m2/repository/org/xmlunit/xmlunit-core/2.9.1/xmlunit-core-2.9.1.jar:/home/linghengqian/.m2/repository/org/junit/platform/junit-platform-launcher/1.9.3/junit-platform-launcher-1.9.3.jar:/home/linghengqian/.m2/repository/org/junit/platform/junit-platform-engine/1.9.3/junit-platform-engine-1.9.3.jar:/home/linghengqian/.m2/repository/org/opentest4j/opentest4j/1.2.0/opentest4j-1.2.0.jar:/home/linghengqian/.m2/repository/org/junit/platform/junit-platform-commons/1.9.3/junit-platform-commons-1.9.3.jar:/home/linghengqian/.m2/repository/org/apiguardian/apiguardian-api/1.1.2/apiguardian-api-1.1.2.jar:/home/linghengqian/.m2/repository/org/graalvm/buildtools/native-maven-plugin/0.9.27/native-maven-plugin-0.9.27.jar:/home/linghengqian/.m2/repository/org/graalvm/buildtools/junit-platform-native/0.9.27/junit-platform-native-0.9.27.jar:/home/linghengqian/.m2/repository/org/junit/platform/junit-platform-console/1.9.3/junit-platform-console-1.9.3.jar:/home/linghengqian/.m2/repository/org/junit/platform/junit-platform-reporting/1.9.3/junit-platform-reporting-1.9.3.jar:/home/linghengqian/.m2/repository/org/junit/platform/junit-platform-launcher/1.9.3/junit-platform-launcher-1.9.3.jar:/home/linghengqian/.m2/repository/org/junit/platform/junit-platform-engine/1.9.3/junit-platform-engine-1.9.3.jar:/home/linghengqian/.m2/repository/org/junit/platform/junit-platform-commons/1.9.3/junit-platform-commons-1.9.3.jar:/home/linghengqian/.m2/repository/org/junit/jupiter/junit-jupiter/5.10.0/junit-jupiter-5.10.0.jar:/home/linghengqian/.m2/repository/org/junit/jupiter/junit-jupiter-api/5.10.0/junit-jupiter-api-5.10.0.jar:/home/linghengqian/.m2/repository/org/junit/jupiter/junit-jupiter-params/5.10.0/junit-jupiter-params-5.10.0.jar:/home/linghengqian/.m2/repository/org/junit/jupiter/junit-jupiter-engine/5.10.0/junit-jupiter-engine-5.10.0.jar:/home/linghengqian/.m2/repository/org/graalvm/buildtools/utils/0.9.27/utils-0.9.27.jar:/home/linghengqian/.m2/repository/org/graalvm/buildtools/graalvm-reachability-metadata/0.9.27/graalvm-reachability-metadata-0.9.27.jar:/home/linghengqian/.m2/repository/org/graalvm/buildtools/junit-platform-native/0.9.27/junit-platform-native-0.9.27.jar --no-fallback -o /home/linghengqian/TwinklingLiftWorks/git/public/boot-native/target/native-tests -Djunit.platform.listeners.uid.tracking.output.dir=/home/linghengqian/TwinklingLiftWorks/git/public/boot-native/target/test-ids -H:ConfigurationFileDirectories=/home/linghengqian/TwinklingLiftWorks/git/public/boot-native/target/graalvm-reachability-metadata/15733192e0f6e369451cde2afd11b12ca027fde5/com.fasterxml.jackson.core/jackson-databind/2.15.2,/home/linghengqian/TwinklingLiftWorks/git/public/boot-native/target/graalvm-reachability-metadata/15733192e0f6e369451cde2afd11b12ca027fde5/com.zaxxer/HikariCP/5.0.1,/home/linghengqian/TwinklingLiftWorks/git/public/boot-native/target/graalvm-reachability-metadata/15733192e0f6e369451cde2afd11b12ca027fde5/org.jboss.logging/jboss-logging/3.5.0.Final,/home/linghengqian/TwinklingLiftWorks/git/public/boot-native/target/graalvm-reachability-metadata/15733192e0f6e369451cde2afd11b12ca027fde5/com.h2database/h2/2.1.210,/home/linghengqian/TwinklingLiftWorks/git/public/boot-native/target/graalvm-reachability-metadata/15733192e0f6e369451cde2afd11b12ca027fde5/ch.qos.logback/logback-classic/1.4.1,/home/linghengqian/TwinklingLiftWorks/git/public/boot-native/target/graalvm-reachability-metadata/15733192e0f6e369451cde2afd11b12ca027fde5/io.undertow/undertow-core/2.2.19.Final,/home/linghengqian/TwinklingLiftWorks/git/public/boot-native/target/graalvm-reachability-metadata/15733192e0f6e369451cde2afd11b12ca027fde5/jakarta.servlet/jakarta.servlet-api/5.0.0,/home/linghengqian/TwinklingLiftWorks/git/public/boot-native/target/graalvm-reachability-metadata/15733192e0f6e369451cde2afd11b12ca027fde5/org.mockito/mockito-core/4.8.1,/home/linghengqian/TwinklingLiftWorks/git/public/boot-native/target/graalvm-reachability-metadata/15733192e0f6e369451cde2afd11b12ca027fde5/org.apache.tomcat.embed/tomcat-embed-core/10.0.20 -H:+AllowDeprecatedBuilderClassesOnImageClasspath --features=org.graalvm.junit.platform.JUnitPlatformFeature org.graalvm.junit.platform.NativeImageJUnitLauncher
Warning: The option '-H:ReflectionConfigurationResources=META-INF/native-image/org.apache.tomcat.embed/tomcat-embed-websocket/tomcat-reflection.json' is experimental and must be enabled via '-H:+UnlockExperimentalVMOptions' in the future.
Warning: The option '-H:ReflectionConfigurationResources=META-INF/native-image/org.apache.tomcat.embed/tomcat-embed-el/tomcat-reflection.json' is experimental and must be enabled via '-H:+UnlockExperimentalVMOptions' in the future.
Warning: The option '-H:Features=org.graalvm.home.HomeFinderFeature' is experimental and must be enabled via '-H:+UnlockExperimentalVMOptions' in the future.
Warning: The option '-H:+AllowDeprecatedBuilderClassesOnImageClasspath' is experimental and must be enabled via '-H:+UnlockExperimentalVMOptions' in the future.
Warning: The option '-H:ResourceConfigurationResources=META-INF/native-image/org.apache.tomcat.embed/tomcat-embed-core/tomcat-resource.json' is experimental and must be enabled via '-H:+UnlockExperimentalVMOptions' in the future.
Warning: The option '-H:ReflectionConfigurationResources=META-INF/native-image/org.apache.tomcat.embed/tomcat-embed-core/tomcat-reflection.json' is experimental and must be enabled via '-H:+UnlockExperimentalVMOptions' in the future.
Warning: The option '-H:ResourceConfigurationResources=META-INF/native-image/org.apache.tomcat.embed/tomcat-embed-el/tomcat-resource.json' is experimental and must be enabled via '-H:+UnlockExperimentalVMOptions' in the future.
Warning: The option '-H:ResourceConfigurationResources=META-INF/native-image/org.apache.tomcat.embed/tomcat-embed-websocket/tomcat-resource.json' is experimental and must be enabled via '-H:+UnlockExperimentalVMOptions' in the future.
Warning: Please re-evaluate whether any experimental option is required, and either remove or unlock it. The build output lists all active experimental options, including where they come from and possible alternatives. If you think an experimental option should be considered as stable, please file an issue.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class com.oracle.svm.core.annotate.TargetElement. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class com.oracle.svm.core.annotate.TargetClass. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class com.oracle.svm.core.annotate.TargetClass$NoClassNameProvider. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class com.oracle.svm.core.annotate.TargetClass$AlwaysIncluded. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class com.oracle.svm.core.annotate.Substitute. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class com.oracle.svm.core.annotate.RecomputeFieldValue. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class com.oracle.svm.core.annotate.RecomputeFieldValue$Kind. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class com.oracle.svm.core.annotate.KeepOriginal. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class com.oracle.svm.core.annotate.InjectAccessors. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class com.oracle.svm.core.annotate.Inject. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class com.oracle.svm.core.annotate.Delete. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class com.oracle.svm.core.annotate.AutomaticFeature. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class com.oracle.svm.core.annotate.AnnotateOriginal. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class com.oracle.svm.core.annotate.Alias. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.hosted.RuntimeSerialization. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.hosted.RuntimeResourceAccess. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.hosted.RuntimeReflection. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.hosted.RuntimeProxyCreation. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.hosted.RuntimeJNIAccess. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.hosted.RuntimeClassInitialization. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.hosted.FieldValueTransformer. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.hosted.Feature. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.hosted.Feature$AfterImageWriteAccess. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.hosted.Feature$BeforeImageWriteAccess. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.hosted.Feature$AfterHeapLayoutAccess. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.hosted.Feature$AfterCompilationAccess. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.hosted.Feature$BeforeCompilationAccess. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.hosted.Feature$CompilationAccess. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.hosted.Feature$BeforeUniverseBuildingAccess. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.hosted.Feature$OnAnalysisExitAccess. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.hosted.Feature$QueryReachabilityAccess. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.hosted.Feature$AfterAnalysisAccess. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.hosted.Feature$DuringAnalysisAccess. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.hosted.Feature$BeforeAnalysisAccess. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.hosted.Feature$DuringSetupAccess. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.hosted.Feature$AfterRegistrationAccess. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.hosted.Feature$IsInConfigurationAccess. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.hosted.Feature$FeatureAccess. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.impl.clinit.ClassInitializationTracking. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.impl.VMRuntimeSupport. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.impl.UnmanagedMemorySupport. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.impl.ThreadingSupport. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.impl.SizeOfSupport. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.impl.RuntimeSerializationSupport. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.impl.RuntimeResourceSupport. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.impl.RuntimeReflectionSupport. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.impl.RuntimeProxyCreationSupport. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.impl.RuntimeOptionsSupport. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.impl.RuntimeJNIAccessSupport. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.impl.ReflectionRegistry. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.impl.RuntimeClassInitializationSupport. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.impl.ProcessPropertiesSupport. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.impl.PinnedObjectSupport. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.impl.ObjectHandlesSupport. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.impl.IsolateSupport. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.impl.ImageSingletonsSupport. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.impl.HeapDumpSupport. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.impl.ConfigurationCondition. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.impl.CTypeConversionSupport. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.impl.CEntryPointLiteralCodePointer. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.impl.CConstantValueSupport. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.impl.InternalPlatform. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.impl.InternalPlatform$PLATFORM_JNI. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.c.constant.CEnumValue. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.c.constant.CEnumLookup. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.c.constant.CEnumConstant. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.c.constant.CEnum. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.c.constant.CConstant. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.c.constant.CConstant$ValueAccess. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.c.function.InvokeCFunctionPointer. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.c.function.CMacroInfo. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.c.function.CLibrary. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.c.function.CFunction. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.c.function.CFunction$Transition. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.c.function.CEntryPoint. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.c.function.CEntryPoint$ExceptionHandler. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.c.function.CEntryPoint$IsolateContext. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.c.function.CEntryPoint$IsolateThreadContext. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.c.function.CEntryPoint$Builtin. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.c.function.CEntryPoint$Publish. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.c.function.CEntryPoint$NotIncludedAutomatically. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.c.function.CEntryPoint$AlwaysIncluded. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.c.function.CEntryPoint$FatalExceptionHandler. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.c.function.RelocatedPointer. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.c.function.CodePointer. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.c.function.CFunctionPointer. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.c.function.CEntryPointLiteral. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.c.type.WordPointer. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.c.type.VoidPointer. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.c.type.CTypeConversion. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.c.type.CTypeConversion$CCharPointerPointerHolder. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.c.type.CTypeConversion$CCharPointerHolder. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.c.type.CShortPointer. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.c.type.CLongPointer. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.c.type.CIntPointerPointer. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.c.type.CIntPointer. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.c.type.CFloatPointer. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.c.type.CDoublePointer. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.c.type.CCharPointerPointer. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.c.type.CCharPointer. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.c.struct.UniqueLocationIdentity. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.c.struct.SizeOf. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.c.struct.RawStructure. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.c.struct.RawPointerTo. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.c.struct.RawFieldOffset. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.c.struct.RawFieldAddress. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.c.struct.RawField. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.c.struct.CTypedefOfInfo. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.c.struct.CFieldOffset. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.c.struct.CFieldAddress. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.c.struct.CField. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.c.struct.CBitfield. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.c.struct.AllowWideningCast. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.c.struct.AllowNarrowingCast. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.c.struct.CPointerTo. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.c.struct.CStruct. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.c.CContext. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.c.CContext$Directives. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.VMRuntime. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.UnmanagedMemory. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.Threading. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.Threading$RecurringCallbackAccess. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.Threading$RecurringCallback. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.StackValue. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.RuntimeOptions. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.ProcessProperties. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.Platforms. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.Platform. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.Platform$HOSTED_ONLY. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.Platform$WINDOWS_AARCH64. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.Platform$WINDOWS_AMD64. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.Platform$MACOS_AARCH64. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.Platform$MACOS_AMD64. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.Platform$IOS_AARCH64. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.Platform$IOS_AMD64. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.Platform$ANDROID_AARCH64. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.Platform$LINUX_AARCH64. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.Platform$LINUX_AMD64. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.Platform$DARWIN_AARCH64. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.Platform$DARWIN_AMD64. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.Platform$LINUX_AARCH64_BASE. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.Platform$LINUX_AMD64_BASE. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.Platform$WINDOWS. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.Platform$MACOS. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.Platform$IOS. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.Platform$DARWIN. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.Platform$ANDROID. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.Platform$LINUX. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.Platform$AARCH64. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.Platform$AMD64. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.PinnedObject. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.ObjectHandles. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.ObjectHandle. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.LogHandler. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.Isolates. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.Isolates$ProtectionDomain. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.Isolates$ProtectionDomain$2. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.Isolates$ProtectionDomain$1. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.Isolates$CreateIsolateParameters. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.Isolates$CreateIsolateParameters$Builder. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.ImageSingletons. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.Isolates$IsolateException. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.ImageInfo. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.IsolateThread. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.Isolate. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.CurrentIsolate. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
Warning: Class-path entry file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar contains class org.graalvm.nativeimage.AnnotationAccess. This class is part of the image builder itself (in jrt:/org.graalvm.nativeimage) and must not be passed via -cp.
========================================================================================================================
GraalVM Native Image: Generating 'native-tests' (executable)...
========================================================================================================================
[1/8] Initializing...                                                                                   (10.1s @ 0.25GB)
 Java version: 21.0.1+12, vendor version: GraalVM CE 21.0.1+12.1
 Graal compiler: optimization level: 2, target machine: x86-64-v3
 C compiler: gcc (linux, x86_64, 11.4.0)
 Garbage collector: Serial GC (max heap size: 80% of RAM)
 4 user-specific feature(s):
 - com.oracle.svm.thirdparty.gson.GsonFeature
 - org.graalvm.home.HomeFinderFeature: Finds GraalVM paths and its version number
 - org.graalvm.junit.platform.JUnitPlatformFeature
 - org.springframework.aot.nativex.feature.PreComputeFieldFeature
------------------------------------------------------------------------------------------------------------------------
 4 experimental option(s) unlocked:
 - '-H:+AllowDeprecatedBuilderClassesOnImageClasspath' (origin(s): command line)
 - '-H:ResourceConfigurationResources' (origin(s): 'META-INF/native-image/org.apache.tomcat.embed/tomcat-embed-el/native-image.properties' in 'file:///home/linghengqian/.m2/repository/org/apache/tomcat/embed/tomcat-embed-el/10.1.13/tomcat-embed-el-10.1.13.jar', 'META-INF/native-image/org.apache.tomcat.embed/tomcat-embed-core/native-image.properties' in 'file:///home/linghengqian/.m2/repository/org/apache/tomcat/embed/tomcat-embed-core/10.1.13/tomcat-embed-core-10.1.13.jar', 'META-INF/native-image/org.apache.tomcat.embed/tomcat-embed-websocket/native-image.properties' in 'file:///home/linghengqian/.m2/repository/org/apache/tomcat/embed/tomcat-embed-websocket/10.1.13/tomcat-embed-websocket-10.1.13.jar')
 - '-H:ReflectionConfigurationResources' (origin(s): 'META-INF/native-image/org.apache.tomcat.embed/tomcat-embed-el/native-image.properties' in 'file:///home/linghengqian/.m2/repository/org/apache/tomcat/embed/tomcat-embed-el/10.1.13/tomcat-embed-el-10.1.13.jar', 'META-INF/native-image/org.apache.tomcat.embed/tomcat-embed-core/native-image.properties' in 'file:///home/linghengqian/.m2/repository/org/apache/tomcat/embed/tomcat-embed-core/10.1.13/tomcat-embed-core-10.1.13.jar', 'META-INF/native-image/org.apache.tomcat.embed/tomcat-embed-websocket/native-image.properties' in 'file:///home/linghengqian/.m2/repository/org/apache/tomcat/embed/tomcat-embed-websocket/10.1.13/tomcat-embed-websocket-10.1.13.jar')
 - '-H:Features' (alternative API option(s): --features=org.graalvm.home.HomeFinderFeature, --features=org.springframework.aot.nativex.feature.PreComputeFieldFeature, --features=org.graalvm.junit.platform.JUnitPlatformFeature, --features=com.oracle.svm.thirdparty.gson.GsonFeature, --features=com.oracle.svm.polyglot.groovy.GroovyIndyInterfaceFeature, --features=com.oracle.svm.polyglot.scala.ScalaFeature; origin(s): 'META-INF/native-image/org.graalvm.home/native-image.properties' in 'file:///home/linghengqian/.m2/repository/org/graalvm/sdk/graal-sdk/22.3.1/graal-sdk-22.3.1.jar')
------------------------------------------------------------------------------------------------------------------------
Build resources:
 - 9.57GB of memory (75.6% of 12.67GB system memory, determined at start)
 - 6 thread(s) (100.0% of 6 available processor(s), determined at start)
[junit-platform-native] Running in 'test listener' mode using files matching pattern [junit-platform-unique-ids*] found in folder [/home/linghengqian/TwinklingLiftWorks/git/public/boot-native/target/test-ids] and its subfolders.
Field org.apache.commons.logging.LogAdapter#log4jSpiPresent set to true at build time
Field org.apache.commons.logging.LogAdapter#log4jSlf4jProviderPresent set to true at build time
Field org.apache.commons.logging.LogAdapter#slf4jSpiPresent set to true at build time
Field org.apache.commons.logging.LogAdapter#slf4jApiPresent set to true at build time
Field org.springframework.cglib.core.AbstractClassGenerator#inNativeImage set to true at build time
Field org.springframework.http.converter.json.Jackson2ObjectMapperBuilder#jackson2XmlPresent set to false at build time
Field org.springframework.boot.logging.java.JavaLoggingSystem$Factory#PRESENT set to true at build time
Field org.springframework.boot.test.mock.mockito.ResetMocksTestExecutionListener#MOCKITO_IS_PRESENT set to true at build time
Field org.springframework.aot.AotDetector#inNativeImage set to true at build time
Field org.springframework.core.NativeDetector#inNativeImage set to true at build time
Field org.springframework.boot.logging.log4j2.Log4J2LoggingSystem$Factory#PRESENT set to false at build time
Field org.springframework.boot.logging.logback.LogbackLoggingSystem$Factory#PRESENT set to true at build time
Field org.springframework.boot.test.autoconfigure.restdocs.RestDocsTestExecutionListener#REST_DOCS_PRESENT set to false at build time
Field org.springframework.transaction.interceptor.TransactionAspectSupport#vavrPresent set to false at build time
Field org.springframework.transaction.interceptor.TransactionAspectSupport#reactiveStreamsPresent set to false at build time
Field org.springframework.web.client.RestTemplate#romePresent set to false at build time
Field org.springframework.web.client.RestTemplate#jaxb2Present set to true at build time
Field org.springframework.web.client.RestTemplate#jackson2Present set to true at build time
Field org.springframework.web.client.RestTemplate#jackson2XmlPresent set to false at build time
Field org.springframework.web.client.RestTemplate#jackson2SmilePresent set to false at build time
Field org.springframework.web.client.RestTemplate#jackson2CborPresent set to false at build time
Field org.springframework.web.client.RestTemplate#gsonPresent set to false at build time
Field org.springframework.web.client.RestTemplate#jsonbPresent set to false at build time
Field org.springframework.web.client.RestTemplate#kotlinSerializationCborPresent set to false at build time
Field org.springframework.web.client.RestTemplate#kotlinSerializationJsonPresent set to false at build time
Field org.springframework.web.client.RestTemplate#kotlinSerializationProtobufPresent set to false at build time
Field org.springframework.core.KotlinDetector#kotlinPresent set to false at build time
Field org.springframework.core.KotlinDetector#kotlinReflectPresent set to false at build time
Field org.springframework.transaction.annotation.AnnotationTransactionAttributeSource#jta12Present set to false at build time
Field org.springframework.transaction.annotation.AnnotationTransactionAttributeSource#ejb3Present set to false at build time
Field org.springframework.boot.test.web.reactive.server.WebTestClientContextCustomizerFactory#webClientPresent set to false at build time
Field org.springframework.web.context.request.RequestContextHolder#jsfPresent set to false at build time
Field org.springframework.web.servlet.config.annotation.WebMvcConfigurationSupport#romePresent set to false at build time
Field org.springframework.web.servlet.config.annotation.WebMvcConfigurationSupport#jaxb2Present set to true at build time
Field org.springframework.web.servlet.config.annotation.WebMvcConfigurationSupport#jackson2Present set to true at build time
Field org.springframework.web.servlet.config.annotation.WebMvcConfigurationSupport#jackson2XmlPresent set to false at build time
Field org.springframework.web.servlet.config.annotation.WebMvcConfigurationSupport#jackson2SmilePresent set to false at build time
Field org.springframework.web.servlet.config.annotation.WebMvcConfigurationSupport#jackson2CborPresent set to false at build time
Field org.springframework.web.servlet.config.annotation.WebMvcConfigurationSupport#gsonPresent set to false at build time
Field org.springframework.web.servlet.config.annotation.WebMvcConfigurationSupport#jsonbPresent set to false at build time
Field org.springframework.web.servlet.config.annotation.WebMvcConfigurationSupport#kotlinSerializationCborPresent set to false at build time
Field org.springframework.web.servlet.config.annotation.WebMvcConfigurationSupport#kotlinSerializationJsonPresent set to false at build time
Field org.springframework.web.servlet.config.annotation.WebMvcConfigurationSupport#kotlinSerializationProtobufPresent set to false at build time
Field org.springframework.boot.test.autoconfigure.webservices.client.MockWebServiceServerTestExecutionListener#MOCK_SERVER_PRESENT set to false at build time
Field org.springframework.web.servlet.view.InternalResourceViewResolver#jstlPresent set to false at build time
Field org.springframework.format.support.DefaultFormattingConversionService#jsr354Present set to false at build time
Field org.springframework.boot.autoconfigure.web.format.WebConversionService#JSR_354_PRESENT set to false at build time
Field org.springframework.test.context.web.socket.MockServerContainerContextCustomizerFactory#webSocketPresent set to true at build time
Field org.springframework.web.context.support.StandardServletEnvironment#jndiPresent set to true at build time
Field org.springframework.web.context.support.WebApplicationContextUtils#jsfPresent set to false at build time
Field org.springframework.jdbc.support.SQLErrorCodeSQLExceptionTranslator#userProvidedErrorCodesFilePresent set to false at build time
Field org.springframework.boot.logging.logback.LogbackLoggingSystemProperties#JBOSS_LOGGING_PRESENT set to true at build time
Field org.springframework.http.converter.support.AllEncompassingFormHttpMessageConverter#jaxb2Present set to true at build time
Field org.springframework.http.converter.support.AllEncompassingFormHttpMessageConverter#jackson2Present set to true at build time
Field org.springframework.http.converter.support.AllEncompassingFormHttpMessageConverter#jackson2XmlPresent set to false at build time
Field org.springframework.http.converter.support.AllEncompassingFormHttpMessageConverter#jackson2SmilePresent set to false at build time
Field org.springframework.http.converter.support.AllEncompassingFormHttpMessageConverter#gsonPresent set to false at build time
Field org.springframework.http.converter.support.AllEncompassingFormHttpMessageConverter#jsonbPresent set to false at build time
Field org.springframework.http.converter.support.AllEncompassingFormHttpMessageConverter#kotlinSerializationCborPresent set to false at build time
Field org.springframework.http.converter.support.AllEncompassingFormHttpMessageConverter#kotlinSerializationJsonPresent set to false at build time
Field org.springframework.http.converter.support.AllEncompassingFormHttpMessageConverter#kotlinSerializationProtobufPresent set to false at build time
Field org.springframework.context.event.ApplicationListenerMethodAdapter#reactiveStreamsPresent set to false at build time
Field org.springframework.core.ReactiveAdapterRegistry#reactorPresent set to false at build time
Field org.springframework.core.ReactiveAdapterRegistry#rxjava3Present set to false at build time
Field org.springframework.core.ReactiveAdapterRegistry#kotlinCoroutinesPresent set to false at build time
Field org.springframework.core.ReactiveAdapterRegistry#mutinyPresent set to false at build time
SLF4J: No SLF4J providers were found.
SLF4J: Defaulting to no-operation (NOP) logger implementation
SLF4J: See https://www.slf4j.org/codes.html#noProviders for further details.
Field org.springframework.web.servlet.mvc.method.annotation.ReactiveTypeHandler#isContextPropagationPresent set to false at build time
Field org.springframework.web.servlet.support.RequestContext#jstlPresent set to false at build time
[2/8] Performing analysis...  [******]                                                                  (77.8s @ 1.88GB)
   23,931 reachable types   (90.7% of   26,391 total)
   38,269 reachable fields  (65.0% of   58,876 total)
  120,860 reachable methods (63.8% of  189,378 total)
    7,298 types,   853 fields, and 10,010 methods registered for reflection
       67 types,    65 fields, and    57 methods registered for JNI access
        4 native libraries: dl, pthread, rt, z
[3/8] Building universe...                                                                               (8.6s @ 2.84GB)
[4/8] Parsing methods...      [***]                                                                      (6.3s @ 3.93GB)
[5/8] Inlining methods...     [***]                                                                      (4.0s @ 3.58GB)
[6/8] Compiling methods...    [*******]                                                                 (54.6s @ 3.49GB)
[7/8] Layouting methods...    [***]                                                                      (8.9s @ 2.71GB)
[8/8] Creating image...       [***]                                                                      (8.8s @ 3.69GB)
  59.60MB (50.54%) for code area:    79,844 compilation units
  54.01MB (45.80%) for image heap:  534,295 objects and 350 resources
   4.32MB ( 3.66%) for other data
 117.93MB in total
------------------------------------------------------------------------------------------------------------------------
Top 10 origins of code area:                                Top 10 object types in image heap:
  15.54MB java.base                                           18.30MB byte[] for code metadata
   6.08MB h2-2.1.214.jar                                       7.75MB byte[] for java.lang.String
   4.33MB java.xml                                             5.77MB java.lang.Class
   4.27MB tomcat-embed-core-10.1.13.jar                        5.21MB java.lang.String
   2.04MB jackson-databind-2.15.2.jar                          2.06MB byte[] for embedded resources
   1.72MB svm.jar (Native Image)                               2.01MB com.oracle.svm.core.hub.DynamicHubCompanion
   1.69MB spring-core-6.0.12.jar                               1.60MB byte[] for reflection metadata
   1.62MB jsqlparser-4.6.jar                                   1.06MB java.lang.String[]
   1.54MB mybatis-3.5.13.jar                                 909.87kB byte[] for general heap data
   1.47MB aspectjweaver-1.9.20.jar                           859.26kB c.o.svm.core.hub.DynamicHub$ReflectionMetadata
  18.74MB for 131 more packages                                8.52MB for 4684 more object types
------------------------------------------------------------------------------------------------------------------------
Recommendations:
 INIT: Adopt '--strict-image-heap' to prepare for the next GraalVM release.
 HEAP: Set max heap for improved and more predictable memory usage.
 CPU:  Enable more CPU features with '-march=native' for improved performance.
------------------------------------------------------------------------------------------------------------------------
                       19.1s (10.5% of total time) in 115 GCs | Peak RSS: 6.31GB | CPU load: 4.92
------------------------------------------------------------------------------------------------------------------------
Produced artifacts:
 /home/linghengqian/TwinklingLiftWorks/git/public/boot-native/target/native-tests (executable)
========================================================================================================================
Finished generating 'native-tests' in 3m 0s.
[INFO] Executing: /home/linghengqian/TwinklingLiftWorks/git/public/boot-native/target/native-tests --xml-output-dir /home/linghengqian/TwinklingLiftWorks/git/public/boot-native/target/native-test-reports -Djunit.platform.listeners.uid.tracking.output.dir=/home/linghengqian/TwinklingLiftWorks/git/public/boot-native/target/test-ids
JUnit Platform on Native Image - report
----------------------------------------


  .   ____          _            __ _ _
 /\\ / ___'_ __ _ _(_)_ __  __ _ \ \ \ \
( ( )\___ | '_ | '_| | '_ \/ _` | \ \ \ \
 \\/  ___)| |_)| | | | | || (_| |  ) ) ) )
  '  |____| .__|_| |_|_| |_\__, | / / / /
 =========|_|==============|___/=/_/_/_/
 :: Spring Boot ::                (v3.1.4)

2023-11-28T19:41:19.072+08:00  INFO 9703 --- [           main] c.e.b.BootNativeApplicationTests         : Starting AOT-processed BootNativeApplicationTests using Java 21.0.1 with PID 9703 (started by linghengqian in /home/linghengqian/TwinklingLiftWorks/git/public/boot-native)
2023-11-28T19:41:19.072+08:00  INFO 9703 --- [           main] c.e.b.BootNativeApplicationTests         : No active profile set, falling back to 1 default profile: "default"
2023-11-28T19:41:19.081+08:00  INFO 9703 --- [           main] trationDelegate$BeanPostProcessorChecker : Bean 'spring.datasource.dynamic-com.baomidou.dynamic.datasource.spring.boot.autoconfigure.DynamicDataSourceProperties' of type [com.baomidou.dynamic.datasource.spring.boot.autoconfigure.DynamicDataSourceProperties] is not eligible for getting processed by all BeanPostProcessors (for example: not eligible for auto-proxying)
2023-11-28T19:41:19.081+08:00  INFO 9703 --- [           main] trationDelegate$BeanPostProcessorChecker : Bean 'com.baomidou.dynamic.datasource.spring.boot.autoconfigure.DynamicDataSourceAopConfiguration' of type [com.baomidou.dynamic.datasource.spring.boot.autoconfigure.DynamicDataSourceAopConfiguration$$SpringCGLIB$$0] is not eligible for getting processed by all BeanPostProcessors (for example: not eligible for auto-proxying)
2023-11-28T19:41:19.082+08:00  INFO 9703 --- [           main] trationDelegate$BeanPostProcessorChecker : Bean 'dsProcessor' of type [com.baomidou.dynamic.datasource.processor.DsJakartaHeaderProcessor] is not eligible for getting processed by all BeanPostProcessors (for example: not eligible for auto-proxying)
2023-11-28T19:41:19.088+08:00  INFO 9703 --- [           main] c.b.d.d.DynamicRoutingDataSource         : dynamic-datasource - add a datasource named [master] success
2023-11-28T19:41:19.088+08:00  INFO 9703 --- [           main] c.b.d.d.DynamicRoutingDataSource         : dynamic-datasource initial loaded [1] datasource,primary datasource named [master]
2023-11-28T19:41:19.095+08:00  INFO 9703 --- [           main] com.zaxxer.hikari.HikariDataSource       : master - Starting...
2023-11-28T19:41:19.099+08:00  INFO 9703 --- [           main] com.zaxxer.hikari.pool.HikariPool        : master - Added connection conn0: url=jdbc:h2:mem:test user=SA
2023-11-28T19:41:19.099+08:00  INFO 9703 --- [           main] com.zaxxer.hikari.HikariDataSource       : master - Start completed.
 _ _   |_  _ _|_. ___ _ |    _ 
| | |\/|_)(_| | |_\  |_)||_|_\ 
     /               |         
                        3.5.4.1 
2023-11-28T19:41:19.207+08:00  INFO 9703 --- [           main] c.e.b.BootNativeApplicationTests         : Started BootNativeApplicationTests in 0.147 seconds (process running for 0.157)
Message[id=1, message=Hello World on run!]
Message[id=2, message=Hello World! on runWithXmlMapper]
------------演示insert-----------------
2023-11-28T19:41:19.208+08:00  INFO 9703 --- [           main] c.e.bootnative.MyMetaObjectHandler       : 进入insertFill填充了
------------演示select-----------------
simple query:Messages{id=3, message='Hello MybatisPlus', messageType=VOICE}
query wrapper:Messages{id=1, message='Hello World on run!', messageType=null}
------------演示update-----------------
2023-11-28T19:41:19.211+08:00  INFO 9703 --- [           main] c.e.bootnative.MyMetaObjectHandler       : 进入updateFill填充了
2023-11-28T19:41:19.212+08:00  INFO 9703 --- [           main] c.e.bootnative.MyMetaObjectHandler       : 进入updateFill填充了
------------演示delete-----------------
------------演示page-----------------
total:2,records[Messages{id=1, message='Hello MybatisPlus', messageType=TEXT}, Messages{id=2, message='Hello World! on runWithXmlMapper', messageType=null}]
------------演示lambda-----------------
2023-11-28T19:41:19.215+08:00 ERROR 9703 --- [           main] o.s.boot.SpringApplication               : Application run failed

java.lang.IllegalStateException: Failed to execute ApplicationRunner
        at org.springframework.boot.SpringApplication.callRunner(SpringApplication.java:768) ~[native-tests:3.1.4]
        at org.springframework.boot.SpringApplication.callRunners(SpringApplication.java:755) ~[native-tests:3.1.4]
        at org.springframework.boot.SpringApplication.run(SpringApplication.java:322) ~[native-tests:3.1.4]
        at org.springframework.boot.test.context.SpringBootContextLoader.lambda$loadContext$3(SpringBootContextLoader.java:137) ~[native-tests:3.1.4]
        at org.springframework.util.function.ThrowingSupplier.get(ThrowingSupplier.java:58) ~[native-tests:6.0.12]
        at org.springframework.util.function.ThrowingSupplier.get(ThrowingSupplier.java:46) ~[native-tests:6.0.12]
        at org.springframework.boot.SpringApplication.withHook(SpringApplication.java:1409) ~[native-tests:3.1.4]
        at org.springframework.boot.test.context.SpringBootContextLoader$ContextLoaderHook.run(SpringBootContextLoader.java:545) ~[na:na]
        at org.springframework.boot.test.context.SpringBootContextLoader.loadContext(SpringBootContextLoader.java:137) ~[native-tests:3.1.4]
        at org.springframework.boot.test.context.SpringBootContextLoader.loadContextForAotRuntime(SpringBootContextLoader.java:119) ~[native-tests:3.1.4]
        at org.springframework.test.context.cache.DefaultCacheAwareContextLoaderDelegate.loadContextInAotMode(DefaultCacheAwareContextLoaderDelegate.java:217) ~[native-tests:6.0.12]
        at org.springframework.test.context.cache.DefaultCacheAwareContextLoaderDelegate.loadContext(DefaultCacheAwareContextLoaderDelegate.java:116) ~[native-tests:6.0.12]
        at org.springframework.test.context.support.DefaultTestContext.getApplicationContext(DefaultTestContext.java:127) ~[na:na]
        at org.springframework.test.context.web.ServletTestExecutionListener.setUpRequestContextIfNecessary(ServletTestExecutionListener.java:191) ~[native-tests:6.0.12]
        at org.springframework.test.context.web.ServletTestExecutionListener.prepareTestInstance(ServletTestExecutionListener.java:130) ~[native-tests:6.0.12]
        at org.springframework.test.context.TestContextManager.prepareTestInstance(TestContextManager.java:241) ~[native-tests:6.0.12]
        at org.springframework.test.context.junit.jupiter.SpringExtension.postProcessTestInstance(SpringExtension.java:138) ~[native-tests:6.0.12]
        at org.junit.jupiter.engine.descriptor.ClassBasedTestDescriptor.lambda$invokeTestInstancePostProcessors$10(ClassBasedTestDescriptor.java:377) ~[native-tests:5.9.3]
        at org.junit.jupiter.engine.descriptor.ClassBasedTestDescriptor.executeAndMaskThrowable(ClassBasedTestDescriptor.java:382) ~[native-tests:5.9.3]
        at org.junit.jupiter.engine.descriptor.ClassBasedTestDescriptor.lambda$invokeTestInstancePostProcessors$11(ClassBasedTestDescriptor.java:377) ~[native-tests:5.9.3]
        at java.base@21.0.1/java.util.stream.ReferencePipeline$3$1.accept(ReferencePipeline.java:197) ~[na:na]
        at java.base@21.0.1/java.util.stream.ReferencePipeline$2$1.accept(ReferencePipeline.java:179) ~[na:na]
        at java.base@21.0.1/java.util.ArrayList$ArrayListSpliterator.forEachRemaining(ArrayList.java:1708) ~[native-tests:na]
        at java.base@21.0.1/java.util.stream.AbstractPipeline.copyInto(AbstractPipeline.java:509) ~[native-tests:na]
        at java.base@21.0.1/java.util.stream.AbstractPipeline.wrapAndCopyInto(AbstractPipeline.java:499) ~[native-tests:na]
        at java.base@21.0.1/java.util.stream.StreamSpliterators$WrappingSpliterator.forEachRemaining(StreamSpliterators.java:310) ~[na:na]
        at java.base@21.0.1/java.util.stream.Streams$ConcatSpliterator.forEachRemaining(Streams.java:735) ~[native-tests:na]
        at java.base@21.0.1/java.util.stream.Streams$ConcatSpliterator.forEachRemaining(Streams.java:734) ~[native-tests:na]
        at java.base@21.0.1/java.util.stream.ReferencePipeline$Head.forEach(ReferencePipeline.java:762) ~[na:na]
        at org.junit.jupiter.engine.descriptor.ClassBasedTestDescriptor.invokeTestInstancePostProcessors(ClassBasedTestDescriptor.java:376) ~[native-tests:5.9.3]
        at org.junit.jupiter.engine.descriptor.ClassBasedTestDescriptor.lambda$instantiateAndPostProcessTestInstance$6(ClassBasedTestDescriptor.java:289) ~[native-tests:5.9.3]
        at org.junit.platform.engine.support.hierarchical.ThrowableCollector.execute(ThrowableCollector.java:73) ~[native-tests:1.9.3]
        at org.junit.jupiter.engine.descriptor.ClassBasedTestDescriptor.instantiateAndPostProcessTestInstance(ClassBasedTestDescriptor.java:288) ~[native-tests:5.9.3]
        at org.junit.jupiter.engine.descriptor.ClassBasedTestDescriptor.lambda$testInstancesProvider$4(ClassBasedTestDescriptor.java:278) ~[native-tests:5.9.3]
        at java.base@21.0.1/java.util.Optional.orElseGet(Optional.java:364) ~[native-tests:na]
        at org.junit.jupiter.engine.descriptor.ClassBasedTestDescriptor.lambda$testInstancesProvider$5(ClassBasedTestDescriptor.java:277) ~[native-tests:5.9.3]
        at org.junit.jupiter.engine.execution.TestInstancesProvider.getTestInstances(TestInstancesProvider.java:31) ~[native-tests:5.9.3]
        at org.junit.jupiter.engine.descriptor.TestMethodTestDescriptor.lambda$prepare$0(TestMethodTestDescriptor.java:105) ~[native-tests:5.9.3]
        at org.junit.platform.engine.support.hierarchical.ThrowableCollector.execute(ThrowableCollector.java:73) ~[native-tests:1.9.3]
        at org.junit.jupiter.engine.descriptor.TestMethodTestDescriptor.prepare(TestMethodTestDescriptor.java:104) ~[native-tests:5.9.3]
        at org.junit.jupiter.engine.descriptor.TestMethodTestDescriptor.prepare(TestMethodTestDescriptor.java:68) ~[native-tests:5.9.3]
        at org.junit.platform.engine.support.hierarchical.NodeTestTask.lambda$prepare$2(NodeTestTask.java:123) ~[na:na]
        at org.junit.platform.engine.support.hierarchical.ThrowableCollector.execute(ThrowableCollector.java:73) ~[native-tests:1.9.3]
        at org.junit.platform.engine.support.hierarchical.NodeTestTask.prepare(NodeTestTask.java:123) ~[na:na]
        at org.junit.platform.engine.support.hierarchical.NodeTestTask.execute(NodeTestTask.java:90) ~[na:na]
        at java.base@21.0.1/java.util.ArrayList.forEach(ArrayList.java:1596) ~[native-tests:na]
        at org.junit.platform.engine.support.hierarchical.SameThreadHierarchicalTestExecutorService.invokeAll(SameThreadHierarchicalTestExecutorService.java:41) ~[na:na]
        at org.junit.platform.engine.support.hierarchical.NodeTestTask.lambda$executeRecursively$6(NodeTestTask.java:155) ~[na:na]
        at org.junit.platform.engine.support.hierarchical.ThrowableCollector.execute(ThrowableCollector.java:73) ~[native-tests:1.9.3]
        at org.junit.platform.engine.support.hierarchical.NodeTestTask.lambda$executeRecursively$8(NodeTestTask.java:141) ~[na:na]
        at org.junit.platform.engine.support.hierarchical.Node.around(Node.java:137) ~[native-tests:1.9.3]
        at org.junit.platform.engine.support.hierarchical.NodeTestTask.lambda$executeRecursively$9(NodeTestTask.java:139) ~[na:na]
        at org.junit.platform.engine.support.hierarchical.ThrowableCollector.execute(ThrowableCollector.java:73) ~[native-tests:1.9.3]
        at org.junit.platform.engine.support.hierarchical.NodeTestTask.executeRecursively(NodeTestTask.java:138) ~[na:na]
        at org.junit.platform.engine.support.hierarchical.NodeTestTask.execute(NodeTestTask.java:95) ~[na:na]
        at java.base@21.0.1/java.util.ArrayList.forEach(ArrayList.java:1596) ~[native-tests:na]
        at org.junit.platform.engine.support.hierarchical.SameThreadHierarchicalTestExecutorService.invokeAll(SameThreadHierarchicalTestExecutorService.java:41) ~[na:na]
        at org.junit.platform.engine.support.hierarchical.NodeTestTask.lambda$executeRecursively$6(NodeTestTask.java:155) ~[na:na]
        at org.junit.platform.engine.support.hierarchical.ThrowableCollector.execute(ThrowableCollector.java:73) ~[native-tests:1.9.3]
        at org.junit.platform.engine.support.hierarchical.NodeTestTask.lambda$executeRecursively$8(NodeTestTask.java:141) ~[na:na]
        at org.junit.platform.engine.support.hierarchical.Node.around(Node.java:137) ~[native-tests:1.9.3]
        at org.junit.platform.engine.support.hierarchical.NodeTestTask.lambda$executeRecursively$9(NodeTestTask.java:139) ~[na:na]
        at org.junit.platform.engine.support.hierarchical.ThrowableCollector.execute(ThrowableCollector.java:73) ~[native-tests:1.9.3]
        at org.junit.platform.engine.support.hierarchical.NodeTestTask.executeRecursively(NodeTestTask.java:138) ~[na:na]
        at org.junit.platform.engine.support.hierarchical.NodeTestTask.execute(NodeTestTask.java:95) ~[na:na]
        at org.junit.platform.engine.support.hierarchical.SameThreadHierarchicalTestExecutorService.submit(SameThreadHierarchicalTestExecutorService.java:35) ~[na:na]
        at org.junit.platform.engine.support.hierarchical.HierarchicalTestExecutor.execute(HierarchicalTestExecutor.java:57) ~[na:na]
        at org.junit.platform.engine.support.hierarchical.HierarchicalTestEngine.execute(HierarchicalTestEngine.java:54) ~[native-tests:1.9.3]
        at org.junit.platform.launcher.core.EngineExecutionOrchestrator.execute(EngineExecutionOrchestrator.java:147) ~[na:na]
        at org.junit.platform.launcher.core.EngineExecutionOrchestrator.execute(EngineExecutionOrchestrator.java:127) ~[na:na]
        at org.junit.platform.launcher.core.EngineExecutionOrchestrator.execute(EngineExecutionOrchestrator.java:90) ~[na:na]
        at org.junit.platform.launcher.core.EngineExecutionOrchestrator.lambda$execute$0(EngineExecutionOrchestrator.java:55) ~[na:na]
        at org.junit.platform.launcher.core.EngineExecutionOrchestrator.withInterceptedStreams(EngineExecutionOrchestrator.java:102) ~[na:na]
        at org.junit.platform.launcher.core.EngineExecutionOrchestrator.execute(EngineExecutionOrchestrator.java:54) ~[na:na]
        at org.junit.platform.launcher.core.DefaultLauncher.execute(DefaultLauncher.java:114) ~[na:na]
        at org.junit.platform.launcher.core.DefaultLauncher.execute(DefaultLauncher.java:95) ~[na:na]
        at org.junit.platform.launcher.core.DefaultLauncherSession$DelegatingLauncher.execute(DefaultLauncherSession.java:91) ~[na:na]
        at org.junit.platform.launcher.core.SessionPerRequestLauncher.execute(SessionPerRequestLauncher.java:60) ~[na:na]
        at org.graalvm.junit.platform.NativeImageJUnitLauncher.execute(NativeImageJUnitLauncher.java:74) ~[na:na]
        at org.graalvm.junit.platform.NativeImageJUnitLauncher.main(NativeImageJUnitLauncher.java:129) ~[na:na]
        at java.base@21.0.1/java.lang.invoke.LambdaForm$DMH/sa346b79c.invokeStaticInit(LambdaForm$DMH) ~[na:na]
Caused by: com.baomidou.mybatisplus.core.exceptions.MybatisPlusException: java.lang.ClassNotFoundException: com.example.bootnative.BootNativeApplication$$Lambda$0e4dae6cce3633a42432312a352810f4c99affcf
        at com.baomidou.mybatisplus.core.toolkit.support.SerializedLambda.extract(SerializedLambda.java:58) ~[native-tests:3.5.4.1]
        at com.baomidou.mybatisplus.core.toolkit.LambdaUtils.extract(LambdaUtils.java:67) ~[na:na]
        at com.baomidou.mybatisplus.core.conditions.AbstractLambdaWrapper.getColumnCache(AbstractLambdaWrapper.java:128) ~[native-tests:3.5.4.1]
        at com.baomidou.mybatisplus.core.conditions.AbstractLambdaWrapper.columnToString(AbstractLambdaWrapper.java:66) ~[native-tests:3.5.4.1]
        at com.baomidou.mybatisplus.core.conditions.AbstractLambdaWrapper.lambda$columnsToString$0(AbstractLambdaWrapper.java:57) ~[native-tests:3.5.4.1]
        at java.base@21.0.1/java.util.stream.ReferencePipeline$3$1.accept(ReferencePipeline.java:197) ~[na:na]
        at java.base@21.0.1/java.util.Spliterators$ArraySpliterator.forEachRemaining(Spliterators.java:1024) ~[na:na]
        at java.base@21.0.1/java.util.stream.AbstractPipeline.copyInto(AbstractPipeline.java:509) ~[native-tests:na]
        at java.base@21.0.1/java.util.stream.AbstractPipeline.wrapAndCopyInto(AbstractPipeline.java:499) ~[native-tests:na]
        at java.base@21.0.1/java.util.stream.ReduceOps$ReduceOp.evaluateSequential(ReduceOps.java:921) ~[native-tests:na]
        at java.base@21.0.1/java.util.stream.AbstractPipeline.evaluate(AbstractPipeline.java:234) ~[native-tests:na]
        at java.base@21.0.1/java.util.stream.ReferencePipeline.collect(ReferencePipeline.java:682) ~[native-tests:na]
        at com.baomidou.mybatisplus.core.conditions.AbstractLambdaWrapper.columnsToString(AbstractLambdaWrapper.java:57) ~[native-tests:3.5.4.1]
        at com.baomidou.mybatisplus.core.conditions.query.LambdaQueryWrapper.doSelect(LambdaQueryWrapper.java:120) ~[native-tests:3.5.4.1]
        at com.baomidou.mybatisplus.core.conditions.query.LambdaQueryWrapper.select(LambdaQueryWrapper.java:106) ~[native-tests:3.5.4.1]
        at com.example.bootnative.BootNativeApplication.lambda$runWithMybatisPlus$2(BootNativeApplication.java:67) ~[native-tests:na]
        at org.springframework.boot.SpringApplication.callRunner(SpringApplication.java:765) ~[native-tests:3.1.4]
        ... 80 common frames omitted
Caused by: java.lang.ClassNotFoundException: com.example.bootnative.BootNativeApplication$$Lambda$0e4dae6cce3633a42432312a352810f4c99affcf
        at org.graalvm.nativeimage.builder/com.oracle.svm.core.hub.ClassForNameSupport.forName(ClassForNameSupport.java:122) ~[na:na]
        at org.graalvm.nativeimage.builder/com.oracle.svm.core.hub.ClassForNameSupport.forName(ClassForNameSupport.java:86) ~[na:na]
        at java.base@21.0.1/java.lang.Class.forName(DynamicHub.java:1346) ~[native-tests:na]
        at java.base@21.0.1/java.lang.Class.forName(DynamicHub.java:1335) ~[native-tests:na]
        at java.base@21.0.1/java.io.ObjectInputStream.resolveClass(ObjectInputStream.java:804) ~[native-tests:na]
        at com.baomidou.mybatisplus.core.toolkit.support.SerializedLambda$1.resolveClass(SerializedLambda.java:50) ~[na:na]
        at java.base@21.0.1/java.io.ObjectInputStream.readNonProxyDesc(ObjectInputStream.java:2061) ~[native-tests:na]
        at java.base@21.0.1/java.io.ObjectInputStream.readClassDesc(ObjectInputStream.java:1927) ~[native-tests:na]
        at java.base@21.0.1/java.io.ObjectInputStream.readOrdinaryObject(ObjectInputStream.java:2252) ~[native-tests:na]
        at java.base@21.0.1/java.io.ObjectInputStream.readObject0(ObjectInputStream.java:1762) ~[native-tests:na]
        at java.base@21.0.1/java.io.ObjectInputStream.readObject(ObjectInputStream.java:540) ~[native-tests:na]
        at java.base@21.0.1/java.io.ObjectInputStream.readObject(ObjectInputStream.java:498) ~[native-tests:na]
        at com.baomidou.mybatisplus.core.toolkit.support.SerializedLambda.extract(SerializedLambda.java:55) ~[native-tests:3.5.4.1]
        ... 96 common frames omitted

2023-11-28T19:41:19.216+08:00  INFO 9703 --- [           main] c.b.d.d.DynamicRoutingDataSource         : dynamic-datasource start closing ....
2023-11-28T19:41:19.216+08:00  INFO 9703 --- [           main] com.zaxxer.hikari.HikariDataSource       : master - Shutdown initiated...
2023-11-28T19:41:19.220+08:00  INFO 9703 --- [           main] com.zaxxer.hikari.HikariDataSource       : master - Shutdown completed.
2023-11-28T19:41:19.220+08:00  INFO 9703 --- [           main] c.b.d.d.d.DefaultDataSourceDestroyer     : dynamic-datasource close the datasource named [master] success,
2023-11-28T19:41:19.220+08:00  INFO 9703 --- [           main] c.b.d.d.DynamicRoutingDataSource         : dynamic-datasource all closed success,bye



============================
CONDITIONS EVALUATION REPORT
============================


Positive matches:
-----------------

    None


Negative matches:
-----------------

    None


Exclusions:
-----------

    None


Unconditional classes:
----------------------

    None



2023-11-28T19:41:19.221+08:00 ERROR 9703 --- [           main] o.s.test.context.TestContextManager      : Caught exception while allowing TestExecutionListener [org.springframework.test.context.web.ServletTestExecutionListener] to prepare test instance [com.example.bootnative.BootNativeApplicationTests@54b77704]

java.lang.IllegalStateException: Failed to load ApplicationContext for [AotMergedContextConfiguration@26cdac41 testClass = com.example.bootnative.BootNativeApplicationTests, contextInitializerClass = com.example.bootnative.BootNativeApplicationTests__TestContext001_ApplicationContextInitializer, original = [WebMergedContextConfiguration@7f3b6454 testClass = com.example.bootnative.BootNativeApplicationTests, locations = [], classes = [com.example.bootnative.BootNativeApplication], contextInitializerClasses = [], activeProfiles = [], propertySourceLocations = [], propertySourceProperties = ["org.springframework.boot.test.context.SpringBootTestContextBootstrapper=true"], contextCustomizers = [org.springframework.boot.test.context.filter.ExcludeFilterContextCustomizer@187dc579, org.springframework.boot.test.json.DuplicateJsonObjectContextCustomizerFactory$DuplicateJsonObjectContextCustomizer@d36509, org.springframework.boot.test.mock.mockito.MockitoContextCustomizer@0, org.springframework.boot.test.web.client.TestRestTemplateContextCustomizer@4b69fe8e, org.springframework.boot.test.autoconfigure.actuate.observability.ObservabilityContextCustomizerFactory$DisableObservabilityContextCustomizer@1f, org.springframework.boot.test.autoconfigure.properties.PropertyMappingContextCustomizer@0, org.springframework.boot.test.autoconfigure.web.servlet.WebDriverContextCustomizer@1c88b67b, org.springframework.boot.test.context.SpringBootTestAnnotation@f25b5a7f], resourceBasePath = "src/main/webapp", contextLoader = org.springframework.boot.test.context.SpringBootContextLoader, parent = null]]
        at org.springframework.test.context.cache.DefaultCacheAwareContextLoaderDelegate.loadContext(DefaultCacheAwareContextLoaderDelegate.java:143) ~[native-tests:6.0.12]
        at org.springframework.test.context.support.DefaultTestContext.getApplicationContext(DefaultTestContext.java:127) ~[na:na]
        at org.springframework.test.context.web.ServletTestExecutionListener.setUpRequestContextIfNecessary(ServletTestExecutionListener.java:191) ~[native-tests:6.0.12]
        at org.springframework.test.context.web.ServletTestExecutionListener.prepareTestInstance(ServletTestExecutionListener.java:130) ~[native-tests:6.0.12]
        at org.springframework.test.context.TestContextManager.prepareTestInstance(TestContextManager.java:241) ~[native-tests:6.0.12]
        at org.springframework.test.context.junit.jupiter.SpringExtension.postProcessTestInstance(SpringExtension.java:138) ~[native-tests:6.0.12]
        at org.junit.jupiter.engine.descriptor.ClassBasedTestDescriptor.lambda$invokeTestInstancePostProcessors$10(ClassBasedTestDescriptor.java:377) ~[native-tests:5.9.3]
        at org.junit.jupiter.engine.descriptor.ClassBasedTestDescriptor.executeAndMaskThrowable(ClassBasedTestDescriptor.java:382) ~[native-tests:5.9.3]
        at org.junit.jupiter.engine.descriptor.ClassBasedTestDescriptor.lambda$invokeTestInstancePostProcessors$11(ClassBasedTestDescriptor.java:377) ~[native-tests:5.9.3]
        at java.base@21.0.1/java.util.stream.ReferencePipeline$3$1.accept(ReferencePipeline.java:197) ~[na:na]
        at java.base@21.0.1/java.util.stream.ReferencePipeline$2$1.accept(ReferencePipeline.java:179) ~[na:na]
        at java.base@21.0.1/java.util.ArrayList$ArrayListSpliterator.forEachRemaining(ArrayList.java:1708) ~[native-tests:na]
        at java.base@21.0.1/java.util.stream.AbstractPipeline.copyInto(AbstractPipeline.java:509) ~[native-tests:na]
        at java.base@21.0.1/java.util.stream.AbstractPipeline.wrapAndCopyInto(AbstractPipeline.java:499) ~[native-tests:na]
        at java.base@21.0.1/java.util.stream.StreamSpliterators$WrappingSpliterator.forEachRemaining(StreamSpliterators.java:310) ~[na:na]
        at java.base@21.0.1/java.util.stream.Streams$ConcatSpliterator.forEachRemaining(Streams.java:735) ~[native-tests:na]
        at java.base@21.0.1/java.util.stream.Streams$ConcatSpliterator.forEachRemaining(Streams.java:734) ~[native-tests:na]
        at java.base@21.0.1/java.util.stream.ReferencePipeline$Head.forEach(ReferencePipeline.java:762) ~[na:na]
        at org.junit.jupiter.engine.descriptor.ClassBasedTestDescriptor.invokeTestInstancePostProcessors(ClassBasedTestDescriptor.java:376) ~[native-tests:5.9.3]
        at org.junit.jupiter.engine.descriptor.ClassBasedTestDescriptor.lambda$instantiateAndPostProcessTestInstance$6(ClassBasedTestDescriptor.java:289) ~[native-tests:5.9.3]
        at org.junit.platform.engine.support.hierarchical.ThrowableCollector.execute(ThrowableCollector.java:73) ~[native-tests:1.9.3]
        at org.junit.jupiter.engine.descriptor.ClassBasedTestDescriptor.instantiateAndPostProcessTestInstance(ClassBasedTestDescriptor.java:288) ~[native-tests:5.9.3]
        at org.junit.jupiter.engine.descriptor.ClassBasedTestDescriptor.lambda$testInstancesProvider$4(ClassBasedTestDescriptor.java:278) ~[native-tests:5.9.3]
        at java.base@21.0.1/java.util.Optional.orElseGet(Optional.java:364) ~[native-tests:na]
        at org.junit.jupiter.engine.descriptor.ClassBasedTestDescriptor.lambda$testInstancesProvider$5(ClassBasedTestDescriptor.java:277) ~[native-tests:5.9.3]
        at org.junit.jupiter.engine.execution.TestInstancesProvider.getTestInstances(TestInstancesProvider.java:31) ~[native-tests:5.9.3]
        at org.junit.jupiter.engine.descriptor.TestMethodTestDescriptor.lambda$prepare$0(TestMethodTestDescriptor.java:105) ~[native-tests:5.9.3]
        at org.junit.platform.engine.support.hierarchical.ThrowableCollector.execute(ThrowableCollector.java:73) ~[native-tests:1.9.3]
        at org.junit.jupiter.engine.descriptor.TestMethodTestDescriptor.prepare(TestMethodTestDescriptor.java:104) ~[native-tests:5.9.3]
        at org.junit.jupiter.engine.descriptor.TestMethodTestDescriptor.prepare(TestMethodTestDescriptor.java:68) ~[native-tests:5.9.3]
        at org.junit.platform.engine.support.hierarchical.NodeTestTask.lambda$prepare$2(NodeTestTask.java:123) ~[na:na]
        at org.junit.platform.engine.support.hierarchical.ThrowableCollector.execute(ThrowableCollector.java:73) ~[native-tests:1.9.3]
        at org.junit.platform.engine.support.hierarchical.NodeTestTask.prepare(NodeTestTask.java:123) ~[na:na]
        at org.junit.platform.engine.support.hierarchical.NodeTestTask.execute(NodeTestTask.java:90) ~[na:na]
        at java.base@21.0.1/java.util.ArrayList.forEach(ArrayList.java:1596) ~[native-tests:na]
        at org.junit.platform.engine.support.hierarchical.SameThreadHierarchicalTestExecutorService.invokeAll(SameThreadHierarchicalTestExecutorService.java:41) ~[na:na]
        at org.junit.platform.engine.support.hierarchical.NodeTestTask.lambda$executeRecursively$6(NodeTestTask.java:155) ~[na:na]
        at org.junit.platform.engine.support.hierarchical.ThrowableCollector.execute(ThrowableCollector.java:73) ~[native-tests:1.9.3]
        at org.junit.platform.engine.support.hierarchical.NodeTestTask.lambda$executeRecursively$8(NodeTestTask.java:141) ~[na:na]
        at org.junit.platform.engine.support.hierarchical.Node.around(Node.java:137) ~[native-tests:1.9.3]
        at org.junit.platform.engine.support.hierarchical.NodeTestTask.lambda$executeRecursively$9(NodeTestTask.java:139) ~[na:na]
        at org.junit.platform.engine.support.hierarchical.ThrowableCollector.execute(ThrowableCollector.java:73) ~[native-tests:1.9.3]
        at org.junit.platform.engine.support.hierarchical.NodeTestTask.executeRecursively(NodeTestTask.java:138) ~[na:na]
        at org.junit.platform.engine.support.hierarchical.NodeTestTask.execute(NodeTestTask.java:95) ~[na:na]
        at java.base@21.0.1/java.util.ArrayList.forEach(ArrayList.java:1596) ~[native-tests:na]
        at org.junit.platform.engine.support.hierarchical.SameThreadHierarchicalTestExecutorService.invokeAll(SameThreadHierarchicalTestExecutorService.java:41) ~[na:na]
        at org.junit.platform.engine.support.hierarchical.NodeTestTask.lambda$executeRecursively$6(NodeTestTask.java:155) ~[na:na]
        at org.junit.platform.engine.support.hierarchical.ThrowableCollector.execute(ThrowableCollector.java:73) ~[native-tests:1.9.3]
        at org.junit.platform.engine.support.hierarchical.NodeTestTask.lambda$executeRecursively$8(NodeTestTask.java:141) ~[na:na]
        at org.junit.platform.engine.support.hierarchical.Node.around(Node.java:137) ~[native-tests:1.9.3]
        at org.junit.platform.engine.support.hierarchical.NodeTestTask.lambda$executeRecursively$9(NodeTestTask.java:139) ~[na:na]
        at org.junit.platform.engine.support.hierarchical.ThrowableCollector.execute(ThrowableCollector.java:73) ~[native-tests:1.9.3]
        at org.junit.platform.engine.support.hierarchical.NodeTestTask.executeRecursively(NodeTestTask.java:138) ~[na:na]
        at org.junit.platform.engine.support.hierarchical.NodeTestTask.execute(NodeTestTask.java:95) ~[na:na]
        at org.junit.platform.engine.support.hierarchical.SameThreadHierarchicalTestExecutorService.submit(SameThreadHierarchicalTestExecutorService.java:35) ~[na:na]
        at org.junit.platform.engine.support.hierarchical.HierarchicalTestExecutor.execute(HierarchicalTestExecutor.java:57) ~[na:na]
        at org.junit.platform.engine.support.hierarchical.HierarchicalTestEngine.execute(HierarchicalTestEngine.java:54) ~[native-tests:1.9.3]
        at org.junit.platform.launcher.core.EngineExecutionOrchestrator.execute(EngineExecutionOrchestrator.java:147) ~[na:na]
        at org.junit.platform.launcher.core.EngineExecutionOrchestrator.execute(EngineExecutionOrchestrator.java:127) ~[na:na]
        at org.junit.platform.launcher.core.EngineExecutionOrchestrator.execute(EngineExecutionOrchestrator.java:90) ~[na:na]
        at org.junit.platform.launcher.core.EngineExecutionOrchestrator.lambda$execute$0(EngineExecutionOrchestrator.java:55) ~[na:na]
        at org.junit.platform.launcher.core.EngineExecutionOrchestrator.withInterceptedStreams(EngineExecutionOrchestrator.java:102) ~[na:na]
        at org.junit.platform.launcher.core.EngineExecutionOrchestrator.execute(EngineExecutionOrchestrator.java:54) ~[na:na]
        at org.junit.platform.launcher.core.DefaultLauncher.execute(DefaultLauncher.java:114) ~[na:na]
        at org.junit.platform.launcher.core.DefaultLauncher.execute(DefaultLauncher.java:95) ~[na:na]
        at org.junit.platform.launcher.core.DefaultLauncherSession$DelegatingLauncher.execute(DefaultLauncherSession.java:91) ~[na:na]
        at org.junit.platform.launcher.core.SessionPerRequestLauncher.execute(SessionPerRequestLauncher.java:60) ~[na:na]
        at org.graalvm.junit.platform.NativeImageJUnitLauncher.execute(NativeImageJUnitLauncher.java:74) ~[na:na]
        at org.graalvm.junit.platform.NativeImageJUnitLauncher.main(NativeImageJUnitLauncher.java:129) ~[na:na]
        at java.base@21.0.1/java.lang.invoke.LambdaForm$DMH/sa346b79c.invokeStaticInit(LambdaForm$DMH) ~[na:na]
Caused by: java.lang.IllegalStateException: Failed to execute ApplicationRunner
        at org.springframework.boot.SpringApplication.callRunner(SpringApplication.java:768) ~[native-tests:3.1.4]
        at org.springframework.boot.SpringApplication.callRunners(SpringApplication.java:755) ~[native-tests:3.1.4]
        at org.springframework.boot.SpringApplication.run(SpringApplication.java:322) ~[native-tests:3.1.4]
        at org.springframework.boot.test.context.SpringBootContextLoader.lambda$loadContext$3(SpringBootContextLoader.java:137) ~[native-tests:3.1.4]
        at org.springframework.util.function.ThrowingSupplier.get(ThrowingSupplier.java:58) ~[native-tests:6.0.12]
        at org.springframework.util.function.ThrowingSupplier.get(ThrowingSupplier.java:46) ~[native-tests:6.0.12]
        at org.springframework.boot.SpringApplication.withHook(SpringApplication.java:1409) ~[native-tests:3.1.4]
        at org.springframework.boot.test.context.SpringBootContextLoader$ContextLoaderHook.run(SpringBootContextLoader.java:545) ~[na:na]
        at org.springframework.boot.test.context.SpringBootContextLoader.loadContext(SpringBootContextLoader.java:137) ~[native-tests:3.1.4]
        at org.springframework.boot.test.context.SpringBootContextLoader.loadContextForAotRuntime(SpringBootContextLoader.java:119) ~[native-tests:3.1.4]
        at org.springframework.test.context.cache.DefaultCacheAwareContextLoaderDelegate.loadContextInAotMode(DefaultCacheAwareContextLoaderDelegate.java:217) ~[native-tests:6.0.12]
        at org.springframework.test.context.cache.DefaultCacheAwareContextLoaderDelegate.loadContext(DefaultCacheAwareContextLoaderDelegate.java:116) ~[native-tests:6.0.12]
        ... 69 common frames omitted
Caused by: com.baomidou.mybatisplus.core.exceptions.MybatisPlusException: java.lang.ClassNotFoundException: com.example.bootnative.BootNativeApplication$$Lambda$0e4dae6cce3633a42432312a352810f4c99affcf
        at com.baomidou.mybatisplus.core.toolkit.support.SerializedLambda.extract(SerializedLambda.java:58) ~[native-tests:3.5.4.1]
        at com.baomidou.mybatisplus.core.toolkit.LambdaUtils.extract(LambdaUtils.java:67) ~[na:na]
        at com.baomidou.mybatisplus.core.conditions.AbstractLambdaWrapper.getColumnCache(AbstractLambdaWrapper.java:128) ~[native-tests:3.5.4.1]
        at com.baomidou.mybatisplus.core.conditions.AbstractLambdaWrapper.columnToString(AbstractLambdaWrapper.java:66) ~[native-tests:3.5.4.1]
        at com.baomidou.mybatisplus.core.conditions.AbstractLambdaWrapper.lambda$columnsToString$0(AbstractLambdaWrapper.java:57) ~[native-tests:3.5.4.1]
        at java.base@21.0.1/java.util.stream.ReferencePipeline$3$1.accept(ReferencePipeline.java:197) ~[na:na]
        at java.base@21.0.1/java.util.Spliterators$ArraySpliterator.forEachRemaining(Spliterators.java:1024) ~[na:na]
        at java.base@21.0.1/java.util.stream.AbstractPipeline.copyInto(AbstractPipeline.java:509) ~[native-tests:na]
        at java.base@21.0.1/java.util.stream.AbstractPipeline.wrapAndCopyInto(AbstractPipeline.java:499) ~[native-tests:na]
        at java.base@21.0.1/java.util.stream.ReduceOps$ReduceOp.evaluateSequential(ReduceOps.java:921) ~[native-tests:na]
        at java.base@21.0.1/java.util.stream.AbstractPipeline.evaluate(AbstractPipeline.java:234) ~[native-tests:na]
        at java.base@21.0.1/java.util.stream.ReferencePipeline.collect(ReferencePipeline.java:682) ~[native-tests:na]
        at com.baomidou.mybatisplus.core.conditions.AbstractLambdaWrapper.columnsToString(AbstractLambdaWrapper.java:57) ~[native-tests:3.5.4.1]
        at com.baomidou.mybatisplus.core.conditions.query.LambdaQueryWrapper.doSelect(LambdaQueryWrapper.java:120) ~[native-tests:3.5.4.1]
        at com.baomidou.mybatisplus.core.conditions.query.LambdaQueryWrapper.select(LambdaQueryWrapper.java:106) ~[native-tests:3.5.4.1]
        at com.example.bootnative.BootNativeApplication.lambda$runWithMybatisPlus$2(BootNativeApplication.java:67) ~[native-tests:na]
        at org.springframework.boot.SpringApplication.callRunner(SpringApplication.java:765) ~[native-tests:3.1.4]
        ... 80 common frames omitted
Caused by: java.lang.ClassNotFoundException: com.example.bootnative.BootNativeApplication$$Lambda$0e4dae6cce3633a42432312a352810f4c99affcf
        at org.graalvm.nativeimage.builder/com.oracle.svm.core.hub.ClassForNameSupport.forName(ClassForNameSupport.java:122) ~[na:na]
        at org.graalvm.nativeimage.builder/com.oracle.svm.core.hub.ClassForNameSupport.forName(ClassForNameSupport.java:86) ~[na:na]
        at java.base@21.0.1/java.lang.Class.forName(DynamicHub.java:1346) ~[native-tests:na]
        at java.base@21.0.1/java.lang.Class.forName(DynamicHub.java:1335) ~[native-tests:na]
        at java.base@21.0.1/java.io.ObjectInputStream.resolveClass(ObjectInputStream.java:804) ~[native-tests:na]
        at com.baomidou.mybatisplus.core.toolkit.support.SerializedLambda$1.resolveClass(SerializedLambda.java:50) ~[na:na]
        at java.base@21.0.1/java.io.ObjectInputStream.readNonProxyDesc(ObjectInputStream.java:2061) ~[native-tests:na]
        at java.base@21.0.1/java.io.ObjectInputStream.readClassDesc(ObjectInputStream.java:1927) ~[native-tests:na]
        at java.base@21.0.1/java.io.ObjectInputStream.readOrdinaryObject(ObjectInputStream.java:2252) ~[native-tests:na]
        at java.base@21.0.1/java.io.ObjectInputStream.readObject0(ObjectInputStream.java:1762) ~[native-tests:na]
        at java.base@21.0.1/java.io.ObjectInputStream.readObject(ObjectInputStream.java:540) ~[native-tests:na]
        at java.base@21.0.1/java.io.ObjectInputStream.readObject(ObjectInputStream.java:498) ~[native-tests:na]
        at com.baomidou.mybatisplus.core.toolkit.support.SerializedLambda.extract(SerializedLambda.java:55) ~[native-tests:3.5.4.1]
        ... 96 common frames omitted

com.example.bootnative.BootNativeApplicationTests > contextLoads() FAILED


Failures (1):
  JUnit Jupiter:BootNativeApplicationTests:contextLoads()
    MethodSource [className = 'com.example.bootnative.BootNativeApplicationTests', methodName = 'contextLoads', methodParameterTypes = '']
    => java.lang.IllegalStateException: Failed to load ApplicationContext for [AotMergedContextConfiguration@26cdac41 testClass = com.example.bootnative.BootNativeApplicationTests, contextInitializerClass = com.example.bootnative.BootNativeApplicationTests__TestContext001_ApplicationContextInitializer, original = [WebMergedContextConfiguration@7f3b6454 testClass = com.example.bootnative.BootNativeApplicationTests, locations = [], classes = [com.example.bootnative.BootNativeApplication], contextInitializerClasses = [], activeProfiles = [], propertySourceLocations = [], propertySourceProperties = ["org.springframework.boot.test.context.SpringBootTestContextBootstrapper=true"], contextCustomizers = [org.springframework.boot.test.context.filter.ExcludeFilterContextCustomizer@187dc579, org.springframework.boot.test.json.DuplicateJsonObjectContextCustomizerFactory$DuplicateJsonObjectContextCustomizer@d36509, org.springframework.boot.test.mock.mockito.MockitoContextCustomizer@0, org.springframework.boot.test.web.client.TestRestTemplateContextCustomizer@4b69fe8e, org.springframework.boot.test.autoconfigure.actuate.observability.ObservabilityContextCustomizerFactory$DisableObservabilityContextCustomizer@1f, org.springframework.boot.test.autoconfigure.properties.PropertyMappingContextCustomizer@0, org.springframework.boot.test.autoconfigure.web.servlet.WebDriverContextCustomizer@1c88b67b, org.springframework.boot.test.context.SpringBootTestAnnotation@f25b5a7f], resourceBasePath = "src/main/webapp", contextLoader = org.springframework.boot.test.context.SpringBootContextLoader, parent = null]]
       org.springframework.test.context.cache.DefaultCacheAwareContextLoaderDelegate.loadContext(DefaultCacheAwareContextLoaderDelegate.java:143)
       org.springframework.test.context.support.DefaultTestContext.getApplicationContext(DefaultTestContext.java:127)
       org.springframework.test.context.web.ServletTestExecutionListener.setUpRequestContextIfNecessary(ServletTestExecutionListener.java:191)
       org.springframework.test.context.web.ServletTestExecutionListener.prepareTestInstance(ServletTestExecutionListener.java:130)
       org.springframework.test.context.TestContextManager.prepareTestInstance(TestContextManager.java:241)
       [...]
     Caused by: java.lang.IllegalStateException: Failed to execute ApplicationRunner
       org.springframework.boot.SpringApplication.callRunner(SpringApplication.java:768)
       org.springframework.boot.SpringApplication.callRunners(SpringApplication.java:755)
       org.springframework.boot.SpringApplication.run(SpringApplication.java:322)
       org.springframework.boot.test.context.SpringBootContextLoader.lambda$loadContext$3(SpringBootContextLoader.java:137)
       org.springframework.util.function.ThrowingSupplier.get(ThrowingSupplier.java:58)
       [...]
     Caused by: com.baomidou.mybatisplus.core.exceptions.MybatisPlusException: java.lang.ClassNotFoundException: com.example.bootnative.BootNativeApplication$$Lambda$0e4dae6cce3633a42432312a352810f4c99affcf
       com.baomidou.mybatisplus.core.toolkit.support.SerializedLambda.extract(SerializedLambda.java:58)
       com.baomidou.mybatisplus.core.toolkit.LambdaUtils.extract(LambdaUtils.java:67)
       com.baomidou.mybatisplus.core.conditions.AbstractLambdaWrapper.getColumnCache(AbstractLambdaWrapper.java:128)
       com.baomidou.mybatisplus.core.conditions.AbstractLambdaWrapper.columnToString(AbstractLambdaWrapper.java:66)
       com.baomidou.mybatisplus.core.conditions.AbstractLambdaWrapper.lambda$columnsToString$0(AbstractLambdaWrapper.java:57)
       [...]
     Caused by: java.lang.ClassNotFoundException: com.example.bootnative.BootNativeApplication$$Lambda$0e4dae6cce3633a42432312a352810f4c99affcf
       org.graalvm.nativeimage.builder/com.oracle.svm.core.hub.ClassForNameSupport.forName(ClassForNameSupport.java:122)
       org.graalvm.nativeimage.builder/com.oracle.svm.core.hub.ClassForNameSupport.forName(ClassForNameSupport.java:86)
       java.base@21.0.1/java.lang.Class.forName(DynamicHub.java:1346)
       java.base@21.0.1/java.lang.Class.forName(DynamicHub.java:1335)
       java.base@21.0.1/java.io.ObjectInputStream.resolveClass(ObjectInputStream.java:804)
       [...]

Test run finished after 177 ms
[         2 containers found      ]
[         0 containers skipped    ]
[         2 containers started    ]
[         0 containers aborted    ]
[         2 containers successful ]
[         0 containers failed     ]
[         1 tests found           ]
[         0 tests skipped         ]
[         1 tests started         ]
[         0 tests aborted         ]
[         0 tests successful      ]
[         1 tests failed          ]

[INFO] ------------------------------------------------------------------------
[INFO] BUILD FAILURE
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  03:14 min (Wall Clock)
[INFO] Finished at: 2023-11-28T19:41:19+08:00
[INFO] ------------------------------------------------------------------------
[ERROR] Failed to execute goal org.graalvm.buildtools:native-maven-plugin:0.9.27:test (test-native) on project boot-native: Execution of /home/linghengqian/TwinklingLiftWorks/git/public/boot-native/target/native-tests --xml-output-dir /home/linghengqian/TwinklingLiftWorks/git/public/boot-native/target/native-test-reports -Djunit.platform.listeners.uid.tracking.output.dir=/home/linghengqian/TwinklingLiftWorks/git/public/boot-native/target/test-ids returned non-zero result -> [Help 1]
[ERROR] 
[ERROR] To see the full stack trace of the errors, re-run Maven with the -e switch.
[ERROR] Re-run Maven using the -X switch to enable full debug logging.
[ERROR] 
[ERROR] For more information about the errors and possible solutions, please read the following articles:
[ERROR] [Help 1] http://cwiki.apache.org/confluence/display/MAVEN/MojoExecutionException

```
