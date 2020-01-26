
# รู้จัก และใช้งาน Ionic Component

Ionic React ใช้แนวคิดการแบ่งส่วนต่างๆ ของแอพพลิเคชั่น ออกเป็นไฟล์ย่อยๆ เรียกว่า **Component** 

ซึ่งใน 1 Component จะประกอบไปด้วย 3 ส่วน นั่นคือ

```jsx
// 1. ส่วน import module อื่นๆ มาใช้งาน
import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar } from '@ionic/react';
import React from 'react';

// 2. ส่วนของหน้าตา Component ที่เขียนใสรูปแบบ function 
const Home: React.FC = () => {

  // function จะ return ค่าเป็น JSX รูปแบบของหน้าตา User Interface ที่คล้ายกับการเขียนหน้าเว็บด้วย HTML
  return (
    <IonPage>
      <IonHeader>
        <IonToolbar>
          <IonTitle>Ionic Blank</IonTitle>
        </IonToolbar>
      </IonHeader>
      <IonContent className="ion-padding">
        The world is your oyster.
        <p>
          If you get lost, the{' '}
          <a target="_blank" rel="noopener noreferrer" href="https://ionicframework.com/docs/">
            docs
          </a>{' '}
          will be your guide.
        </p>
      </IonContent>
    </IonPage>
  );
};

// 3. ส่วนที่ export function ออกไปใช้งานที่ module อื่น
export default Home;
```

## JSX ของ Ionic 

ดูรายการ JSX Component ทั้งหมดได้ที่ https://ionicframework.com/docs/components

## เปรียบเทียบกับ JavaScript ใน Node.js

เนื่องจาก React มีการนำภาษา TypeScript มาใช้งาน ซึ่งมี keyword และวิธีการเขียนที่เพิ่มจาก JavaScript ธรรมดา จึงขอเปรียบเทียบส่วนที่คล้ายกันดังนี้ 

### A. เทียบ `import` กับ `require()`

เขียนใน React
```js
import React from 'react';
```

เขียนใน Node.js
```js
let React = require('react');
```

### B. เทียบ `import {...}` กับ `require()`

เขียนใน React
```js
import { IonContent, IonHeader, IonPage } from '@ionic/react';
```

เขียนใน Node.js
```js
let reactComponent = require('@ionic/react');
let IonContent = reactComponent.IonContent
let IonHeader = require('@ionic/react').IonHeader;
let IonPage = require('@ionic/react').IonPage;
```

### C. เทียบ `export default` กับ `module.exports`

เขียนใน React
```js
export default Home;
```

เขียนใน Node.js
```js
module.exports = Home;
```