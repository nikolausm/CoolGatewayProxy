# The highest priorities of this proxy

Easily to configure and high performant

Most important use cases is to be used as backend for the Frontend / Gateway
and for caching

## Caching Features

 @todo #1:30 Add more information here about caching
Caching headers are fully supported, such as Etags etc.

### Memory Caching

 @todo #1:45 Add some example how to configure max memory etc.

Based on priority, the memory cache can be used.

### File Caching

### Database Caching

### Intelligent Resource Update

### Simple caching interface

## BFF Features

### Json Combiner

combines a Json file only by configuring multiple requests.

### Autoexpand

´
{
    "blogpost":{
      "link":{
         "rel":"self",
         "href":"<http://blog/post/4711">
      }
}
´
will result in
´
{
    "blogpost":{
      {
          "title": "The Blog post",
          "content": "the content of the blogpost"
      }
}
´
Links are retrieved asychronisly

Translated with www.DeepL.com/Translator