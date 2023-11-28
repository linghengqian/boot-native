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
[INFO] Copying 5 resources from src/main/resources to target/classes
[INFO] 
[INFO] --- compiler:3.11.0:compile (default-compile) @ boot-native ---
[INFO] Changes detected - recompiling the module! :source
[INFO] Compiling 7 source files with javac [debug release 17] to target/classes
[INFO] 
[INFO] --- resources:3.3.1:testResources (default-testResources) @ boot-native ---
[INFO] skip non existing resourceDirectory /home/linghengqian/TwinklingLiftWorks/git/public/boot-native/src/test/resources
[INFO] 
[INFO] --- compiler:3.11.0:testCompile (default-testCompile) @ boot-native ---
[INFO] Changes detected - recompiling the module! :dependency
[INFO] Compiling 1 source file with javac [debug release 17] to target/test-classes
[INFO] 
[INFO] --- spring-boot:3.1.4:process-test-aot (process-test-aot) @ boot-native ---
20:34:33.875 [main] INFO org.springframework.test.context.aot.TestClassScanner -- Scanning for Spring test classes in all packages in classpath roots [/home/linghengqian/TwinklingLiftWorks/git/public/boot-native/target/test-classes]
20:34:34.547 [main] INFO org.springframework.test.context.support.AnnotationConfigContextLoaderUtils -- Could not detect default configuration classes for test class [com.example.bootnative.BootNativeApplicationTests]: BootNativeApplicationTests does not declare any static, non-private, non-final, nested classes annotated with @Configuration.
20:34:34.933 [main] INFO org.springframework.boot.test.context.SpringBootTestContextBootstrapper -- Found @SpringBootConfiguration com.example.bootnative.BootNativeApplication for test class com.example.bootnative.BootNativeApplicationTests

  .   ____          _            __ _ _
 /\\ / ___'_ __ _ _(_)_ __  __ _ \ \ \ \
( ( )\___ | '_ | '_| | '_ \/ _` | \ \ \ \
 \\/  ___)| |_)| | | | | || (_| |  ) ) ) )
  '  |____| .__|_| |_|_| |_\__, | / / / /
 =========|_|==============|___/=/_/_/_/
 :: Spring Boot ::                (v3.1.4)

2023-11-28T20:34:35.993+08:00  INFO 13203 --- [           main] c.e.b.BootNativeApplicationTests         : Starting BootNativeApplicationTests using Java 21.0.1 with PID 13203 (/home/linghengqian/TwinklingLiftWorks/git/public/boot-native/target/test-classes started by linghengqian in /home/linghengqian/TwinklingLiftWorks/git/public/boot-native)
2023-11-28T20:34:35.995+08:00  INFO 13203 --- [           main] c.e.b.BootNativeApplicationTests         : No active profile set, falling back to 1 default profile: "default"
[INFO] 
[INFO] --- surefire:3.0.0:test (default-test) @ boot-native ---
[WARNING]  Parameter 'systemProperties' is deprecated: Use systemPropertyVariables instead.
[INFO] Using auto detected provider org.apache.maven.surefire.junitplatform.JUnitPlatformProvider
[INFO] 
[INFO] -------------------------------------------------------
[INFO]  T E S T S
[INFO] -------------------------------------------------------
[INFO] Running com.example.bootnative.BootNativeApplicationTests
20:34:43.798 [main] INFO org.springframework.test.context.support.AnnotationConfigContextLoaderUtils -- Could not detect default configuration classes for test class [com.example.bootnative.BootNativeApplicationTests]: BootNativeApplicationTests does not declare any static, non-private, non-final, nested classes annotated with @Configuration.
20:34:43.916 [main] INFO org.springframework.boot.test.context.SpringBootTestContextBootstrapper -- Found @SpringBootConfiguration com.example.bootnative.BootNativeApplication for test class com.example.bootnative.BootNativeApplicationTests

  .   ____          _            __ _ _
 /\\ / ___'_ __ _ _(_)_ __  __ _ \ \ \ \
( ( )\___ | '_ | '_| | '_ \/ _` | \ \ \ \
 \\/  ___)| |_)| | | | | || (_| |  ) ) ) )
  '  |____| .__|_| |_|_| |_\__, | / / / /
 =========|_|==============|___/=/_/_/_/
 :: Spring Boot ::                (v3.1.4)

2023-11-28T20:34:44.303+08:00  INFO 13241 --- [           main] c.e.b.BootNativeApplicationTests         : Starting BootNativeApplicationTests using Java 21.0.1 with PID 13241 (started by linghengqian in /home/linghengqian/TwinklingLiftWorks/git/public/boot-native)
2023-11-28T20:34:44.305+08:00  INFO 13241 --- [           main] c.e.b.BootNativeApplicationTests         : No active profile set, falling back to 1 default profile: "default"
2023-11-28T20:34:45.233+08:00  INFO 13241 --- [           main] trationDelegate$BeanPostProcessorChecker : Bean 'spring.datasource.dynamic-com.baomidou.dynamic.datasource.spring.boot.autoconfigure.DynamicDataSourceProperties' of type [com.baomidou.dynamic.datasource.spring.boot.autoconfigure.DynamicDataSourceProperties] is not eligible for getting processed by all BeanPostProcessors (for example: not eligible for auto-proxying)
2023-11-28T20:34:45.236+08:00  INFO 13241 --- [           main] trationDelegate$BeanPostProcessorChecker : Bean 'com.baomidou.dynamic.datasource.spring.boot.autoconfigure.DynamicDataSourceAopConfiguration' of type [com.baomidou.dynamic.datasource.spring.boot.autoconfigure.DynamicDataSourceAopConfiguration$$SpringCGLIB$$0] is not eligible for getting processed by all BeanPostProcessors (for example: not eligible for auto-proxying)
2023-11-28T20:34:45.244+08:00  INFO 13241 --- [           main] trationDelegate$BeanPostProcessorChecker : Bean 'dsProcessor' of type [com.baomidou.dynamic.datasource.processor.DsJakartaHeaderProcessor] is not eligible for getting processed by all BeanPostProcessors (for example: not eligible for auto-proxying)
2023-11-28T20:34:45.325+08:00  INFO 13241 --- [           main] c.b.d.d.DynamicRoutingDataSource         : dynamic-datasource - add a datasource named [master] success
2023-11-28T20:34:45.326+08:00  INFO 13241 --- [           main] c.b.d.d.DynamicRoutingDataSource         : dynamic-datasource initial loaded [1] datasource,primary datasource named [master]
2023-11-28T20:34:45.343+08:00  INFO 13241 --- [           main] com.zaxxer.hikari.HikariDataSource       : master - Starting...
2023-11-28T20:34:45.528+08:00  INFO 13241 --- [           main] com.zaxxer.hikari.pool.HikariPool        : master - Added connection conn0: url=jdbc:h2:mem:test user=SA
2023-11-28T20:34:45.531+08:00  INFO 13241 --- [           main] com.zaxxer.hikari.HikariDataSource       : master - Start completed.
 _ _   |_  _ _|_. ___ _ |    _ 
| | |\/|_)(_| | |_\  |_)||_|_\ 
     /               |         
                        3.5.4.1 
