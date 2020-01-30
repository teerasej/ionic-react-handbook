
# ปักหมุดตำแหน่ง ผ่าน Google Map API

- [Google Map API Documentation](https://developers.google.com/maps/documentation/javascript/tutorial) 

ตัว `GoogleMapReact` มีการเปิด props ที่ทำให้เราเรียกใช้ Google Map API ได้โดยตรง

ทำได้โดยการกำหนด props

- `yesIWantToUseGoogleMapApiInternals`
- `onGoogleApiLoaded={({ map, maps }) => onMapLoad(map, maps)}`

```jsx
<GoogleMapReact
            bootstrapURLKeys={{ key: 'AIzaSyBDqlW1EIlePcA48oLVV_kYQJXm9dQ75uw' }}
            defaultCenter={currentPosition}
            defaultZoom={currentZoom}

            yesIWantToUseGoogleMapApiInternals
            onGoogleApiLoaded={({ map, maps }) => onMapLoad(map, maps)}
          >
          </GoogleMapReact>
```

จากนั้นเราสามารถเรียกใช้ Google Map API ได้จากตัวแปร `map` (ตัวแผนที่) และ `maps` (API) ที่ได้จาก `GoogleMapReact` component

```js
const onMapLoad = (map: any, maps: any) => {
    let marker = new maps.Marker({
      // กำหนดตำแหน่งของแผนที่ ในที่นี้ใช้ ตัวแปร state ชื่อ currentPosition ที่สร้างเอาไว้ก่อนหน้านี้
      position: currentPosition,
      map
    });
}
```

ทดสอบการทำงาน