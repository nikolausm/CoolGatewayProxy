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

The Filesystem caching should enable a fast access to the filesystem by providing a structure of maximum of 1156 files per directory and max of 1156 of directories by directory.

This will be accomplished ab spearating the filestructure into directory.

Example: mycurrentfilenr18.html, will be stored in my/cu/rr/en/tf/il/en/nr/18.html.

This leads to a very fast access to those files.

### Database Caching

In addition to the Filecaching it is possible to store Cachfiles into database.

### Intelligent Resource Update

Depending on how often the files are generated and requested, the internal mechanism will ensure to deliver the most recent file and prevent the generation on request problem. It ensures only cached values are delivered to the client.

### Simple caching interface

Caching can be set up simple by configuration.

 @todo #1 Add more details to each node.


<cachingConfigurations>
  <configuration name="products">
    <sourcePath>/products</sourcePath>
    <methods>
      <method>GET</method>
    </methods>
    <parameterSettings>
      <ignoreOrder>
        true
      </ignoreOrder>
      <ignoreParameters>
      </ignoreParameters>
      <cache>
        <maxDurationInSeconds>600<maxDurationInSeconds>
        <autoupdate threshold="15">true</autoupdate>
      <cache>
    </parameterSettings>
  </configuration>
</cachingConfigurations>
## BFF Features

### Routing

<routeConfiguration id="mesh">
  <incomingRoute>/v1/categories<incomingRoute>
  <target>
    {
      [
        "replace": {
          "id": "Brand1",
          "selector": "$..*"
          "link": {
            "href": "https://q-myApp.myDomain.com/categoryService/v1/categories/600000-1"
          }
        },
        "replace": {
          "id": "Brand1",
          "selector": "$..*",
          "link": {
            "href": "https://q-myApp.myDomain.com/categoryService/v1/categories/600000-2"
          }
        }
      ]
    }
  </target>
  <parametersPassthrough>true</parametersPassthrough>
</routeConfiguration>
### Json Combiner

combines a Json file only by configuring multiple requests.

Will use
https://github.com/json-path/JsonPath

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