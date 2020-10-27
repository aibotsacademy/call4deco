# 🤖 Stormy Bot Documentation🌪 https://stormybot.talktoai.co/
## IBM Call for Code 2020
### Global Competition 
###### ||Tech Stak: IBM Watson + IBM Push Notifications + NASA GIBS API ||
###### ||Data Sources: [NASA GIBS API](https://wiki.earthdata.nasa.gov/display/GIBS/GIBS+API+for+Developers) ||
###### ||Region: Latin America & Caribbean 🌎 ||Challenge: Climate Change ||

#### Stormy is a virtual assistant trained on predicting and alerting about Natural Disasters!

![Test Image 4](https://i.ibb.co/x7WMPDn/Screen-Shot-2020-07-31-at-04-04-22.png)

#### How it works?

-  👇 Stormy Bot Pitch: Global Challenge

[![Stormy Bot Pitch](https://img.youtube.com/vi/Acci829ZVNI/2.jpg)](https://youtu.be/Acci829ZVNI)

- 👇 Stormy Bot Live Demo (1 minute)

[![Stormy Bot Live Demo](https://img.youtube.com/vi/pFKrdUqfDDs/2.jpg)](https://youtu.be/pFKrdUqfDDs)

- 👇 Stormy Bot Pitch: LATAM Challenge (2 minutes)

[![Stormy Bot Live Demo](https://img.youtube.com/vi/7bLHkBmf1UM/2.jpg)](https://youtu.be/7bLHkBmf1UM)


- [Try our Demo](https://stormybot.talktoai.co/)


> Phase 1: Monitoring NASA Data about Natural Disasters:

We use the ***NASA's Global Imagery Browse Services (GIBS) APIs*** as a Data Provider for the satellite imagery and visualize the Data Layers using  ***Web Map Title Service (WMTS)*** such as:

- URL: https://gibs.earthdata.nasa.gov/wmts/
- Layer: (e.g. "MODIS / Terra")
- Matrix Set:'EPSG_(n)m'
- Origin:[Lat, Long]
- Resolution:[0...2]
- Tile: Open Layers

> Create Layer function:

```
 function createLayer() {
    var source = new ol.source.WMTS({
      url: 'https://gibs.earthdata.nasa.gov/wmts/epsg4326/best/wmts.cgi?SERVICE='
      layer: 'MODIS_Terra_Property1_Property(n)',
      format: 'image/jpeg',
      matrixSet: 'EPSG_(N)m',
      tileGrid: new ol.tilegrid.WMTS({
        origin: [Lat, Long],
        resolutions: [
          0...(n)
        ],
        matrixIds: [0, 1, 2, 3, 4, 5, 6, 7, 8],
        tileSize: 512
      })
    });
```

> Phase 2: Integrate IBM Watson to the Web

```
<script>
  window.watsonAssistantChatOptions = {
      integrationID: "your_ID", // The ID of this integration.
      region: "us-south", // The region your integration is hosted in.
      serviceInstanceID: "your_Service", // The ID of your service instance.
      onLoad: function(instance) { instance.render(); }
    };
  setTimeout(function(){
    const t=document.createElement('script');
    t.src="https://web-chat.global.assistant.watson.appdomain.cloud/loadWatsonAssistantChat.js";
    document.head.appendChild(t);
  });
</script>
```
#### What's next?

> Phase 3: Social Media API
By Meassuring near real time Keyword trends in search engines we can Correlate the socio economic variables such as: (i) Total Population, (ii)GDP, Country Debt, (iv) Foreign Investment, (v) Public Transport Statistics and (n) other predictors as (vi) Education for adjusting our COVID19 Spread risk and prevention model scoring.


```
KeywordTrends.dailyTrends({
  trendDate: new Date('2019-01-10'),
  geo: 'US',
}, function(err, results) {
  if (err) {
    console.log(err);
  }else{
    console.log(results);
  }
});
```
> Phase 4: Computer Vision 
Users can send their pictures from climate events to help on the prediction model! 


![Test Image 4](https://i.ibb.co/WPMWB8r/C4C.png)
