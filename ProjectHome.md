**A http appender for logging event with log4j**

Just a little appender to send http message using log4j mecanism.

In your code, just use a HttpMessage object
```java

//Create a new message
HttpMessage message = new HttpMessage ();
message.addParameter(id, "1");
message.addParameter(uid, "sebastien");
message.addParameter(evt, "just a test");

//send message via httpAppender
log.debug(message);
```

and configure your log4j.properties

```
log4j.category.fr.bettinger = DEBUG, AppenderStat
log4j.appender.AppenderStat=fr.bettinger.log4j.HttpAppender
log4j.appender.AppenderStat.LogURL=http://where.to.send
log4j.appender.AppenderStat.layout = fr.bettinger.log4j.HttpLayout
log4j.appender.AppenderStat.layout.conversionPattern = ?param=%id&usr=%uid&evt=%evt
```

And that's it !