2023-11-28T20:34:46.314+08:00  INFO 13241 --- [           main] c.e.b.BootNativeApplicationTests         : Started BootNativeApplicationTests in 2.256 seconds (process running for 3.251)
Message[id=1, message=Hello World on run!]
Message[id=2, message=Hello World! on runWithXmlMapper]
------------演示insert-----------------
2023-11-28T20:34:46.392+08:00  INFO 13241 --- [           main] c.e.bootnative.MyMetaObjectHandler       : 进入insertFill填充了
------------演示select-----------------
simple query:Messages{id=3, message='Hello MybatisPlus', messageType=VOICE}
query wrapper:Messages{id=1, message='Hello World on run!', messageType=null}
------------演示update-----------------
2023-11-28T20:34:46.434+08:00  INFO 13241 --- [           main] c.e.bootnative.MyMetaObjectHandler       : 进入updateFill填充了
2023-11-28T20:34:46.440+08:00  INFO 13241 --- [           main] c.e.bootnative.MyMetaObjectHandler       : 进入updateFill填充了
------------演示delete-----------------
------------演示page-----------------
total:2,records[Messages{id=1, message='Hello MybatisPlus', messageType=TEXT}, Messages{id=2, message='Hello World! on runWithXmlMapper', messageType=null}]
------------演示lambda-----------------
lambda query:null
2023-11-28T20:34:46.506+08:00  INFO 13241 --- [           main] c.e.bootnative.MyMetaObjectHandler       : 进入updateFill填充了
lambda update:1
lambda delete:1
OpenJDK 64-Bit Server VM warning: Sharing is only supported for boot loader classes because bootstrap classpath has been appended
WARNING: A Java agent has been loaded dynamically (/home/linghengqian/.m2/repository/net/bytebuddy/byte-buddy-agent/1.14.8/byte-buddy-agent-1.14.8.jar)
WARNING: If a serviceability tool is in use, please run with -XX:+EnableDynamicAgentLoading to hide this warning
WARNING: If a serviceability tool is not in use, please run with -Djdk.instrument.traceUsage for more information
WARNING: Dynamic loading of agents will be disallowed by default in a future release
test
[INFO] Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 3.674 s - in com.example.bootnative.BootNativeApplicationTests
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
[INFO] [graalvm reachability metadata repository for ch.qos.logback:logback-classic:1.4.11]: Configuration directory not found. Trying latest version.
[INFO] [graalvm reachability metadata repository for ch.qos.logback:logback-classic:1.4.11]: Configuration directory is ch.qos.logback/logback-classic/1.4.1
[INFO] [graalvm reachability metadata repository for com.fasterxml.jackson.core:jackson-databind:2.15.2]: Configuration directory is com.fasterxml.jackson.core/jackson-databind/2.15.2
[INFO] [graalvm reachability metadata repository for org.apache.tomcat.embed:tomcat-embed-core:10.1.13]: Configuration directory not found. Trying latest version.
[INFO] [graalvm reachability metadata repository for org.apache.tomcat.embed:tomcat-embed-core:10.1.13]: Configuration directory is org.apache.tomcat.embed/tomcat-embed-core/10.0.20
[INFO] [graalvm reachability metadata repository for org.mockito:mockito-core:5.3.1]: Configuration directory not found. Trying latest version.
[INFO] [graalvm reachability metadata repository for org.mockito:mockito-core:5.3.1]: Configuration directory is org.mockito/mockito-core/4.8.1
[INFO] Executing: /home/linghengqian/.sdkman/candidates/java/21.0.1-graalce/bin/native-image -cp /home/linghengqian/TwinklingLiftWorks/git/public/boot-native/target/classes:/home/linghengqian/TwinklingLiftWorks/git/public/boot-native/target/test-classes:/home/linghengqian/.m2/repository/com/h2database/h2/2.1.214/h2-2.1.214.jar:/home/linghengqian/.m2/repository/com/zaxxer/HikariCP/5.0.1/HikariCP-5.0.1.jar:/home/linghengqian/.m2/repository/org/slf4j/slf4j-api/2.0.9/slf4j-api-2.0.9.jar:/home/linghengqian/.m2/repository/com/baomidou/dynamic-datasource-spring-boot3-starter/4.2.0/dynamic-datasource-spring-boot3-starter-4.2.0.jar:/home/linghengqian/.m2/repository/com/baomidou/dynamic-datasource-spring-boot-common/4.2.0/dynamic-datasource-spring-boot-common-4.2.0.jar:/home/linghengqian/.m2/repository/com/baomidou/dynamic-datasource-spring/4.2.0/dynamic-datasource-spring-4.2.0.jar:/home/linghengqian/.m2/repository/com/baomidou/dynamic-datasource-creator/4.2.0/dynamic-datasource-creator-4.2.0.jar:/home/linghengqian/.m2/repository/org/springframework/boot/spring-boot-starter-aop/3.1.4/spring-boot-starter-aop-3.1.4.jar:/home/linghengqian/.m2/repository/org/aspectj/aspectjweaver/1.9.20/aspectjweaver-1.9.20.jar:/home/linghengqian/.m2/repository/org/springframework/boot/spring-boot-starter-undertow/3.1.4/spring-boot-starter-undertow-3.1.4.jar:/home/linghengqian/.m2/repository/io/undertow/undertow-core/2.3.8.Final/undertow-core-2.3.8.Final.jar:/home/linghengqian/.m2/repository/org/jboss/logging/jboss-logging/3.5.3.Final/jboss-logging-3.5.3.Final.jar:/home/linghengqian/.m2/repository/org/jboss/xnio/xnio-api/3.8.8.Final/xnio-api-3.8.8.Final.jar:/home/linghengqian/.m2/repository/org/wildfly/common/wildfly-common/1.5.4.Final/wildfly-common-1.5.4.Final.jar:/home/linghengqian/.m2/repository/org/wildfly/client/wildfly-client-config/1.0.1.Final/wildfly-client-config-1.0.1.Final.jar:/home/linghengqian/.m2/repository/org/jboss/xnio/xnio-nio/3.8.8.Final/xnio-nio-3.8.8.Final.jar:/home/linghengqian/.m2/repository/org/jboss/threads/jboss-threads/3.5.0.Final/jboss-threads-3.5.0.Final.jar:/home/linghengqian/.m2/repository/io/undertow/undertow-servlet/2.3.8.Final/undertow-servlet-2.3.8.Final.jar:/home/linghengqian/.m2/repository/jakarta/servlet/jakarta.servlet-api/6.0.0/jakarta.servlet-api-6.0.0.jar:/home/linghengqian/.m2/repository/io/undertow/undertow-websockets-jsr/2.3.8.Final/undertow-websockets-jsr-2.3.8.Final.jar:/home/linghengqian/.m2/repository/jakarta/websocket/jakarta.websocket-api/2.1.1/jakarta.websocket-api-2.1.1.jar:/home/linghengqian/.m2/repository/jakarta/websocket/jakarta.websocket-client-api/2.1.1/jakarta.websocket-client-api-2.1.1.jar:/home/linghengqian/.m2/repository/org/apache/tomcat/embed/tomcat-embed-el/10.1.13/tomcat-embed-el-10.1.13.jar:/home/linghengqian/.m2/repository/com/baomidou/mybatis-plus-spring-boot3-starter/3.5.4.1/mybatis-plus-spring-boot3-starter-3.5.4.1.jar:/home/linghengqian/.m2/repository/com/baomidou/mybatis-plus/3.5.4.1/mybatis-plus-3.5.4.1.jar:/home/linghengqian/.m2/repository/com/baomidou/mybatis-plus-core/3.5.4.1/mybatis-plus-core-3.5.4.1.jar:/home/linghengqian/.m2/repository/com/baomidou/mybatis-plus-annotation/3.5.4.1/mybatis-plus-annotation-3.5.4.1.jar:/home/linghengqian/.m2/repository/com/baomidou/mybatis-plus-extension/3.5.4.1/mybatis-plus-extension-3.5.4.1.jar:/home/linghengqian/.m2/repository/org/mybatis/mybatis/3.5.13/mybatis-3.5.13.jar:/home/linghengqian/.m2/repository/com/github/jsqlparser/jsqlparser/4.6/jsqlparser-4.6.jar:/home/linghengqian/.m2/repository/org/mybatis/mybatis-spring/3.0.2/mybatis-spring-3.0.2.jar:/home/linghengqian/.m2/repository/com/baomidou/mybatis-plus-spring-boot-autoconfigure/3.5.4.1/mybatis-plus-spring-boot-autoconfigure-3.5.4.1.jar:/home/linghengqian/.m2/repository/org/springframework/boot/spring-boot-autoconfigure/3.1.4/spring-boot-autoconfigure-3.1.4.jar:/home/linghengqian/.m2/repository/org/springframework/boot/spring-boot/3.1.4/spring-boot-3.1.4.jar:/home/linghengqian/.m2/repository/org/springframework/boot/spring-boot-starter-jdbc/3.1.4/spring-boot-starter-jdbc-3.1.4.jar:/home/linghengqian/.m2/repository/org/springframework/spring-jdbc/6.0.12/spring-jdbc-6.0.12.jar:/home/linghengqian/.m2/repository/org/springframework/spring-tx/6.0.12/spring-tx-6.0.12.jar:/home/linghengqian/.m2/repository/org/springframework/boot/spring-boot-starter-web/3.1.4/spring-boot-starter-web-3.1.4.jar:/home/linghengqian/.m2/repository/org/springframework/boot/spring-boot-starter/3.1.4/spring-boot-starter-3.1.4.jar:/home/linghengqian/.m2/repository/org/springframework/boot/spring-boot-starter-logging/3.1.4/spring-boot-starter-logging-3.1.4.jar:/home/linghengqian/.m2/repository/ch/qos/logback/logback-classic/1.4.11/logback-classic-1.4.11.jar:/home/linghengqian/.m2/repository/ch/qos/logback/logback-core/1.4.11/logback-core-1.4.11.jar:/home/linghengqian/.m2/repository/org/apache/logging/log4j/log4j-to-slf4j/2.20.0/log4j-to-slf4j-2.20.0.jar:/home/linghengqian/.m2/repository/org/apache/logging/log4j/log4j-api/2.20.0/log4j-api-2.20.0.jar:/home/linghengqian/.m2/repository/org/slf4j/jul-to-slf4j/2.0.9/jul-to-slf4j-2.0.9.jar:/home/linghengqian/.m2/repository/jakarta/annotation/jakarta.annotation-api/2.1.1/jakarta.annotation-api-2.1.1.jar:/home/linghengqian/.m2/repository/org/yaml/snakeyaml/1.33/snakeyaml-1.33.jar:/home/linghengqian/.m2/repository/org/springframework/boot/spring-boot-starter-json/3.1.4/spring-boot-starter-json-3.1.4.jar:/home/linghengqian/.m2/repository/com/fasterxml/jackson/core/jackson-databind/2.15.2/jackson-databind-2.15.2.jar:/home/linghengqian/.m2/repository/com/fasterxml/jackson/core/jackson-annotations/2.15.2/jackson-annotations-2.15.2.jar:/home/linghengqian/.m2/repository/com/fasterxml/jackson/core/jackson-core/2.15.2/jackson-core-2.15.2.jar:/home/linghengqian/.m2/repository/com/fasterxml/jackson/datatype/jackson-datatype-jdk8/2.15.2/jackson-datatype-jdk8-2.15.2.jar:/home/linghengqian/.m2/repository/com/fasterxml/jackson/datatype/jackson-datatype-jsr310/2.15.2/jackson-datatype-jsr310-2.15.2.jar:/home/linghengqian/.m2/repository/com/fasterxml/jackson/module/jackson-module-parameter-names/2.15.2/jackson-module-parameter-names-2.15.2.jar:/home/linghengqian/.m2/repository/org/springframework/boot/spring-boot-starter-tomcat/3.1.4/spring-boot-starter-tomcat-3.1.4.jar:/home/linghengqian/.m2/repository/org/apache/tomcat/embed/tomcat-embed-core/10.1.13/tomcat-embed-core-10.1.13.jar:/home/linghengqian/.m2/repository/org/apache/tomcat/embed/tomcat-embed-websocket/10.1.13/tomcat-embed-websocket-10.1.13.jar:/home/linghengqian/.m2/repository/org/springframework/spring-web/6.0.12/spring-web-6.0.12.jar:/home/linghengqian/.m2/repository/org/springframework/spring-beans/6.0.12/spring-beans-6.0.12.jar:/home/linghengqian/.m2/repository/io/micrometer/micrometer-observation/1.11.4/micrometer-observation-1.11.4.jar:/home/linghengqian/.m2/repository/io/micrometer/micrometer-commons/1.11.4/micrometer-commons-1.11.4.jar:/home/linghengqian/.m2/repository/org/springframework/spring-webmvc/6.0.12/spring-webmvc-6.0.12.jar:/home/linghengqian/.m2/repository/org/springframework/spring-aop/6.0.12/spring-aop-6.0.12.jar:/home/linghengqian/.m2/repository/org/springframework/spring-context/6.0.12/spring-context-6.0.12.jar:/home/linghengqian/.m2/repository/org/springframework/spring-expression/6.0.12/spring-expression-6.0.12.jar:/home/linghengqian/.m2/repository/org/springframework/boot/spring-boot-starter-test/3.1.4/spring-boot-starter-test-3.1.4.jar:/home/linghengqian/.m2/repository/org/springframework/boot/spring-boot-test/3.1.4/spring-boot-test-3.1.4.jar:/home/linghengqian/.m2/repository/org/springframework/boot/spring-boot-test-autoconfigure/3.1.4/spring-boot-test-autoconfigure-3.1.4.jar:/home/linghengqian/.m2/repository/com/jayway/jsonpath/json-path/2.8.0/json-path-2.8.0.jar:/home/linghengqian/.m2/repository/jakarta/xml/bind/jakarta.xml.bind-api/4.0.1/jakarta.xml.bind-api-4.0.1.jar:/home/linghengqian/.m2/repository/jakarta/activation/jakarta.activation-api/2.1.2/jakarta.activation-api-2.1.2.jar:/home/linghengqian/.m2/repository/net/minidev/json-smart/2.4.11/json-smart-2.4.11.jar:/home/linghengqian/.m2/repository/net/minidev/accessors-smart/2.4.11/accessors-smart-2.4.11.jar:/home/linghengqian/.m2/repository/org/ow2/asm/asm/9.3/asm-9.3.jar:/home/linghengqian/.m2/repository/org/assertj/assertj-core/3.24.2/assertj-core-3.24.2.jar:/home/linghengqian/.m2/repository/net/bytebuddy/byte-buddy/1.14.8/byte-buddy-1.14.8.jar:/home/linghengqian/.m2/repository/org/hamcrest/hamcrest/2.2/hamcrest-2.2.jar:/home/linghengqian/.m2/repository/org/junit/jupiter/junit-jupiter/5.9.3/junit-jupiter-5.9.3.jar:/home/linghengqian/.m2/repository/org/junit/jupiter/junit-jupiter-api/5.9.3/junit-jupiter-api-5.9.3.jar:/home/linghengqian/.m2/repository/org/junit/jupiter/junit-jupiter-params/5.9.3/junit-jupiter-params-5.9.3.jar:/home/linghengqian/.m2/repository/org/junit/jupiter/junit-jupiter-engine/5.9.3/junit-jupiter-engine-5.9.3.jar:/home/linghengqian/.m2/repository/org/mockito/mockito-core/5.3.1/mockito-core-5.3.1.jar:/home/linghengqian/.m2/repository/net/bytebuddy/byte-buddy-agent/1.14.8/byte-buddy-agent-1.14.8.jar:/home/linghengqian/.m2/repository/org/objenesis/objenesis/3.3/objenesis-3.3.jar:/home/linghengqian/.m2/repository/org/mockito/mockito-junit-jupiter/5.3.1/mockito-junit-jupiter-5.3.1.jar:/home/linghengqian/.m2/repository/org/skyscreamer/jsonassert/1.5.1/jsonassert-1.5.1.jar:/home/linghengqian/.m2/repository/com/vaadin/external/google/android-json/0.0.20131108.vaadin1/android-json-0.0.20131108.vaadin1.jar:/home/linghengqian/.m2/repository/org/springframework/spring-core/6.0.12/spring-core-6.0.12.jar:/home/linghengqian/.m2/repository/org/springframework/spring-jcl/6.0.12/spring-jcl-6.0.12.jar:/home/linghengqian/.m2/repository/org/springframework/spring-test/6.0.12/spring-test-6.0.12.jar:/home/linghengqian/.m2/repository/org/xmlunit/xmlunit-core/2.9.1/xmlunit-core-2.9.1.jar:/home/linghengqian/.m2/repository/org/junit/platform/junit-platform-launcher/1.9.3/junit-platform-launcher-1.9.3.jar:/home/linghengqian/.m2/repository/org/junit/platform/junit-platform-engine/1.9.3/junit-platform-engine-1.9.3.jar:/home/linghengqian/.m2/repository/org/opentest4j/opentest4j/1.2.0/opentest4j-1.2.0.jar:/home/linghengqian/.m2/repository/org/junit/platform/junit-platform-commons/1.9.3/junit-platform-commons-1.9.3.jar:/home/linghengqian/.m2/repository/org/apiguardian/apiguardian-api/1.1.2/apiguardian-api-1.1.2.jar:/home/linghengqian/.m2/repository/org/graalvm/buildtools/native-maven-plugin/0.9.27/native-maven-plugin-0.9.27.jar:/home/linghengqian/.m2/repository/org/graalvm/buildtools/junit-platform-native/0.9.27/junit-platform-native-0.9.27.jar:/home/linghengqian/.m2/repository/org/junit/platform/junit-platform-console/1.9.3/junit-platform-console-1.9.3.jar:/home/linghengqian/.m2/repository/org/junit/platform/junit-platform-reporting/1.9.3/junit-platform-reporting-1.9.3.jar:/home/linghengqian/.m2/repository/org/junit/platform/junit-platform-launcher/1.9.3/junit-platform-launcher-1.9.3.jar:/home/linghengqian/.m2/repository/org/junit/platform/junit-platform-engine/1.9.3/junit-platform-engine-1.9.3.jar:/home/linghengqian/.m2/repository/org/junit/platform/junit-platform-commons/1.9.3/junit-platform-commons-1.9.3.jar:/home/linghengqian/.m2/repository/org/junit/jupiter/junit-jupiter/5.10.0/junit-jupiter-5.10.0.jar:/home/linghengqian/.m2/repository/org/junit/jupiter/junit-jupiter-api/5.10.0/junit-jupiter-api-5.10.0.jar:/home/linghengqian/.m2/repository/org/junit/jupiter/junit-jupiter-params/5.10.0/junit-jupiter-params-5.10.0.jar:/home/linghengqian/.m2/repository/org/junit/jupiter/junit-jupiter-engine/5.10.0/junit-jupiter-engine-5.10.0.jar:/home/linghengqian/.m2/repository/org/graalvm/buildtools/utils/0.9.27/utils-0.9.27.jar:/home/linghengqian/.m2/repository/org/graalvm/buildtools/graalvm-reachability-metadata/0.9.27/graalvm-reachability-metadata-0.9.27.jar:/home/linghengqian/.m2/repository/org/graalvm/buildtools/junit-platform-native/0.9.27/junit-platform-native-0.9.27.jar --no-fallback -o /home/linghengqian/TwinklingLiftWorks/git/public/boot-native/target/native-tests -Djunit.platform.listeners.uid.tracking.output.dir=/home/linghengqian/TwinklingLiftWorks/git/public/boot-native/target/test-ids -H:ConfigurationFileDirectories=/home/linghengqian/TwinklingLiftWorks/git/public/boot-native/target/graalvm-reachability-metadata/15733192e0f6e369451cde2afd11b12ca027fde5/ch.qos.logback/logback-classic/1.4.1,/home/linghengqian/TwinklingLiftWorks/git/public/boot-native/target/graalvm-reachability-metadata/15733192e0f6e369451cde2afd11b12ca027fde5/com.h2database/h2/2.1.210,/home/linghengqian/TwinklingLiftWorks/git/public/boot-native/target/graalvm-reachability-metadata/15733192e0f6e369451cde2afd11b12ca027fde5/io.undertow/undertow-core/2.2.19.Final,/home/linghengqian/TwinklingLiftWorks/git/public/boot-native/target/graalvm-reachability-metadata/15733192e0f6e369451cde2afd11b12ca027fde5/com.zaxxer/HikariCP/5.0.1,/home/linghengqian/TwinklingLiftWorks/git/public/boot-native/target/graalvm-reachability-metadata/15733192e0f6e369451cde2afd11b12ca027fde5/com.fasterxml.jackson.core/jackson-databind/2.15.2,/home/linghengqian/TwinklingLiftWorks/git/public/boot-native/target/graalvm-reachability-metadata/15733192e0f6e369451cde2afd11b12ca027fde5/org.apache.tomcat.embed/tomcat-embed-core/10.0.20,/home/linghengqian/TwinklingLiftWorks/git/public/boot-native/target/graalvm-reachability-metadata/15733192e0f6e369451cde2afd11b12ca027fde5/jakarta.servlet/jakarta.servlet-api/5.0.0,/home/linghengqian/TwinklingLiftWorks/git/public/boot-native/target/graalvm-reachability-metadata/15733192e0f6e369451cde2afd11b12ca027fde5/org.jboss.logging/jboss-logging/3.5.0.Final,/home/linghengqian/TwinklingLiftWorks/git/public/boot-native/target/graalvm-reachability-metadata/15733192e0f6e369451cde2afd11b12ca027fde5/org.mockito/mockito-core/4.8.1 --features=org.graalvm.junit.platform.JUnitPlatformFeature org.graalvm.junit.platform.NativeImageJUnitLauncher
Warning: The option '-H:ResourceConfigurationResources=META-INF/native-image/org.apache.tomcat.embed/tomcat-embed-core/tomcat-resource.json' is experimental and must be enabled via '-H:+UnlockExperimentalVMOptions' in the future.
Warning: The option '-H:ReflectionConfigurationResources=META-INF/native-image/org.apache.tomcat.embed/tomcat-embed-core/tomcat-reflection.json' is experimental and must be enabled via '-H:+UnlockExperimentalVMOptions' in the future.
Warning: The option '-H:ReflectionConfigurationResources=META-INF/native-image/org.apache.tomcat.embed/tomcat-embed-websocket/tomcat-reflection.json' is experimental and must be enabled via '-H:+UnlockExperimentalVMOptions' in the future.
Warning: The option '-H:ReflectionConfigurationResources=META-INF/native-image/org.apache.tomcat.embed/tomcat-embed-el/tomcat-reflection.json' is experimental and must be enabled via '-H:+UnlockExperimentalVMOptions' in the future.
Warning: The option '-H:ResourceConfigurationResources=META-INF/native-image/org.apache.tomcat.embed/tomcat-embed-el/tomcat-resource.json' is experimental and must be enabled via '-H:+UnlockExperimentalVMOptions' in the future.
Warning: The option '-H:ResourceConfigurationResources=META-INF/native-image/org.apache.tomcat.embed/tomcat-embed-websocket/tomcat-resource.json' is experimental and must be enabled via '-H:+UnlockExperimentalVMOptions' in the future.
Warning: Please re-evaluate whether any experimental option is required, and either remove or unlock it. The build output lists all active experimental options, including where they come from and possible alternatives. If you think an experimental option should be considered as stable, please file an issue.
========================================================================================================================
GraalVM Native Image: Generating 'native-tests' (executable)...
========================================================================================================================
[1/8] Initializing...                                                                                    (9.9s @ 0.22GB)
 Java version: 21.0.1+12, vendor version: GraalVM CE 21.0.1+12.1
 Graal compiler: optimization level: 2, target machine: x86-64-v3
 C compiler: gcc (linux, x86_64, 11.4.0)
 Garbage collector: Serial GC (max heap size: 80% of RAM)
 3 user-specific feature(s):
 - com.oracle.svm.thirdparty.gson.GsonFeature
 - org.graalvm.junit.platform.JUnitPlatformFeature
 - org.springframework.aot.nativex.feature.PreComputeFieldFeature
