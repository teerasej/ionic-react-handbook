
# แสดงแผนที่เมื่อได้ข้อมูลพิกัด

## อ้างอิง

- [วิธีขอ Google Map API Key](https://developers.google.com/maps/documentation/javascript/get-api-key)
- [Google Map API Documentation](https://developers.google.com/maps/documentation/javascript/tutorial)

## 1. ติดตั้ง module 

```bash
npm i google-map-react @types/google-map-react
```

## 2. เรียกใช้ในหน้า Home 

```js
import GoogleMapReact from 'google-map-react';
```

## 3. แสดง Google Map React เมื่อตำแหน่ง GPS พร้อมใช้งาน

เนื่องจาก google-map-react จะทำงานเมื่อมีการกำหนดพิกัดเริ่มต้น เราจึงเลือกที่จะแสดงแผนที่บนแอพ เมื่อได้พิกัดมาจาก Geolocation แล้ว 

เราจะเริ่มจากกำหนด useState เพื่อสร้างตัวแปร
1. ที่จะกำหนดการแสดง `<GoogmeMapReact>` ขึ้นมาในหน้าจอ
2. ค่าตัวแปรที่เก็บตำแหน่งที่ได้จาก Geolocation

ในที่นี้เราไม่ต้องการเปลี่ยนแปลงค่า Zoom เลยกำหนดเป็นตัวแปรธรรมดา

```js

const [positionReady, setPositionReady] = useState(false);
const [currentPosition, setCurrentPosition] = useState({ lat: 0, lng: 0 });
const currentZoom = 15;
```

จากนั้นเราจะใช้ตัวแปร state นี้ ในการพิจารณาว่าจะแสดง GoogleMapReact เมื่อไหร่ 

```jsx
let googleMap;
  
  if(positionReady){
    console.log('Data is ready');
    googleMap = (
      <GoogleMapReact
            bootstrapURLKeys={{ key: 'AIzaSyBDqlW1EIlePcA48oLVV_kYQJXm9dQ75uw' }}
            defaultCenter={currentPosition}
            defaultZoom={currentZoom}
          >
          </GoogleMapReact>
    )
  }
```

จากนั้นนำ `googleMap` ไปแสดงในหน้าแอพ

```jsx
<IonContent>
    <div style={{ height: '94vh', width: '100%' }}>
        {googleMap}
    </div>
    <IonLoading
        isOpen={showLoading}
        message={'Getting GPS...'}
    />
</IonContent>
```

## 4. กำหนดตัวแปร state ด้วยข้อมูลที่ได้จาก Geolocation 

หลังจากที่ได้พิกัดมา เราก็จะกำหนดค่าตัวแปร state ที่ทำให้เกิดการ render component ใหม่

```js
  setPositionReady(true);
  setCurrentPosition({ lat: coordinates.coords.latitude, lng: coordinates.coords.longitude })
```

```js
const startGetGPS = async () => {
    console.log('getting gps');
    setshowLoading(true);
    const coordinates = await Geolocation.getCurrentPosition();
    setshowLoading(false);
    console.log('Current', coordinates);

    setPositionReady(true);
    setCurrentPosition({ lat: coordinates.coords.latitude, lng: coordinates.coords.longitude })
}
```

