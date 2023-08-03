---
description: >-
  Solr is a blazing-fast, open source enterprise search platform built on Apache
  Lucene.
---

# ☀ Apache Solr

## Common Issues

### Query Parser Choice

Solr supports multiple query parsers. Which one to chose depends on the use case.

* **Lucene Query Parser**
  * default parser with good results out of the box, more strict and harder to configure
* **eDisMax Query Parser (Extended DisMax Query Parser)**
  * more lenient syntax, better configurability then Lucene, less ideal results out of the box
  * supports boosting with multiplication instead of addition&#x20;

see also: [https://medium.com/empathyco/edismax-query-parser-a-parser-to-be-going-mad-for-3cb353292a30](https://medium.com/empathyco/edismax-query-parser-a-parser-to-be-going-mad-for-3cb353292a30)

### Sorting

When sorting search results alphabetically it's important to use a field that contains the full string without any indexing. Sorting indexed fields can result in an unexpected order depending on the filter functions that are used to tokenise the field.

An easy fix is to setup a dedicated field for sorting. E.g.

```xml
<field name="YOURFIELD_sort" type="sort_text" indexed="true" stored="true" multiValued="false" default=""/>

<!-- This is an example of using the KeywordTokenizer along With various TokenFilterFactories to produce a sortable field
        that does not include some properties of the source text -->
<fieldType name="sort_text" class="solr.TextField" sortMissingLast="true" omitNorms="true">
    <analyzer>
        <charFilter class="solr.MappingCharFilterFactory" mapping="mapping-ISOLatin1Accent.txt"/>
        <!-- KeywordTokenizer does no actual tokenizing, so the entire input string is preserved as a single token -->
        <tokenizer class="solr.KeywordTokenizerFactory"/>
        <!-- The LowerCase TokenFilter does what you expect, which can be when you want your sorting to be case insensitive -->
        <filter class="solr.LowerCaseFilterFactory"/>
        <!-- The TrimFilter removes any leading or trailing whitespace -->
        <filter class="solr.TrimFilterFactory"/>
        <!-- The PatternReplaceFilter gives you the flexibility to use Java Regular expression to replace any sequence of characters
            matching a pattern with an arbitrary replacement string, which may include back references to portions of the original string
            matched by the pattern. See the Java Regular Expression documentation for more information on pattern and replacement string
            syntax. http://java.sun.com/j2se/1.5.0/docs/api/java/util/regex/package-summary.html -->
        <filter class="solr.PatternReplaceFilterFactory" pattern="([^a-z0-9])" replacement="" replace="all"/>
    </analyzer>
</fieldType>
```

to automatically populate the field from the source a copyField action can be used:

```xml
<copyField source="YOURFIELD" dest="YOURFIELD_sort"/>
```