------------------------------------------------------------------------------------------------------------------------
 2 experimental option(s) unlocked:
 - '-H:ResourceConfigurationResources' (origin(s): 'META-INF/native-image/org.apache.tomcat.embed/tomcat-embed-el/native-image.properties' in 'file:///home/linghengqian/.m2/repository/org/apache/tomcat/embed/tomcat-embed-el/10.1.13/tomcat-embed-el-10.1.13.jar', 'META-INF/native-image/org.apache.tomcat.embed/tomcat-embed-core/native-image.properties' in 'file:///home/linghengqian/.m2/repository/org/apache/tomcat/embed/tomcat-embed-core/10.1.13/tomcat-embed-core-10.1.13.jar', 'META-INF/native-image/org.apache.tomcat.embed/tomcat-embed-websocket/native-image.properties' in 'file:///home/linghengqian/.m2/repository/org/apache/tomcat/embed/tomcat-embed-websocket/10.1.13/tomcat-embed-websocket-10.1.13.jar')
 - '-H:ReflectionConfigurationResources' (origin(s): 'META-INF/native-image/org.apache.tomcat.embed/tomcat-embed-el/native-image.properties' in 'file:///home/linghengqian/.m2/repository/org/apache/tomcat/embed/tomcat-embed-el/10.1.13/tomcat-embed-el-10.1.13.jar', 'META-INF/native-image/org.apache.tomcat.embed/tomcat-embed-core/native-image.properties' in 'file:///home/linghengqian/.m2/repository/org/apache/tomcat/embed/tomcat-embed-core/10.1.13/tomcat-embed-core-10.1.13.jar', 'META-INF/native-image/org.apache.tomcat.embed/tomcat-embed-websocket/native-image.properties' in 'file:///home/linghengqian/.m2/repository/org/apache/tomcat/embed/tomcat-embed-websocket/10.1.13/tomcat-embed-websocket-10.1.13.jar')
