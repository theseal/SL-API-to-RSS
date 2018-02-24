# SL-API-to-RSS

Supported endpoints
* realtimedeparturesV4

## realtimedeparturesV4
[Documentation from SL](https://www.trafiklab.se/api/sl-realtidsinformation-4).
#### Arguments
* **apiKey** - (required) your API key from Trafiklabs (see documentation above)
* **destinationFilter** - (optional) regexp if you want to see all destinations in the feed
* **stationId** - (required) the station which you want to see real-time depatures from (The ID can be found by searching real-time depatures on SL.se and then notice the ID in the browser location bar.
* **transportMode** - (required) The type of transportation you would like to see in your stream. Supported types are (case sensitve):
  * Buses
  * Metros
  * Trains
  * Trams
  * Ships
  
#### Example
```
$ curl  'http://localhost:5000/realtimedeparturesV4?stationId=9326&apiKey=SECRETKEY&transportMode=Metros&destinationFilter=Kungs'
<?xml version='1.0' encoding='UTF-8'?>
<rss xmlns:atom="http://www.w3.org/2005/Atom" xmlns:content="http://purl.org/rss/1.0/modules/content/" version="2.0">
  <channel>
    <title>realtimedeparturesV4 9326 (Metros)</title>
    <link>https://github.com/theseal/SL-API-to-RSS</link>
    <description>realtimedeparturesV4 to RSS.</description>
    <docs>http://www.rssboard.org/rss-specification</docs>
    <generator>python-feedgen</generator>
    <lastBuildDate>Sat, 24 Feb 2018 20:14:08 +0000</lastBuildDate>
    <item>
      <title>Kungsträdgården 1 min</title>
    </item>
    <item>
      <title>Kungsträdgården 15 min</title>
    </item>
  </channel>
</rss>


Patches are welcome!
