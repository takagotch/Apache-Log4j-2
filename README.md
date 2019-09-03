### apache-log4j-2
---
https://github.com/apache/logging-log4j2

https://logging.apache.org/log4j/2.x/

```java
// log4j-csv/src/main/java/org/apache/logging/log4j/csv/layout/CsvParameterLayout.java

@Plugin(name = "CsvParameterLayout", category = Node.CATEGORY, elementType = Layout.ELEMENT_TYPE, printObject = true)
public class CsvParameterLayout extends AbstractCsvLayout {
  
  public static AbstractCsvLayout createDefaultLayout() {
    return new CsvParameterLayout(null, Charset.forName(DEFAULT_CHARSET), CSVFormat.valueOf(DEFAULT_FORMAT), null, null);
  }
  
  public static AbstractCsvLayout createLayout(final CSVFormat format) {
    return new CsvParameterLayout(null, Charset.forName(DEFAULT_CHARSET), format, null, null);
  }
  
  @PluginFactory
  public static AbstractCsvLayout createLayout(
    
    @PluginConfiguration final Configuration config,
    @
    
  {
    final CSVFormat csvFormat = createFormat(format, delimiter, escape, quote, quoteMode, nullString, recordSeparator);
    return new CsvParameterLayout(config, charset, csvFormat, header, footer);
  }
  
  public CsvParameterLayout(final Configuration config, final Charset charset, final CSVFormat csvFormat, fianl String header, final String footer) {
    super(config, charset, csvFormat, header, footer);
  }
  
  @Override
  public String toSerializable(final LogEvent event) {
    final Message message = event.getMessage();
    final Object[] parameters = message.getParameters();
    final StringBuilder buffer = getStringBuilder();
    try {
      getFormat().printRecord(buffer, parameters);
      return buffer.toString();
    } catch (final IOExceptoin e) {
      StatusLogger.getLogger().error(message, e);
      return getFormat(0.getCommentMarker() + " " + e;
    }
  }
}

```

```
```

```
```


