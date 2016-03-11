#Formatting guide:

##Markdown

*Github formatting*

https://help.github.com/articles/basic-writing-and-formatting-syntax/

*Stackoverflow formatting*

http://stackoverflow.com/editing-help

*Stackoverflow comments formatting*

http://stackoverflow.com/editing-help#comment-formatting


##Doc Comments for Javadocs:

http://www.oracle.com/technetwork/java/javase/documentation/index-137868.html
Example:
```java
  /**
     * Returns the value mapped by {@code name} if it exists and is a long or
     * can be coerced to a long, or {@code fallback} otherwise. Note that JSON represents
     * numbers as doubles, so this is <a href="#lossy">lossy</a>; use strings to transfer
     * numbers via JSON.
     */
    public long optLong(String name, long fallback) {
        Object object = opt(name);
        Long result = JSON.toLong(object);
        return result != null ? result : fallback;
    }

    /**
     * Returns the value mapped by {@code name} if it exists, coercing it if
     * necessary, or throws if no such mapping exists.
     *
     * @throws JSONException if no such mapping exists.
     */
    public String getString(String name) throws JSONException {
        Object object = get(name);
        String result = JSON.toString(object);
        if (result == null) {
            throw JSON.typeMismatch(name, object, "String");
        }
        return result;
    }
```
