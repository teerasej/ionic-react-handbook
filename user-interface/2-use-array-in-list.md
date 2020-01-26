
# ใช้ข้อมูลจาก Array ใน List 

เปิดไฟล์ **src/pages/Home.tsx** 

## 1. สร้างตัวแปร Array ใน function Home

```js
const Home: React.FC = () => {

  let contactArray = [
    'Michael',
    'Jojo',
    'Sandra',
    'Susan'
  ];

```

## 2. สร้างรายการของ JSX จากข้อมูลใน Array

เราจะใช้ `array.map()` เพื่อวนเอาข้อมูลใน Array ทีละตัว สร้างเป็น JSX และเก็บไว้ในตัวแปรชื่อ `itemList`

```jsx
  let itemList = contactArray.map((item) => {
    return (
    <IonItem>{item}</IonItem>
    )
  })
```


## 3. แก้ส่วนของ JSX ที่เป็น List ให้ใช้ค่าตัวแปร `itemList` แทน

```html
<IonContent>
    <IonList>
        {itemList}
    </IonList>
</IonContent>
```

## ไฟล์ **src/pages/Home.tsx**

```jsx
import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar, IonList, IonItem } from '@ionic/react';
import React from 'react';

const Home: React.FC = () => {

  let contactArray = [
    'Michael',
    'Jojo',
    'Sandra',
    'Susan'
  ];

  let itemList = contactArray.map((item) => {
    return (
    <IonItem>{item}</IonItem>
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