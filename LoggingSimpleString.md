If you already have java classes you want to log, you may want to send just a string using http without changing your code to use specifig HttpMessage class.

You can to this by simply use specific _UnhandledMessage_ key in you layout conversion pattern.

Add something like this as conversion pattern in your log4j.propertie file
```
log4j.appender.AppenderUnHandled.layout.conversionPattern = ?txt=%UnhandledMessage
```



And a simple

```java

//send message via httpAppender
log.debug("my message");
```

will be send to http://....?txt=my%20message
