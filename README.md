# tool-requestId

使用Filter,给所有请求头和响应头添加X-Afmobi-RequestId。调用方没传时，默认生成。此RequestId方便查日志定位问题。

# Quick start
1.添加tool的github的repository
```xml
<repositories>
    <repository>
        <id>tool-maven-repository</id>
        <url>https://raw.github.com/afmobi-QSee/tool-maven-repository/master/releases</url>
    </repository>
</repositories>
```

2.添加依赖
```xml
<dependency>
    <groupId>com.tool</groupId>
    <artifactId>tool-requestId</artifactId>
    <version>0.0.1</version>
</dependency>
```

2.springboot添加扫描包
```java
@ServletComponentScan(basePackages={"com.tool"})
```

3.logback使用[RequestId: %X{X-Afmobi-RequestId}]获取RequestId
```xml
<appender name="CONSOLE" class="ch.qos.logback.core.ConsoleAppender">
    <encoder>
        <pattern>%d{yyyy-MM-dd HH:mm:ss.SSS} [RequestId: %X{X-Afmobi-RequestId}] %logger{50} - %msg%n</pattern>
    </encoder>
</appender>
```
