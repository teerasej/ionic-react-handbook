
# การกลไกการเปิดจากหน้า Home ไป Detail

เปิดไฟล์ **src/pages/Home.tsx**

## 1. เรียกใช้ RouteComponentProps จาก module ชื่อ react-router

```js
import { RouteComponentProps } from 'react-router';

// กำหนดให้กับ React.FC เพื่อใช้งานตัวแปรที่ชื่อ history
const Home: React.FC<RouteComponentProps> = ({ history }) => {
```

## 2. ใช้งาน history ตอนที่มีการกด IonItem 

เราสามารถตรวจกับการกดบน User Interface ได้ โดยใช้ event attribute ชื่อ `onClick` โดยกำหนด function ที่ต้องการให้ทำงาน

ในที่นี้เราจะใช้ตัวแปร history ที่ส่งเข้ามาในการสั่งเปิดไปยัง Route ชื่อ `/detail` (ชื่อเดียวกันกับที่ตั้งไว้ในไฟล์ `src/App.tsx`)

```jsx
let itemList = contactArray.map((item) => {
    return (
      <IonItem onClick={() => history.push('/detail')}>{item}</IonItem>
    )
  })
```

# ไฟล์ **src/pages/Home.tsx**

```jsx
import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar, IonList, IonItem } from '@ionic/react';
import React from 'react';
import { RouteComponentProps } from 'react-router';

const Home: React.FC<RouteComponentProps> = ({ history }) => {

  let contactArray = [
    'Michael',
    'Jojo',
    'Sandra',
    'Susan'
  ];

  let itemList = contactArray.map((item) => {
    return (
      <IonItem onClick={() => history.push('/detail')}>{item}</IonItem>
    )
  })

  return (
    <IonPage>
      <IonHeader>
        <IonToolbar>
          <IonTitle>Contact</IonTitle>
        </IonToolbar>
      </IonHeader>
      <IonContent>
        <IonList>
          {itemList}
        </IonList>
      </IonContent>
    </IonPage>
  );
};

export default Home;
```