------------------------------------------------------------------------------------------------------------------------
Build resources:
 - 9.57GB of memory (75.6% of 12.67GB system memory, determined at start)
 - 6 thread(s) (100.0% of 6 available processor(s), determined at start)
[junit-platform-native] Running in 'test listener' mode using files matching pattern [junit-platform-unique-ids*] found in folder [/home/linghengqian/TwinklingLiftWorks/git/public/boot-native/target/test-ids] and its subfolders.
Field org.apache.commons.logging.LogAdapter#log4jSpiPresent set to true at build time
Field org.apache.commons.logging.LogAdapter#log4jSlf4jProviderPresent set to true at build time
Field org.apache.commons.logging.LogAdapter#slf4jSpiPresent set to true at build time
Field org.apache.commons.logging.LogAdapter#slf4jApiPresent set to true at build time
Field org.springframework.core.NativeDetector#inNativeImage set to true at build time
Field org.springframework.http.converter.json.Jackson2ObjectMapperBuilder#jackson2XmlPresent set to false at build time
Field org.springframework.cglib.core.AbstractClassGenerator#inNativeImage set to true at build time
Field org.springframework.boot.logging.logback.LogbackLoggingSystem$Factory#PRESENT set to true at build time
Field org.springframework.aot.AotDetector#inNativeImage set to true at build time
Field org.springframework.boot.test.autoconfigure.restdocs.RestDocsTestExecutionListener#REST_DOCS_PRESENT set to false at build time
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
Field org.springframework.boot.test.mock.mockito.ResetMocksTestExecutionListener#MOCKITO_IS_PRESENT set to true at build time
Field org.springframework.transaction.annotation.AnnotationTransactionAttributeSource#jta12Present set to false at build time
Field org.springframework.transaction.annotation.AnnotationTransactionAttributeSource#ejb3Present set to false at build time
Field org.springframework.boot.test.autoconfigure.webservices.client.MockWebServiceServerTestExecutionListener#MOCK_SERVER_PRESENT set to false at build time
Field org.springframework.web.servlet.view.InternalResourceViewResolver#jstlPresent set to false at build time
Field org.springframework.test.context.web.socket.MockServerContainerContextCustomizerFactory#webSocketPresent set to true at build time
Field org.springframework.core.KotlinDetector#kotlinPresent set to false at build time
Field org.springframework.core.KotlinDetector#kotlinReflectPresent set to false at build time
Field org.springframework.boot.test.web.reactive.server.WebTestClientContextCustomizerFactory#webClientPresent set to false at build time
Field org.springframework.boot.logging.java.JavaLoggingSystem$Factory#PRESENT set to true at build time
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
Field org.springframework.transaction.interceptor.TransactionAspectSupport#vavrPresent set to false at build time
Field org.springframework.transaction.interceptor.TransactionAspectSupport#reactiveStreamsPresent set to false at build time
Field org.springframework.web.context.request.RequestContextHolder#jsfPresent set to false at build time
Field org.springframework.boot.logging.log4j2.Log4J2LoggingSystem$Factory#PRESENT set to false at build time
Field org.springframework.boot.autoconfigure.web.format.WebConversionService#JSR_354_PRESENT set to false at build time
Field org.springframework.format.support.DefaultFormattingConversionService#jsr354Present set to false at build time
Field org.springframework.web.context.support.StandardServletEnvironment#jndiPresent set to true at build time
Field org.springframework.http.converter.support.AllEncompassingFormHttpMessageConverter#jaxb2Present set to true at build time
Field org.springframework.http.converter.support.AllEncompassingFormHttpMessageConverter#jackson2Present set to true at build time
Field org.springframework.http.converter.support.AllEncompassingFormHttpMessageConverter#jackson2XmlPresent set to false at build time
Field org.springframework.http.converter.support.AllEncompassingFormHttpMessageConverter#jackson2SmilePresent set to false at build time
Field org.springframework.http.converter.support.AllEncompassingFormHttpMessageConverter#gsonPresent set to false at build time
Field org.springframework.http.converter.support.AllEncompassingFormHttpMessageConverter#jsonbPresent set to false at build time
Field org.springframework.http.converter.support.AllEncompassingFormHttpMessageConverter#kotlinSerializationCborPresent set to false at build time
Field org.springframework.http.converter.support.AllEncompassingFormHttpMessageConverter#kotlinSerializationJsonPresent set to false at build time
Field org.springframework.http.converter.support.AllEncompassingFormHttpMessageConverter#kotlinSerializationProtobufPresent set to false at build time
Field org.springframework.jdbc.support.SQLErrorCodeSQLExceptionTranslator#userProvidedErrorCodesFilePresent set to false at build time
Field org.springframework.boot.logging.logback.LogbackLoggingSystemProperties#JBOSS_LOGGING_PRESENT set to true at build time
Field org.springframework.core.ReactiveAdapterRegistry#reactorPresent set to false at build time
Field org.springframework.core.ReactiveAdapterRegistry#rxjava3Present set to false at build time
Field org.springframework.core.ReactiveAdapterRegistry#kotlinCoroutinesPresent set to false at build time
Field org.springframework.core.ReactiveAdapterRegistry#mutinyPresent set to false at build time
SLF4J: No SLF4J providers were found.
SLF4J: Defaulting to no-operation (NOP) logger implementation
SLF4J: See https://www.slf4j.org/codes.html#noProviders for further details.
Field org.springframework.web.servlet.mvc.method.annotation.ReactiveTypeHandler#isContextPropagationPresent set to false at build time
Field org.springframework.web.context.support.WebApplicationContextUtils#jsfPresent set to false at build time
Field org.springframework.context.event.ApplicationListenerMethodAdapter#reactiveStreamsPresent set to false at build time
Field org.springframework.web.servlet.support.RequestContext#jstlPresent set to false at build time
[2/8] Performing analysis...  [******]                                                                  (96.8s @ 2.15GB)
   23,927 reachable types   (90.7% of   26,387 total)
   38,266 reachable fields  (65.1% of   58,801 total)
  120,851 reachable methods (63.9% of  189,266 total)
    7,285 types,   840 fields, and 9,777 methods registered for reflection
       67 types,    65 fields, and    57 methods registered for JNI access
        4 native libraries: dl, pthread, rt, z
[3/8] Building universe...                                                                              (10.4s @ 2.28GB)
[4/8] Parsing methods...      [[4/8] Parsing methods...      [***]                                                                      (8.3s @ 2.42GB)
[5/8] Inlining methods...     [***]                                                                      (5.2s @ 3.62GB)
[6/8] Compiling methods...    [********]                                                                (72.0s @ 2.46GB)
[7/8] Layouting methods...    [***]                                                                      (9.9s @ 3.97GB)
[8/8] Creating image...       [***]                                                                     (10.5s @ 2.46GB)
  59.59MB (50.55%) for code area:    79,830 compilation units
  53.98MB (45.79%) for image heap:  533,997 objects and 348 resources
   4.32MB ( 3.66%) for other data
 117.90MB in total
------------------------------------------------------------------------------------------------------------------------
Top 10 origins of code area:                                Top 10 object types in image heap:
  15.53MB java.base                                           18.29MB byte[] for code metadata
   6.08MB h2-2.1.214.jar                                       7.74MB byte[] for java.lang.String
   4.33MB java.xml                                             5.77MB java.lang.Class
   4.27MB tomcat-embed-core-10.1.13.jar                        5.20MB java.lang.String
   2.05MB jackson-databind-2.15.2.jar                          2.06MB byte[] for embedded resources
   1.71MB svm.jar (Native Image)                               2.01MB com.oracle.svm.core.hub.DynamicHubCompanion
   1.69MB spring-core-6.0.12.jar                               1.58MB byte[] for reflection metadata
   1.62MB jsqlparser-4.6.jar                                   1.06MB java.lang.String[]
   1.54MB mybatis-3.5.13.jar                                 909.83kB byte[] for general heap data
   1.47MB aspectjweaver-1.9.20.jar                           858.28kB c.o.svm.core.hub.DynamicHub$ReflectionMetadata
  18.74MB for 130 more packages                                8.53MB for 4684 more object types
------------------------------------------------------------------------------------------------------------------------
Recommendations:
 INIT: Adopt '--strict-image-heap' to prepare for the next GraalVM release.
 HEAP: Set max heap for improved and more predictable memory usage.
 CPU:  Enable more CPU features with '-march=native' for improved performance.
------------------------------------------------------------------------------------------------------------------------
                       19.7s (8.7% of total time) in 102 GCs | Peak RSS: 6.14GB | CPU load: 4.71
------------------------------------------------------------------------------------------------------------------------
Produced artifacts:
 /home/linghengqian/TwinklingLiftWorks/git/public/boot-native/target/native-tests (executable)
========================================================================================================================
Finished generating 'native-tests' in 3m 44s.
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

2023-11-28T20:38:34.200+08:00  INFO 13553 --- [           main] c.e.b.BootNativeApplicationTests         : Starting AOT-processed BootNativeApplicationTests using Java 21.0.1 with PID 13553 (started by linghengqian in /home/linghengqian/TwinklingLiftWorks/git/public/boot-native)
2023-11-28T20:38:34.200+08:00  INFO 13553 --- [           main] c.e.b.BootNativeApplicationTests         : No active profile set, falling back to 1 default profile: "default"
2023-11-28T20:38:34.211+08:00  INFO 13553 --- [           main] trationDelegate$BeanPostProcessorChecker : Bean 'spring.datasource.dynamic-com.baomidou.dynamic.datasource.spring.boot.autoconfigure.DynamicDataSourceProperties' of type [com.baomidou.dynamic.datasource.spring.boot.autoconfigure.DynamicDataSourceProperties] is not eligible for getting processed by all BeanPostProcessors (for example: not eligible for auto-proxying)
2023-11-28T20:38:34.211+08:00  INFO 13553 --- [           main] trationDelegate$BeanPostProcessorChecker : Bean 'com.baomidou.dynamic.datasource.spring.boot.autoconfigure.DynamicDataSourceAopConfiguration' of type [com.baomidou.dynamic.datasource.spring.boot.autoconfigure.DynamicDataSourceAopConfiguration$$SpringCGLIB$$0] is not eligible for getting processed by all BeanPostProcessors (for example: not eligible for auto-proxying)
2023-11-28T20:38:34.212+08:00  INFO 13553 --- [           main] trationDelegate$BeanPostProcessorChecker : Bean 'dsProcessor' of type [com.baomidou.dynamic.datasource.processor.DsJakartaHeaderProcessor] is not eligible for getting processed by all BeanPostProcessors (for example: not eligible for auto-proxying)
2023-11-28T20:38:34.218+08:00  INFO 13553 --- [           main] c.b.d.d.DynamicRoutingDataSource         : dynamic-datasource - add a datasource named [master] success
2023-11-28T20:38:34.218+08:00  INFO 13553 --- [           main] c.b.d.d.DynamicRoutingDataSource         : dynamic-datasource initial loaded [1] datasource,primary datasource named [master]
2023-11-28T20:38:34.225+08:00  INFO 13553 --- [           main] com.zaxxer.hikari.HikariDataSource       : master - Starting...
2023-11-28T20:38:34.229+08:00  INFO 13553 --- [           main] com.zaxxer.hikari.pool.HikariPool        : master - Added connection conn0: url=jdbc:h2:mem:test user=SA
2023-11-28T20:38:34.229+08:00  INFO 13553 --- [           main] com.zaxxer.hikari.HikariDataSource       : master - Start completed.
 _ _   |_  _ _|_. ___ _ |    _ 
| | |\/|_)(_| | |_\  |_)||_|_\ 
     /               |         
                        3.5.4.1 
