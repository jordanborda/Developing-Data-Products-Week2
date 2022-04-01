---
title: "My First Leaflet Map"
author: "Jordan Borda"
date: "04/01/2022"
output: html_document
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
```
The source code is available at [GitHub](https://github.com/jordanborda/Developing-Data-Products-Week2)

## My First Leaflet Map
Create a leaflet map object.
```{r cars}
library(leaflet)
map <- leaflet() %>% addTiles()
```

Create a marker with a picture of Benrath Palace and a link to its homepage.
```{r}
benrathPalaceIcon <- makeIcon(
   iconUrl = "http://www.schloss-benrath.de/fileadmin/_processed_/csm_corps-de-logis-blumen_2e04b2b859.jpg",
   iconWidth = 30*408/255, iconHeight = 30,
   iconAnchorX = 30*408/255/2, iconAnchorY = 30/2
)
```

Add the marker to the map and display the map.
```{r}
benrathPalacePopup <- c("<a href= 'http://www.schloss-benrath.de/welcome/?L=1' >Benrath Palace<br><img src='http://www.schloss-benrath.de/fileadmin/_processed_/csm_corps-de-logis-blumen_2e04b2b859.jpg' width='210' height='132'  alt='Foto Corps de Logis' title='Foto Corps de Logi'></a>")
map %>%
   addTiles() %>%
   addMarkers(lat=51.161027, lng=6.870550, popup = benrathPalacePopup)
```
