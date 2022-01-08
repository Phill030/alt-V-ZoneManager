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
/*
ZoneType 1 = 2PointZone,
ZoneType 2 = 4PointZone,
ZoneType 3 = 6PointZone,
ZoneType 4 = NPointZone
*/
```
Example: 
```js
alt.emit("ZoneManager:RegisterZone",[new alt.Vector3(0,0,70), new alt.Vector3(5,5,80)],10,0,1,0);
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
# Callbacks:
### Every function has a callback, which gets triggered when you create or delete something
* IsZoneRegistered returns: [bool]
* GetZoneByName returns: [ZoneObject]
* GetZoneByIndex returns: [ZoneObject]
* RegisterZone returns: [ZoneObject]
* UnregisterZone returns: [true if deleted or false if invalid]
* DrawZoneBy2 returns: [IntervalId]
* DrawZoneBy4 returns: [IntervalId]
* DrawZoneBy6 returns: [IntervalId]
* DrawZoneByN returns: [IntervalId]
* IsPointInZone returns [bool]
```js
alt.on("ZoneManager:IsZoneRegistered:Callback")
alt.on("ZoneManager:GetZoneByName:Callback")
alt.on("ZoneManager:GetZoneByIndex:Callback")
alt.on("ZoneManager:RegisterZone:Callback")
alt.on("ZoneManager:UnregisterZone:Callback")
alt.on("ZoneManager:DrawZoneBy2:Callback")
alt.on("ZoneManager:DrawZoneBy4:Callback")
alt.on("ZoneManager:DrawZoneBy6:Callback")
alt.on("ZoneManager:DrawZoneByN:Callback")
alt.on("ZoneManager:IsPointInZone:Callback")
```
# Known Bugs:
* zoneName is sometimes undefined when entering/leaving a zone
* dimension is 0 everytime, because there is no clientside getter but this will be fixed in the near future

###### made with [❤](https://www.youtube.com/watch?v=XWFttsqzfcg) by [@Phill030](https://www.youtube.com/watch?v=f0U38Nx4oe4)