2023-11-28T20:38:34.345+08:00  INFO 13553 --- [           main] c.e.b.BootNativeApplicationTests         : Started BootNativeApplicationTests in 0.161 seconds (process running for 0.17)
Message[id=1, message=Hello World on run!]
Message[id=2, message=Hello World! on runWithXmlMapper]
------------演示insert-----------------
2023-11-28T20:38:34.347+08:00  INFO 13553 --- [           main] c.e.bootnative.MyMetaObjectHandler       : 进入insertFill填充了
------------演示select-----------------
simple query:Messages{id=3, message='Hello MybatisPlus', messageType=VOICE}
query wrapper:Messages{id=1, message='Hello World on run!', messageType=null}
------------演示update-----------------
2023-11-28T20:38:34.350+08:00  INFO 13553 --- [           main] c.e.bootnative.MyMetaObjectHandler       : 进入updateFill填充了
2023-11-28T20:38:34.350+08:00  INFO 13553 --- [           main] c.e.bootnative.MyMetaObjectHandler       : 进入updateFill填充了
------------演示delete-----------------
------------演示page-----------------
total:2,records[Messages{id=1, message='Hello MybatisPlus', messageType=TEXT}, Messages{id=2, message='Hello World! on runWithXmlMapper', messageType=null}]
------------演示lambda-----------------
lambda query:null
2023-11-28T20:38:34.354+08:00  INFO 13553 --- [           main] c.e.bootnative.MyMetaObjectHandler       : 进入updateFill填充了
lambda update:1
lambda delete:1
test
com.example.bootnative.BootNativeApplicationTests > contextLoads() SUCCESSFUL


Test run finished after 178 ms
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
[         1 tests successful      ]
[         0 tests failed          ]

