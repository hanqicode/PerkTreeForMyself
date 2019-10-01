# Slf4j Log Framework
Link: https://www.slf4j.org/

## Introduction
It's a log framework which provide an **interface** for user, but user needs to choose and bind the concrete implementation.

## How to Use
If you have **Lombok** library, you can specify to use with the annotation:

```java
@Slf4j
public class LogDemo {

    public static void main(String[] args) {
        log.debug("This is debug level log.");
        log.info("This is info level log.");
    }
}
```

Here, we use **Log4J** as implementation.
We need to write an XML file or a property file to claim the configurations, like log file name, path, level, etc.

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<!DOCTYPE log4j:configuration SYSTEM "log4j.dtd">
<log4j:configuration debug="true"
                     xmlns:log4j='http://jakarta.apache.org/log4j/'>

    <appender name="file" class="org.apache.log4j.RollingFileAppender">
        <param name="append" value="false" />
        <param name="maxFileSize" value="10MB" />
        <param name="maxBackupIndex" value="5" />
        <!-- For Tomcat -->
        <param name="file" value="D:\\Documents\\JavaWorkspace\\Logs\\application.log" />
        <layout class="org.apache.log4j.PatternLayout">
            <param name="ConversionPattern"
                   value="%d{yyyy-MM-dd HH:mm:ss} %-5p %c{1}:%L - %m%n" />
        </layout>
    </appender>

    <root>
        <level value="INFO" />
        <appender-ref ref="file" />
    </root>

</log4j:configuration>
```

Note here, the file path is for Windows OS. It is different from Linux/Mac.

The infomation in log file:

```
2019-09-30 21:56:23 INFO  LogDemo:10 - This is info level log.
```
