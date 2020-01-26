
# สร้างปุ่มเปิด New Contact จากหน้า Home

เปิดไฟล์ **src/pages/Home.tsx**

## 1. เรียกใช้ module 

```js
import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar, IonList, IonItem, IonButtons, IonButton, IonIcon } from '@ionic/react';
import { add } from 'ionicons/icons';
```

## 2. เพิ่มปุ่มไอคอนใน IonToolbar

โดยใส่ event attribute `onClick` พร้อม function ที่จะเรียกใช้ history เพื่อเปิดไปยัง Route URL `/new-contact` 

```html
<IonToolbar>
    <IonTitle>Contact</IonTitle>
    <IonButtons slot="end">
        <IonButton onClick={() => history.push('/new-contact')}>
            <IonIcon slot="icon-only" icon={add}></IonIcon>
        </IonButton>
    </IonButtons>
</IonToolbar>
```

## ไฟล์ **src/pages/Home.tsx**

import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar, IonList, IonItem, IonButtons, IonButton, IonIcon } from '@ionic/react';
import React from 'react';
import { RouteComponentProps } from 'react-router';
import { add } from 'ionicons/icons';

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