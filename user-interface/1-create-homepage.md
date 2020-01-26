
# สร้างหน้า Home Page 

> ดูรายการ User Interface Component ทั้งหมดได้ที่ https://ionicframework.com/docs/components

เปิดไฟล์ **src/pages/Home.tsx** 

## 1. เรียกใช้ Module `IonList` และ `IonItem` 

- [รายละเอียด IonList](https://ionicframework.com/docs/api/list)
- [รายละเอียด IonItem](https://ionicframework.com/docs/api/item)

```js
import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar, IonList, IonItem } from '@ionic/react';
```

## 2. เปลี่ยนชื่อส่วนหัวเพจ 

```html
<IonHeader>
    <IonToolbar>
        <IonTitle>Contact</IonTitle>
    </IonToolbar>
</IonHeader>
```

## 3. สร้างรายการเมนูด้วย IonList และ IonItem

```html
<IonContent>
    <IonList>
        <IonItem>
            Michael
        </IonItem>
        <IonItem>
            Jojo
        </IonItem>
        <IonItem>
            Sandra
        </IonItem>
    </IonList>
</IonContent>
```

## ไฟล์ **src/pages/Home.tsx**

```jsx
import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar, IonList, IonItem } from '@ionic/react';
import React from 'react';

const Home: React.FC = () => {
  return (
    <IonPage>
      <IonHeader>
        <IonToolbar>
          <IonTitle>Contact</IonTitle>
        </IonToolbar>
      </IonHeader>
      <IonContent>
        <IonList>
          <IonItem>
            Michael
          </IonItem>
          <IonItem>
            Jojo
          </IonItem>
          <IonItem>
            Sandra
          </IonItem>
        </IonList>
      </IonContent>
    </IonPage>
  );
};

export default Home;
```