2023-11-28T20:38:34.357+08:00  INFO 13553 --- [extShutdownHook] c.b.d.d.DynamicRoutingDataSource         : dynamic-datasource start closing ....
2023-11-28T20:38:34.357+08:00  INFO 13553 --- [extShutdownHook] com.zaxxer.hikari.HikariDataSource       : master - Shutdown initiated...
2023-11-28T20:38:34.360+08:00  INFO 13553 --- [extShutdownHook] com.zaxxer.hikari.HikariDataSource       : master - Shutdown completed.
2023-11-28T20:38:34.361+08:00  INFO 13553 --- [extShutdownHook] c.b.d.d.d.DefaultDataSourceDestroyer     : dynamic-datasource close the datasource named [master] success,
2023-11-28T20:38:34.361+08:00  INFO 13553 --- [extShutdownHook] c.b.d.d.DynamicRoutingDataSource         : dynamic-datasource all closed success,bye
[INFO] 
[INFO] --- native:0.9.27:test (native-test) @ boot-native ---
[INFO] ====================
[INFO] Initializing project: boot-native
[INFO] ====================
[INFO] [graalvm reachability metadata repository for com.h2database:h2:2.1.214]: Configuration directory not found. Trying latest version.
[INFO] [graalvm reachability metadata repository for com.h2database:h2:2.1.214]: Configuration directory is com.h2database/h2/2.1.210
[INFO] [graalvm reachability metadata repository for com.zaxxer:HikariCP:5.0.1]: Configuration directory is com.zaxxer/HikariCP/5.0.1
[INFO] [graalvm reachability metadata repository for io.undertow:undertow-core:2.3.8.Final]: Configuration directory not found. Trying latest version.
[INFO] [graalvm reachability metadata repository for io.undertow:undertow-core:2.3.8.Final]: Configuration directory is io.undertow/undertow-core/2.2.19.Final
[INFO] [graalvm reachability metadata repository for org.jboss.logging:jboss-logging:3.5.3.Final]: Configuration directory not found. Trying latest version.
[INFO] [graalvm reachability metadata repository for org.jboss.logging:jboss-logging:3.5.3.Final]: Configuration directory is org.jboss.logging/jboss-logging/3.5.0.Final
[INFO] [graalvm reachability metadata repository for jakarta.servlet:jakarta.servlet-api:6.0.0]: Configuration directory not found. Trying latest version.
[INFO] [graalvm reachability metadata repository for jakarta.servlet:jakarta.servlet-api:6.0.0]: Configuration directory is jakarta.servlet/jakarta.servlet-api/5.0.0
[INFO] [graalvm reachability metadata repository for ch.qos.logback:logback-classic:1.4.11]: Configuration directory not found. Trying latest version.
[INFO] [graalvm reachability metadata repository for ch.qos.logback:logback-classic:1.4.11]: Configuration directory is ch.qos.logback/logback-classic/1.4.1
[INFO] [graalvm reachability metadata repository for com.fasterxml.jackson.core:jackson-databind:2.15.2]: Configuration directory is com.fasterxml.jackson.core/jackson-databind/2.15.2
[INFO] [graalvm reachability metadata repository for org.apache.tomcat.embed:tomcat-embed-core:10.1.13]: Configuration directory not found. Trying latest version.
[INFO] [graalvm reachability metadata repository for org.apache.tomcat.embed:tomcat-embed-core:10.1.13]: Configuration directory is org.apache.tomcat.embed/tomcat-embed-core/10.0.20
[INFO] [graalvm reachability metadata repository for org.mockito:mockito-core:5.3.1]: Configuration directory not found. Trying latest version.
[INFO] [graalvm reachability metadata repository for org.mockito:mockito-core:5.3.1]: Configuration directory is org.mockito/mockito-core/4.8.1
[INFO] Executing: /home/linghengqian/.sdkman/candidates/java/21.0.1-graalce/bin/native-image -cp /home/linghengqian/TwinklingLiftWorks/git/public/boot-native/target/classes:/home/linghengqian/TwinklingLiftWorks/git/public/boot-native/target/test-classes:/home/linghengqian/.m2/repository/com/h2database/h2/2.1.214/h2-2.1.214.jar:/home/linghengqian/.m2/repository/com/zaxxer/HikariCP/5.0.1/HikariCP-5.0.1.jar:/home/linghengqian/.m2/repository/org/slf4j/slf4j-api/2.0.9/slf4j-api-2.0.9.jar:/home/linghengqian/.m2/repository/com/baomidou/dynamic-datasource-spring-boot3-starter/4.2.0/dynamic-datasource-spring-boot3-starter-4.2.0.jar:/home/linghengqian/.m2/repository/com/baomidou/dynamic-datasource-spring-boot-common/4.2.0/dynamic-datasource-spring-boot-common-4.2.0.jar:/home/linghengqian/.m2/repository/com/baomidou/dynamic-datasource-spring/4.2.0/dynamic-datasource-spring-4.2.0.jar:/home/linghengqian/.m2/repository/com/baomidou/dynamic-datasource-creator/4.2.0/dynamic-datasource-creator-4.2.0.jar:/home/linghengqian/.m2/repository/org/springframework/boot/spring-boot-starter-aop/3.1.4/spring-boot-starter-aop-3.1.4.jar:/home/linghengqian/.m2/repository/org/aspectj/aspectjweaver/1.9.20/aspectjweaver-1.9.20.jar:/home/linghengqian/.m2/repository/org/springframework/boot/spring-boot-starter-undertow/3.1.4/spring-boot-starter-undertow-3.1.4.jar:/home/linghengqian/.m2/repository/io/undertow/undertow-core/2.3.8.Final/undertow-core-2.3.8.Final.jar:/home/linghengqian/.m2/repository/org/jboss/logging/jboss-logging/3.5.3.Final/jboss-logging-3.5.3.Final.jar:/home/linghengqian/.m2/repository/org/jboss/xnio/xnio-api/3.8.8.Final/xnio-api-3.8.8.Final.jar:/home/linghengqian/.m2/repository/org/wildfly/common/wildfly-common/1.5.4.Final/wildfly-common-1.5.4.Final.jar:/home/linghengqian/.m2/repository/org/wildfly/client/wildfly-client-config/1.0.1.Final/wildfly-client-config-1.0.1.Final.jar:/home/linghengqian/.m2/repository/org/jboss/xnio/xnio-nio/3.8.8.Final/xnio-nio-3.8.8.Final.jar:/home/linghengqian/.m2/repository/org/jboss/threads/jboss-threads/3.5.0.Final/jboss-threads-3.5.0.Final.jar:/home/linghengqian/.m2/repository/io/undertow/undertow-servlet/2.3.8.Final/undertow-servlet-2.3.8.Final.jar:/home/linghengqian/.m2/repository/jakarta/servlet/jakarta.servlet-api/6.0.0/jakarta.servlet-api-6.0.0.jar:/home/linghengqian/.m2/repository/io/undertow/undertow-websockets-jsr/2.3.8.Final/undertow-websockets-jsr-2.3.8.Final.jar:/home/linghengqian/.m2/repository/jakarta/websocket/jakarta.websocket-api/2.1.1/jakarta.websocket-api-2.1.1.jar:/home/linghengqian/.m2/repository/jakarta/websocket/jakarta.websocket-client-api/2.1.1/jakarta.websocket-client-api-2.1.1.jar:/home/linghengqian/.m2/repository/org/apache/tomcat/embed/tomcat-embed-el/10.1.13/tomcat-embed-el-10.1.13.jar:/home/linghengqian/.m2/repository/com/baomidou/mybatis-plus-spring-boot3-starter/3.5.4.1/mybatis-plus-spring-boot3-starter-3.5.4.1.jar:/home/linghengqian/.m2/repository/com/baomidou/mybatis-plus/3.5.4.1/mybatis-plus-3.5.4.1.jar:/home/linghengqian/.m2/repository/com/baomidou/mybatis-plus-core/3.5.4.1/mybatis-plus-core-3.5.4.1.jar:/home/linghengqian/.m2/repository/com/baomidou/mybatis-plus-annotation/3.5.4.1/mybatis-plus-annotation-3.5.4.1.jar:/home/linghengqian/.m2/repository/com/baomidou/mybatis-plus-extension/3.5.4.1/mybatis-plus-extension-3.5.4.1.jar:/home/linghengqian/.m2/repository/org/mybatis/mybatis/3.5.13/mybatis-3.5.13.jar:/home/linghengqian/.m2/repository/com/github/jsqlparser/jsqlparser/4.6/jsqlparser-4.6.jar:/home/linghengqian/.m2/repository/org/mybatis/mybatis-spring/3.0.2/mybatis-spring-3.0.2.jar:/home/linghengqian/.m2/repository/com/baomidou/mybatis-plus-spring-boot-autoconfigure/3.5.4.1/mybatis-plus-spring-boot-autoconfigure-3.5.4.1.jar:/home/linghengqian/.m2/repository/org/springframework/boot/spring-boot-autoconfigure/3.1.4/spring-boot-autoconfigure-3.1.4.jar:/home/linghengqian/.m2/repository/org/springframework/boot/spring-boot/3.1.4/spring-boot-3.1.4.jar:/home/linghengqian/.m2/repository/org/springframework/boot/spring-boot-starter-jdbc/3.1.4/spring-boot-starter-jdbc-3.1.4.jar:/home/linghengqian/.m2/repository/org/springframework/spring-jdbc/6.0.12/spring-jdbc-6.0.12.jar:/home/linghengqian/.m2/repository/org/springframework/spring-tx/6.0.12/spring-tx-6.0.12.jar:/home/linghengqian/.m2/repository/org/springframework/boot/spring-boot-starter-web/3.1.4/spring-boot-starter-web-3.1.4.jar:/home/linghengqian/.m2/repository/org/springframework/boot/spring-boot-starter/3.1.4/spring-boot-starter-3.1.4.jar:/home/linghengqian/.m2/repository/org/springframework/boot/spring-boot-starter-logging/3.1.4/spring-boot-starter-logging-3.1.4.jar:/home/linghengqian/.m2/repository/ch/qos/logback/logback-classic/1.4.11/logback-classic-1.4.11.jar:/home/linghengqian/.m2/repository/ch/qos/logback/logback-core/1.4.11/logback-core-1.4.11.jar:/home/linghengqian/.m2/repository/org/apache/logging/log4j/log4j-to-slf4j/2.20.0/log4j-to-slf4j-2.20.0.jar:/home/linghengqian/.m2/repository/org/apache/logging/log4j/log4j-api/2.20.0/log4j-api-2.20.0.jar:/home/linghengqian/.m2/repository/org/slf4j/jul-to-slf4j/2.0.9/jul-to-slf4j-2.0.9.jar:/home/linghengqian/.m2/repository/jakarta/annotation/jakarta.annotation-api/2.1.1/jakarta.annotation-api-2.1.1.jar:/home/linghengqian/.m2/repository/org/yaml/snakeyaml/1.33/snakeyaml-1.33.jar:/home/linghengqian/.m2/repository/org/springframework/boot/spring-boot-starter-json/3.1.4/spring-boot-starter-json-3.1.4.jar:/home/linghengqian/.m2/repository/com/fasterxml/jackson/core/jackson-databind/2.15.2/jackson-databind-2.15.2.jar:/home/linghengqian/.m2/repository/com/fasterxml/jackson/core/jackson-annotations/2.15.2/jackson-annotations-2.15.2.jar:/home/linghengqian/.m2/repository/com/fasterxml/jackson/core/jackson-core/2.15.2/jackson-core-2.15.2.jar:/home/linghengqian/.m2/repository/com/fasterxml/jackson/datatype/jackson-datatype-jdk8/2.15.2/jackson-datatype-jdk8-2.15.2.jar:/home/linghengqian/.m2/repository/com/fasterxml/jackson/datatype/jackson-datatype-jsr310/2.15.2/jackson-datatype-jsr310-2.15.2.jar:/home/linghengqian/.m2/repository/com/fasterxml/jackson/module/jackson-module-parameter-names/2.15.2/jackson-module-parameter-names-2.15.2.jar:/home/linghengqian/.m2/repository/org/springframework/boot/spring-boot-starter-tomcat/3.1.4/spring-boot-starter-tomcat-3.1.4.jar:/home/linghengqian/.m2/repository/org/apache/tomcat/embed/tomcat-embed-core/10.1.13/tomcat-embed-core-10.1.13.jar:/home/linghengqian/.m2/repository/org/apache/tomcat/embed/tomcat-embed-websocket/10.1.13/tomcat-embed-websocket-10.1.13.jar:/home/linghengqian/.m2/repository/org/springframework/spring-web/6.0.12/spring-web-6.0.12.jar:/home/linghengqian/.m2/repository/org/springframework/spring-beans/6.0.12/spring-beans-6.0.12.jar:/home/linghengqian/.m2/repository/io/micrometer/micrometer-observation/1.11.4/micrometer-observation-1.11.4.jar:/home/linghengqian/.m2/repository/io/micrometer/micrometer-commons/1.11.4/micrometer-commons-1.11.4.jar:/home/linghengqian/.m2/repository/org/springframework/spring-webmvc/6.0.12/spring-webmvc-6.0.12.jar:/home/linghengqian/.m2/repository/org/springframework/spring-aop/6.0.12/spring-aop-6.0.12.jar:/home/linghengqian/.m2/repository/org/springframework/spring-context/6.0.12/spring-context-6.0.12.jar:/home/linghengqian/.m2/repository/org/springframework/spring-expression/6.0.12/spring-expression-6.0.12.jar:/home/linghengqian/.m2/repository/org/springframework/boot/spring-boot-starter-test/3.1.4/spring-boot-starter-test-3.1.4.jar:/home/linghengqian/.m2/repository/org/springframework/boot/spring-boot-test/3.1.4/spring-boot-test-3.1.4.jar:/home/linghengqian/.m2/repository/org/springframework/boot/spring-boot-test-autoconfigure/3.1.4/spring-boot-test-autoconfigure-3.1.4.jar:/home/linghengqian/.m2/repository/com/jayway/jsonpath/json-path/2.8.0/json-path-2.8.0.jar:/home/linghengqian/.m2/repository/jakarta/xml/bind/jakarta.xml.bind-api/4.0.1/jakarta.xml.bind-api-4.0.1.jar:/home/linghengqian/.m2/repository/jakarta/activation/jakarta.activation-api/2.1.2/jakarta.activation-api-2.1.2.jar:/home/linghengqian/.m2/repository/net/minidev/json-smart/2.4.11/json-smart-2.4.11.jar:/home/linghengqian/.m2/repository/net/minidev/accessors-smart/2.4.11/accessors-smart-2.4.11.jar:/home/linghengqian/.m2/repository/org/ow2/asm/asm/9.3/asm-9.3.jar:/home/linghengqian/.m2/repository/org/assertj/assertj-core/3.24.2/assertj-core-3.24.2.jar:/home/linghengqian/.m2/repository/net/bytebuddy/byte-buddy/1.14.8/byte-buddy-1.14.8.jar:/home/linghengqian/.m2/repository/org/hamcrest/hamcrest/2.2/hamcrest-2.2.jar:/home/linghengqian/.m2/repository/org/junit/jupiter/junit-jupiter/5.9.3/junit-jupiter-5.9.3.jar:/home/linghengqian/.m2/repository/org/junit/jupiter/junit-jupiter-api/5.9.3/junit-jupiter-api-5.9.3.jar:/home/linghengqian/.m2/repository/org/junit/jupiter/junit-jupiter-params/5.9.3/junit-jupiter-params-5.9.3.jar:/home/linghengqian/.m2/repository/org/junit/jupiter/junit-jupiter-engine/5.9.3/junit-jupiter-engine-5.9.3.jar:/home/linghengqian/.m2/repository/org/mockito/mockito-core/5.3.1/mockito-core-5.3.1.jar:/home/linghengqian/.m2/repository/net/bytebuddy/byte-buddy-agent/1.14.8/byte-buddy-agent-1.14.8.jar:/home/linghengqian/.m2/repository/org/objenesis/objenesis/3.3/objenesis-3.3.jar:/home/linghengqian/.m2/repository/org/mockito/mockito-junit-jupiter/5.3.1/mockito-junit-jupiter-5.3.1.jar:/home/linghengqian/.m2/repository/org/skyscreamer/jsonassert/1.5.1/jsonassert-1.5.1.jar:/home/linghengqian/.m2/repository/com/vaadin/external/google/android-json/0.0.20131108.vaadin1/android-json-0.0.20131108.vaadin1.jar:/home/linghengqian/.m2/repository/org/springframework/spring-core/6.0.12/spring-core-6.0.12.jar:/home/linghengqian/.m2/repository/org/springframework/spring-jcl/6.0.12/spring-jcl-6.0.12.jar:/home/linghengqian/.m2/repository/org/springframework/spring-test/6.0.12/spring-test-6.0.12.jar:/home/linghengqian/.m2/repository/org/xmlunit/xmlunit-core/2.9.1/xmlunit-core-2.9.1.jar:/home/linghengqian/.m2/repository/org/junit/platform/junit-platform-launcher/1.9.3/junit-platform-launcher-1.9.3.jar:/home/linghengqian/.m2/repository/org/junit/platform/junit-platform-engine/1.9.3/junit-platform-engine-1.9.3.jar:/home/linghengqian/.m2/repository/org/opentest4j/opentest4j/1.2.0/opentest4j-1.2.0.jar:/home/linghengqian/.m2/repository/org/junit/platform/junit-platform-commons/1.9.3/junit-platform-commons-1.9.3.jar:/home/linghengqian/.m2/repository/org/apiguardian/apiguardian-api/1.1.2/apiguardian-api-1.1.2.jar:/home/linghengqian/.m2/repository/org/graalvm/buildtools/native-maven-plugin/0.9.27/native-maven-plugin-0.9.27.jar:/home/linghengqian/.m2/repository/org/graalvm/buildtools/junit-platform-native/0.9.27/junit-platform-native-0.9.27.jar:/home/linghengqian/.m2/repository/org/junit/platform/junit-platform-console/1.9.3/junit-platform-console-1.9.3.jar:/home/linghengqian/.m2/repository/org/junit/platform/junit-platform-reporting/1.9.3/junit-platform-reporting-1.9.3.jar:/home/linghengqian/.m2/repository/org/junit/platform/junit-platform-launcher/1.9.3/junit-platform-launcher-1.9.3.jar:/home/linghengqian/.m2/repository/org/junit/platform/junit-platform-engine/1.9.3/junit-platform-engine-1.9.3.jar:/home/linghengqian/.m2/repository/org/junit/platform/junit-platform-commons/1.9.3/junit-platform-commons-1.9.3.jar:/home/linghengqian/.m2/repository/org/junit/jupiter/junit-jupiter/5.10.0/junit-jupiter-5.10.0.jar:/home/linghengqian/.m2/repository/org/junit/jupiter/junit-jupiter-api/5.10.0/junit-jupiter-api-5.10.0.jar:/home/linghengqian/.m2/repository/org/junit/jupiter/junit-jupiter-params/5.10.0/junit-jupiter-params-5.10.0.jar:/home/linghengqian/.m2/repository/org/junit/jupiter/junit-jupiter-engine/5.10.0/junit-jupiter-engine-5.10.0.jar:/home/linghengqian/.m2/repository/org/graalvm/buildtools/utils/0.9.27/utils-0.9.27.jar:/home/linghengqian/.m2/repository/org/graalvm/buildtools/graalvm-reachability-metadata/0.9.27/graalvm-reachability-metadata-0.9.27.jar:/home/linghengqian/.m2/repository/org/graalvm/buildtools/junit-platform-native/0.9.27/junit-platform-native-0.9.27.jar --no-fallback -o /home/linghengqian/TwinklingLiftWorks/git/public/boot-native/target/native-tests -Djunit.platform.listeners.uid.tracking.output.dir=/home/linghengqian/TwinklingLiftWorks/git/public/boot-native/target/test-ids -H:ConfigurationFileDirectories=/home/linghengqian/TwinklingLiftWorks/git/public/boot-native/target/graalvm-reachability-metadata/15733192e0f6e369451cde2afd11b12ca027fde5/org.jboss.logging/jboss-logging/3.5.0.Final,/home/linghengqian/TwinklingLiftWorks/git/public/boot-native/target/graalvm-reachability-metadata/15733192e0f6e369451cde2afd11b12ca027fde5/com.fasterxml.jackson.core/jackson-databind/2.15.2,/home/linghengqian/TwinklingLiftWorks/git/public/boot-native/target/graalvm-reachability-metadata/15733192e0f6e369451cde2afd11b12ca027fde5/org.apache.tomcat.embed/tomcat-embed-core/10.0.20,/home/linghengqian/TwinklingLiftWorks/git/public/boot-native/target/graalvm-reachability-metadata/15733192e0f6e369451cde2afd11b12ca027fde5/ch.qos.logback/logback-classic/1.4.1,/home/linghengqian/TwinklingLiftWorks/git/public/boot-native/target/graalvm-reachability-metadata/15733192e0f6e369451cde2afd11b12ca027fde5/com.zaxxer/HikariCP/5.0.1,/home/linghengqian/TwinklingLiftWorks/git/public/boot-native/target/graalvm-reachability-metadata/15733192e0f6e369451cde2afd11b12ca027fde5/org.mockito/mockito-core/4.8.1,/home/linghengqian/TwinklingLiftWorks/git/public/boot-native/target/graalvm-reachability-metadata/15733192e0f6e369451cde2afd11b12ca027fde5/com.h2database/h2/2.1.210,/home/linghengqian/TwinklingLiftWorks/git/public/boot-native/target/graalvm-reachability-metadata/15733192e0f6e369451cde2afd11b12ca027fde5/io.undertow/undertow-core/2.2.19.Final,/home/linghengqian/TwinklingLiftWorks/git/public/boot-native/target/graalvm-reachability-metadata/15733192e0f6e369451cde2afd11b12ca027fde5/jakarta.servlet/jakarta.servlet-api/5.0.0 --features=org.graalvm.junit.platform.JUnitPlatformFeature org.graalvm.junit.platform.NativeImageJUnitLauncher
Warning: The option '-H:ResourceConfigurationResources=META-INF/native-image/org.apache.tomcat.embed/tomcat-embed-core/tomcat-resource.json' is experimental and must be enabled via '-H:+UnlockExperimentalVMOptions' in the future.
Warning: The option '-H:ReflectionConfigurationResources=META-INF/native-image/org.apache.tomcat.embed/tomcat-embed-core/tomcat-reflection.json' is experimental and must be enabled via '-H:+UnlockExperimentalVMOptions' in the future.
Warning: The option '-H:ReflectionConfigurationResources=META-INF/native-image/org.apache.tomcat.embed/tomcat-embed-websocket/tomcat-reflection.json' is experimental and must be enabled via '-H:+UnlockExperimentalVMOptions' in the future.
Warning: The option '-H:ReflectionConfigurationResources=META-INF/native-image/org.apache.tomcat.embed/tomcat-embed-el/tomcat-reflection.json' is experimental and must be enabled via '-H:+UnlockExperimentalVMOptions' in the future.
Warning: The option '-H:ResourceConfigurationResources=META-INF/native-image/org.apache.tomcat.embed/tomcat-embed-el/tomcat-resource.json' is experimental and must be enabled via '-H:+UnlockExperimentalVMOptions' in the future.
Warning: The option '-H:ResourceConfigurationResources=META-INF/native-image/org.apache.tomcat.embed/tomcat-embed-websocket/tomcat-resource.json' is experimental and must be enabled via '-H:+UnlockExperimentalVMOptions' in the future.
Warning: Please re-evaluate whether any experimental option is required, and either remove or unlock it. The build output lists all active experimental options, including where they come from and possible alternatives. If you think an experimental option should be considered as stable, please file an issue.
========================================================================================================================
GraalVM Native Image: Generating 'native-tests' (executable)...
========================================================================================================================
[1/8] Initializing...                                                                                   (15.0s @ 0.18GB)
 Java version: 21.0.1+12, vendor version: GraalVM CE 21.0.1+12.1
 Graal compiler: optimization level: 2, target machine: x86-64-v3
 C compiler: gcc (linux, x86_64, 11.4.0)
 Garbage collector: Serial GC (max heap size: 80% of RAM)
 3 user-specific feature(s):
 - com.oracle.svm.thirdparty.gson.GsonFeature
 - org.graalvm.junit.platform.JUnitPlatformFeature
 - org.springframework.aot.nativex.feature.PreComputeFieldFeature
