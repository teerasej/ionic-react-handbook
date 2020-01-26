
# สร้างปุ่ม Back

เปิดไฟล์ **src/pages/Detail.tsx**

## 1. เรียกใช้ module `IonButtons` และ `IonBackButton`

```js
import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar, IonButtons, IonBackButton } from '@ionic/react';
```

## 2. เพิ่มปุ่ม `IonBackButton` ลงไปใน `IonToolbar`

```html
<IonToolbar>
    <IonButtons slot="start">
        <IonBackButton></IonBackButton>
    </IonButtons>
    <IonTitle>Page Title</IonTitle>
</IonToolbar>
```

## ไฟล์ **src/pages/Detail.tsx**

```jsx
import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar, IonButtons, IonBackButton } from '@ionic/react';
import React from 'react';

const DetailPage: React.FC = () => {

    return (
        <IonPage>
            <IonHeader>
                <IonToolbar>
                    <IonButtons slot="start">
                        <IonBackButton></IonBackButton>
                    </IonButtons>
                    <IonTitle>Page Title</IonTitle>
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