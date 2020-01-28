
# เก็บข้อมูลที่ถูกเลือกจากหน้า Home และดึงมาใช้งานในหน้า Detail

เปิดไฟล์ **src/pages/Home.tsx**

## 1. เรียกใช้ share module 

```js
import shareValue from "../models/share";
```

## 2. เก็บข้อมูลเข้า share module ก่อนที่จะเปิดไปหน้า Detail  

```js
let itemList = contactArray.map((item) => {
    return (
      <IonItem onClick={() => {
        shareValue.selected = item;
        history.push('/detail');
      }}>{item}</IonItem>
    )
  })
```

## 3. แสดงข้อมูลในหน้า Detail โดยดึงจาก share module 

เปิดไฟล์ **src/pages/Detail.tsx**

ทำการเรียกใช้ share module และเอามาแสดงใน JSX 

```jsx
import shareValue from '../models/share';

const DetailPage: React.FC = () => {
    let name = shareValue.selected;
    return (
        <IonPage>
            <IonHeader>
                <IonToolbar>
                    <IonButtons slot="start">
                        <IonBackButton></IonBackButton>
                    </IonButtons>
                    <IonTitle>{name}</IonTitle>
                </IonToolbar>
```

## ไฟล์ **src/pages/Detail.tsx**

```jsx
import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar, IonButtons, IonBackButton } from '@ionic/react';
import React from 'react';
import shareValue from '../models/share';

const DetailPage: React.FC = () => {
    let name = shareValue.selected;
    return (
        <IonPage>
            <IonHeader>
                <IonToolbar>
                    <IonButtons slot="start">
                        <IonBackButton></IonBackButton>
                    </IonButtons>
                    <IonTitle>{name}</IonTitle>
                </IonToolbar>
            </IonHeader>
            <IonContent className="ion-padding">
                UI goes here...
            </IonContent>
        </IonPage>
    );
};

export default DetailPage;
```

## ไฟล์ **src/pages/Home.tsx**

```jsx
import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar, IonList, IonItem, IonButtons, IonButton, IonIcon } from '@ionic/react';
import React from 'react';
import { RouteComponentProps } from 'react-router';
import { add } from 'ionicons/icons';

import shareValue from "../models/share";

const Home: React.FC<RouteComponentProps> = ({ history }) => {

  let contactArray = [
    'Michael',
    'Jojo',
    'Sandra',
    'Susan'
  ];

  let itemList = contactArray.map((item) => {
    return (
      <IonItem onClick={() => {
        shareValue.selected = item;
        history.push('/detail');
      }}>{item}</IonItem>
    )
  })

  return (
    <IonPage>
      <IonHeader>
        <IonToolbar>
          <IonTitle>Contact</IonTitle>
          <IonButtons slot="end">
            <IonButton onClick={() => history.push('/new-contact')}>
              <IonIcon slot="icon-only" icon={add}></IonIcon>
            </IonButton>
          </IonButtons>
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