------------------------------------------------------------------------------------------------------------------------
 2 experimental option(s) unlocked:
 - '-H:ResourceConfigurationResources' (origin(s): 'META-INF/native-image/org.apache.tomcat.embed/tomcat-embed-el/native-image.properties' in 'file:///home/linghengqian/.m2/repository/org/apache/tomcat/embed/tomcat-embed-el/10.1.13/tomcat-embed-el-10.1.13.jar', 'META-INF/native-image/org.apache.tomcat.embed/tomcat-embed-core/native-image.properties' in 'file:///home/linghengqian/.m2/repository/org/apache/tomcat/embed/tomcat-embed-core/10.1.13/tomcat-embed-core-10.1.13.jar', 'META-INF/native-image/org.apache.tomcat.embed/tomcat-embed-websocket/native-image.properties' in 'file:///home/linghengqian/.m2/repository/org/apache/tomcat/embed/tomcat-embed-websocket/10.1.13/tomcat-embed-websocket-10.1.13.jar')
 - '-H:ReflectionConfigurationResources' (origin(s): 'META-INF/native-image/org.apache.tomcat.embed/tomcat-embed-el/native-image.properties' in 'file:///home/linghengqian/.m2/repository/org/apache/tomcat/embed/tomcat-embed-el/10.1.13/tomcat-embed-el-10.1.13.jar', 'META-INF/native-image/org.apache.tomcat.embed/tomcat-embed-core/native-image.properties' in 'file:///home/linghengqian/.m2/repository/org/apache/tomcat/embed/tomcat-embed-core/10.1.13/tomcat-embed-core-10.1.13.jar', 'META-INF/native-image/org.apache.tomcat.embed/tomcat-embed-websocket/native-image.properties' in 'file:///home/linghengqian/.m2/repository/org/apache/tomcat/embed/tomcat-embed-websocket/10.1.13/tomcat-embed-websocket-10.1.13.jar')
------------------------------------------------------------------------------------------------------------------------
Build resources:
 - 9.57GB of memory (75.6% of 12.67GB system memory, determined at start)
 - 6 thread(s) (100.0% of 6 available processor(s), determined at start)
