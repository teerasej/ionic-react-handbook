
# ใช้งาน Loading Component ระหว่างรอข้อมูลตำแหน่ง

## 1. เรียกใช้ Loading Component 

```js
import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar, IonButtons, IonButton, IonIcon, IonLoading } from '@ionic/react';
```

## 2. นำ Loading Component มาแสดงในหน้า Home 

```jsx
let showLoading = true;

<IonContent>
    <IonLoading
        isOpen={showLoading}
        message={'Getting GPS...'}
    />
</IonContent>
```

## 3. แสดง Loading Component ก่อนเรียกข้อมูล GPS

เริ่มจากใช้ `useState` ในการสร้างตัวแปร State `showLoading` 

```js
const [showLoading, setshowLoading] = useState(false);
// let showLoading = true;
```

จากนั้นกำหนดค่าให้ `showLoading` ก่อน และหลังขอข้อมูล GPS 

```js
  const startGetGPS = async () => {
    console.log('getting gps');
    setshowLoading(true);
    const coordinates = await Geolocation.getCurrentPosition();
    setshowLoading(false);
    console.log('Current', coordinates);
  }
```

ทดสอบขอข้อมูล จะเห็นว่ามีตัว Loading แสดงขึ้นมา และซ่อนหลังได้พิกัด
