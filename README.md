# Features
* Create 3D polygons
* Trigger events when enter or leave them

# How to use
### Create 3D Polygon (without event):
```js
alt.emit("ZoneManager:DrawZoneBy2",startPos, endPos, r, g, b, a);
```
### Or if you want more points:
```js
alt.emit("ZoneManager:DrawZoneBy4",vectors, height, r, g, b, a);
alt.emit("ZoneManager:DrawZoneBy6",vectors, height, r, g, b, a);
alt.emit("ZoneManager:DrawZoneByN",vectors, height, r, g, b, a);
```

### Register or Unregister a zone:
```js
alt.emit("ZoneManager:RegisterZone",vectors, height, zoneName, type, dimension);
alt.emit("ZoneManager:UnregisterZone",zoneName, dimension);
```

### Check if a point is in the zone:
```js
alt.emit("ZoneManager:IsPointInZone",point, zoneName, dimension);
```

### (W.I.P) Get a Zone by Index or Name:
```js
alt.emit("ZoneManager:GetZoneByName",name,dimension);
alt.emit("ZoneManager:GetZoneByIndex",index);
```

# Known Bugs:
* zoneName is sometimes undefined when entering/leaving a zone
* dimension is 0 everytime, because there is no clientside getter

###### made with [❤](https://www.youtube.com/watch?v=XWFttsqzfcg) by [@Phill030](https://open.spotify.com/track/5YsZ99OX1aOyppre3Zwhnp?si=7e4da09dd74d489b)