[junit-platform-native] Running in 'test listener' mode using files matching pattern [junit-platform-unique-ids*] found in folder [/home/linghengqian/TwinklingLiftWorks/git/public/boot-native/target/test-ids] and its subfolders.
Field org.apache.commons.logging.LogAdapter#log4jSpiPresent set to true at build time
Field org.apache.commons.logging.LogAdapter#log4jSlf4jProviderPresent set to true at build time
Field org.apache.commons.logging.LogAdapter#slf4jSpiPresent set to true at build time
Field org.apache.commons.logging.LogAdapter#slf4jApiPresent set to true at build time
Field org.springframework.boot.logging.log4j2.Log4J2LoggingSystem$Factory#PRESENT set to false at build time
Field org.springframework.core.NativeDetector#inNativeImage set to true at build time
Field org.springframework.cglib.core.AbstractClassGenerator#inNativeImage set to true at build time
Field org.springframework.boot.logging.logback.LogbackLoggingSystem$Factory#PRESENT set to true at build time
Field org.springframework.transaction.annotation.AnnotationTransactionAttributeSource#jta12Present set to false at build time
Field org.springframework.transaction.annotation.AnnotationTransactionAttributeSource#ejb3Present set to false at build time
Field org.springframework.core.KotlinDetector#kotlinPresent set to false at build time
Field org.springframework.core.KotlinDetector#kotlinReflectPresent set to false at build time
Field org.springframework.aot.AotDetector#inNativeImage set to true at build time
Field org.springframework.boot.test.mock.mockito.ResetMocksTestExecutionListener#MOCKITO_IS_PRESENT set to true at build time
Field org.springframework.boot.test.autoconfigure.webservices.client.MockWebServiceServerTestExecutionListener#MOCK_SERVER_PRESENT set to false at build time
Field org.springframework.boot.test.autoconfigure.restdocs.RestDocsTestExecutionListener#REST_DOCS_PRESENT set to false at build time
Field org.springframework.web.servlet.view.InternalResourceViewResolver#jstlPresent set to false at build time
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
Field org.springframework.test.context.web.socket.MockServerContainerContextCustomizerFactory#webSocketPresent set to true at build time
Field org.springframework.http.converter.json.Jackson2ObjectMapperBuilder#jackson2XmlPresent set to false at build time
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
Field org.springframework.boot.test.web.reactive.server.WebTestClientContextCustomizerFactory#webClientPresent set to false at build time
Field org.springframework.boot.logging.java.JavaLoggingSystem$Factory#PRESENT set to true at build time
Field org.springframework.transaction.interceptor.TransactionAspectSupport#vavrPresent set to false at build time
Field org.springframework.transaction.interceptor.TransactionAspectSupport#reactiveStreamsPresent set to false at build time
Field org.springframework.boot.autoconfigure.web.format.WebConversionService#JSR_354_PRESENT set to false at build time
Field org.springframework.format.support.DefaultFormattingConversionService#jsr354Present set to false at build time
Field org.springframework.web.context.request.RequestContextHolder#jsfPresent set to false at build time
Field org.springframework.web.context.support.StandardServletEnvironment#jndiPresent set to true at build time
Field org.springframework.web.context.support.WebApplicationContextUtils#jsfPresent set to false at build time
Field org.springframework.boot.logging.logback.LogbackLoggingSystemProperties#JBOSS_LOGGING_PRESENT set to true at build time
Field org.springframework.jdbc.support.SQLErrorCodeSQLExceptionTranslator#userProvidedErrorCodesFilePresent set to false at build time
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
Field org.springframework.web.servlet.support.RequestContext#jstlPresent set to false at build time
Field org.springframework.core.ReactiveAdapterRegistry#reactorPresent set to false at build time
Field org.springframework.core.ReactiveAdapterRegistry#rxjava3Present set to false at build time
Field org.springframework.core.ReactiveAdapterRegistry#kotlinCoroutinesPresent set to false at build time
Field org.springframework.core.ReactiveAdapterRegistry#mutinyPresent set to false at build time
SLF4J: No SLF4J providers were found.
SLF4J: Defaulting to no-operation (NOP) logger implementation
SLF4J: See https://www.slf4j.org/codes.html#noProviders for further details.
Field org.springframework.web.servlet.mvc.method.annotation.ReactiveTypeHandler#isContextPropagationPresent set to false at build time
[2/8] Performing analysis...  [******]                                                                  (97.1s @ 2.53GB)
   23,927 reachable types   (90.7% of   26,388 total)
   38,266 reachable fields  (65.0% of   58,829 total)
  120,852 reachable methods (63.9% of  189,269 total)
    7,285 types,   840 fields, and 9,777 methods registered for reflection
       67 types,    65 fields, and    57 methods registered for JNI access
        4 native libraries: dl, pthread, rt, z
[3/8] Building universe...                                                                              (13.7s @ 2.20GB)
[4/8] Parsing methods...      [[4/8] Parsing methods...      [***]                                                                      (7.0s @ 3.47GB)
[5/8] Inlining methods...     [***]                                                                      (3.9s @ 3.16GB)
[6/8] Compiling methods...    [[6/8] Compiling methods...    [********]                                                                (69.4s @ 3.41GB)
[7/8] Layouting methods...    [***]                                                                     (11.3s @ 2.29GB)
[8/8] Creating image...       [****]                                                                    (16.1s @ 3.26GB)
  59.59MB (50.55%) for code area:    79,830 compilation units
  53.98MB (45.79%) for image heap:  534,051 objects and 348 resources
   4.32MB ( 3.66%) for other data
 117.89MB in total
------------------------------------------------------------------------------------------------------------------------
Top 10 origins of code area:                                Top 10 object types in image heap:
  15.53MB java.base                                           18.29MB byte[] for code metadata
   6.08MB h2-2.1.214.jar                                       7.74MB byte[] for java.lang.String
   4.33MB java.xml                                             5.77MB java.lang.Class
   4.27MB tomcat-embed-core-10.1.13.jar                        5.21MB java.lang.String
   2.04MB jackson-databind-2.15.2.jar                          2.06MB byte[] for embedded resources
   1.71MB svm.jar (Native Image)                               2.01MB com.oracle.svm.core.hub.DynamicHubCompanion
   1.69MB spring-core-6.0.12.jar                               1.58MB byte[] for reflection metadata
   1.62MB jsqlparser-4.6.jar                                   1.06MB java.lang.String[]
   1.54MB mybatis-3.5.13.jar                                 909.83kB byte[] for general heap data
   1.47MB aspectjweaver-1.9.20.jar                           858.28kB c.o.svm.core.hub.DynamicHub$ReflectionMetadata
  18.74MB for 130 more packages                                8.53MB for 4686 more object types
------------------------------------------------------------------------------------------------------------------------
Recommendations:
 INIT: Adopt '--strict-image-heap' to prepare for the next GraalVM release.
 HEAP: Set max heap for improved and more predictable memory usage.
 CPU:  Enable more CPU features with '-march=native' for improved performance.
------------------------------------------------------------------------------------------------------------------------
                       27.4s (11.6% of total time) in 193 GCs | Peak RSS: 6.60GB | CPU load: 4.67
------------------------------------------------------------------------------------------------------------------------
Produced artifacts:
 /home/linghengqian/TwinklingLiftWorks/git/public/boot-native/target/native-tests (executable)
========================================================================================================================
Finished generating 'native-tests' in 3m 55s.
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

2023-11-28T20:42:32.384+08:00  INFO 13785 --- [           main] c.e.b.BootNativeApplicationTests         : Starting AOT-processed BootNativeApplicationTests using Java 21.0.1 with PID 13785 (started by linghengqian in /home/linghengqian/TwinklingLiftWorks/git/public/boot-native)
2023-11-28T20:42:32.385+08:00  INFO 13785 --- [           main] c.e.b.BootNativeApplicationTests         : No active profile set, falling back to 1 default profile: "default"
2023-11-28T20:42:32.397+08:00  INFO 13785 --- [           main] trationDelegate$BeanPostProcessorChecker : Bean 'spring.datasource.dynamic-com.baomidou.dynamic.datasource.spring.boot.autoconfigure.DynamicDataSourceProperties' of type [com.baomidou.dynamic.datasource.spring.boot.autoconfigure.DynamicDataSourceProperties] is not eligible for getting processed by all BeanPostProcessors (for example: not eligible for auto-proxying)
2023-11-28T20:42:32.398+08:00  INFO 13785 --- [           main] trationDelegate$BeanPostProcessorChecker : Bean 'com.baomidou.dynamic.datasource.spring.boot.autoconfigure.DynamicDataSourceAopConfiguration' of type [com.baomidou.dynamic.datasource.spring.boot.autoconfigure.DynamicDataSourceAopConfiguration$$SpringCGLIB$$0] is not eligible for getting processed by all BeanPostProcessors (for example: not eligible for auto-proxying)
2023-11-28T20:42:32.398+08:00  INFO 13785 --- [           main] trationDelegate$BeanPostProcessorChecker : Bean 'dsProcessor' of type [com.baomidou.dynamic.datasource.processor.DsJakartaHeaderProcessor] is not eligible for getting processed by all BeanPostProcessors (for example: not eligible for auto-proxying)
2023-11-28T20:42:32.406+08:00  INFO 13785 --- [           main] c.b.d.d.DynamicRoutingDataSource         : dynamic-datasource - add a datasource named [master] success
2023-11-28T20:42:32.406+08:00  INFO 13785 --- [           main] c.b.d.d.DynamicRoutingDataSource         : dynamic-datasource initial loaded [1] datasource,primary datasource named [master]
2023-11-28T20:42:32.413+08:00  INFO 13785 --- [           main] com.zaxxer.hikari.HikariDataSource       : master - Starting...
2023-11-28T20:42:32.419+08:00  INFO 13785 --- [           main] com.zaxxer.hikari.pool.HikariPool        : master - Added connection conn0: url=jdbc:h2:mem:test user=SA
2023-11-28T20:42:32.419+08:00  INFO 13785 --- [           main] com.zaxxer.hikari.HikariDataSource       : master - Start completed.
 _ _   |_  _ _|_. ___ _ |    _ 
| | |\/|_)(_| | |_\  |_)||_|_\ 
     /               |         
                        3.5.4.1 
2023-11-28T20:42:32.552+08:00  INFO 13785 --- [           main] c.e.b.BootNativeApplicationTests         : Started BootNativeApplicationTests in 0.21 seconds (process running for 0.247)
Message[id=1, message=Hello World on run!]
Message[id=2, message=Hello World! on runWithXmlMapper]
------------演示insert-----------------
2023-11-28T20:42:32.553+08:00  INFO 13785 --- [           main] c.e.bootnative.MyMetaObjectHandler       : 进入insertFill填充了
------------演示select-----------------
simple query:Messages{id=3, message='Hello MybatisPlus', messageType=VOICE}
query wrapper:Messages{id=1, message='Hello World on run!', messageType=null}
------------演示update-----------------
2023-11-28T20:42:32.557+08:00  INFO 13785 --- [           main] c.e.bootnative.MyMetaObjectHandler       : 进入updateFill填充了
2023-11-28T20:42:32.557+08:00  INFO 13785 --- [           main] c.e.bootnative.MyMetaObjectHandler       : 进入updateFill填充了
------------演示delete-----------------
------------演示page-----------------
total:2,records[Messages{id=1, message='Hello MybatisPlus', messageType=TEXT}, Messages{id=2, message='Hello World! on runWithXmlMapper', messageType=null}]
------------演示lambda-----------------
lambda query:null
2023-11-28T20:42:32.567+08:00  INFO 13785 --- [           main] c.e.bootnative.MyMetaObjectHandler       : 进入updateFill填充了
lambda update:1
lambda delete:1
test
com.example.bootnative.BootNativeApplicationTests > contextLoads() SUCCESSFUL


Test run finished after 254 ms
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
[         1 tests successful      ]
[         0 tests failed          ]

2023-11-28T20:42:32.570+08:00  INFO 13785 --- [extShutdownHook] c.b.d.d.DynamicRoutingDataSource         : dynamic-datasource start closing ....
2023-11-28T20:42:32.580+08:00  INFO 13785 --- [extShutdownHook] com.zaxxer.hikari.HikariDataSource       : master - Shutdown initiated...
2023-11-28T20:42:32.582+08:00  INFO 13785 --- [extShutdownHook] com.zaxxer.hikari.HikariDataSource       : master - Shutdown completed.
2023-11-28T20:42:32.582+08:00  INFO 13785 --- [extShutdownHook] c.b.d.d.d.DefaultDataSourceDestroyer     : dynamic-datasource close the datasource named [master] success,
2023-11-28T20:42:32.582+08:00  INFO 13785 --- [extShutdownHook] c.b.d.d.DynamicRoutingDataSource         : dynamic-datasource all closed success,bye
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  08:02 min (Wall Clock)
[INFO] Finished at: 2023-11-28T20:42:32+08:00
[INFO] ------------------------------------------------------------------------

```
