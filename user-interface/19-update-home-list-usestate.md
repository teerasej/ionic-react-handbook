
# เปลี่ยนให้หน้า Home มาใช้ตัวแปร State เพื่อให้สามารถอัพเดตค่าที่มีผลต่อ JSX ได้

เปิดไฟล์ **src/pages/Home.tsx**

และปรับแก้จากตัวแปรธรรมดา ที่เอาไปใช้ใน JSX เป็นตัวแปร State ที่ได้จากการประกาศใช้ `useState`

```jsx
import React, { useState } from 'react';

const Home: React.FC<RouteComponentProps> = ({ history }) => {

  const [contactArray, setNewContactArray] = useState([
    'Michael',
    'Jojo',
    'Sandra',
    'Susan'
  ]);

```

## ไฟล์ **src/pages/Home.tsx**

```jsx
import React, { useState } from 'react';
import { RouteComponentProps } from 'react-router';
import { add } from 'ionicons/icons';

import shareValue from "../models/share";

const Home: React.FC<RouteComponentProps> = ({ history }) => {

  const [contactArray, setNewContactArray] = useState([
    'Michael',
    'Jojo',
    'Sandra',
    'Susan'
  ]);

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