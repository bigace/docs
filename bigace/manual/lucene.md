# Lucene search

In Bigace v3 the [MySQL search](bigace/manual/search) was replaced with Lucene.

## Indexing

Currently Bigace indexes the following data automatically when adding or updating/saving:

 1.  User
 2.  Pages (metadata and content)
 3.  Image metadata (like name, description ...)
 4.  File metadata (like name, description ...)
    - Docx (MS Word 2010)
    - Pptx (MS Powerpoint 2010)

## Re-indexing

Re-indexing is the process of reloading all content into the search index.
This process is, depending on your amount of data in Bigace, pretty time- and memory consuming. You should not use this function unless you have pretty good reasons for it.

Legal reasons could be:

*  a crashed index

*  a missing index after Bigace migration

*  ...
