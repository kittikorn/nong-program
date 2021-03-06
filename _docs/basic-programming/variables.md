---
title: Variables
subtitle: การใช้งาน <strong>ตัวแปร</strong> ในการกำหนดค่า
icon: fas fa-superscript
difficulty: 2
duration: 3
useful: 4
---

**ตัวแปร หรือ Variables** ในการเขียนโปรแกรม ก็เหมือนๆกับการกำหนดตัวแปร `x` หรือ `y` ที่เราอาจจะคุ้นเคยกันในวิชาคณิตศาสตร์ **เพื่อแทนค่าอะไรบางอย่าง** เช่น

> กำหนดค่า **x เท่ากับ 3** เมื่อเรานำ **x + 2** จะได้เท่ากับ **5**
{:.is-light}

โดยการจัดให้เป็นรูปแบบในการเขียนโปรแกรมได้ดังนี้

```javascript
let x = 3; // ประกาศตัวแปรชื่อ x โดยกำหนดค่า x เท่ากับ 3

/**
 * โดยอาจจะแปลภาษาโปรแกรมเป็นภาษาคนแบบไทยๆได้ดังนี้
 *
 * let  | ประกาศตัวแปร
 * x    | ชื่อเอ็กซ์
 * =    | โดยกำหนดค่าเท่ากับ
 * 3    | สาม
 */

alert(x + 2); // แสดงผล x + 2
```

เมื่อเราทำการ **Run** ผลลัพธ์ที่ได้คือ `5` ตามผลลัพธ์ของ `alert()` ที่สั่งให้แสดงผลของ `x + 2` โดยเราจะใช้คำสั่ง `let` เพื่อการประกาศตัวแปรเป็นชื่อต่างๆ และใช้เครื่องหมาย `=` ในการกำหนดค่าให้กับตัวแปร

## การประกาศตัวแปร

ในการประกาศตัวแปรของ **JavaScript** จะเรียกใช้คำสั่งว่า `let` จากนั้นตามด้วยชื่อตัวแปรที่เราต้องการ

```js
let message; // ประกาศตัวแปรชื่อ message แบบไม่มีค่า
```

จากนั้นในการกำหนดค่า เราจะใช้คำสั่ง `=` ที่เรียกว่าการ **Assignment**

```js
let message; // ประกาศตัวแปรชื่อ message แบบไม่มีค่า
message = 'Hello World!'; // กำหนดให้ตัวแปร message มีค่าเท่ากับ 'Hello World!'
```

จากนั้นเราจะได้ว่า `message` มีค่าเท่ากับ `'Hello World!` เมื่อทำการแสดงผลด้วย `alert()`

```javascript
let message; // ประกาศตัวแปรชื่อ message แบบไม่มีค่า
message = 'Hello World!'; // กำหนดให้ตัวแปร message มีค่าเท่ากับ 'Hello World!'
alert(message); // แสดงผลค่าบนตัวแปรของ message
```

> **คำเตือน:** ในการใช้ชื่อตัวแปร **พิมพ์เล็ก-พิมพ์ใหญ่** มีผลต่อการใช้งาน เช่นดังตัวอย่างที่ใช้ `Message`
>
> ```javascript
> let Message = 'Hello World!'; // ✅ (M)essage
> alert(message); // ⛔ (m)essage
> ```
> {:.is-danger}
>
> จะพบว่ามี **Exception** เตือนว่า `message is not defined` ตามที่แปลได้ตรงๆ คือ `message` ไม่ได้ถูกกำหนดค่าไว้ ดังนั้นจึงต้องเปลี่ยนเป็นพิมพ์เล็ก-ใหญ่ให้ถูกต้องด้วย
>
> ```javascript
> let Message = 'Hello World!'; // ✅ (M)essage
> alert(Message); // ✅ (M)essage
> ```
>
> นอกจากนั้น การกำหนดชื่อตัวแปร **จะไม่สามารถใช้คำสงวนได้** เช่น `let` ดังตัวอย่าง
>
> ```javascript
> let let = 'Let me gooo!'; // ⛔ ใช้ let ไม่ได้เพราะซ้ำกับคำสั่ง JS
> ```
> {:.is-danger}
>
> จะพบว่ามี **Exception** เตือนว่า `Unexpected strict mode reserved word` เนื่องจากเป็นคำสงวนที่ **ซ้ำกับคำสั่งบน JavaScript**
>
> โดยนอกจากนั้นยังมีตัวแปรอื่นๆที่ไม่สามารถตั้งชื่อได้ เช่น **ไม่สามารถนำตัวเลขขึ้นนำหน้าชื่อตัวแปรได้** และ **ไม่สามารถใช้เครื่องหมายพิเศษได้** (ยกเว้น `_` และ `$`) เนื่องจากซ้ำกับสัญลักษณ์คำสั่งอื่นๆที่มีบนภาษาโปรแกรม
>
> ```javascript
> let 123Hi = '123, Hi!'; // ⛔ ใช้ไม่ได้ เพราะขึ้นต้นด้วยตัวเลข
> alert(123Hi);
> ```
> {:.is-danger}
>
> ```javascript
> let Hi123 = '123, Hi!'; // ✅ ใช้ได้ เพราะไม่ได้ขึ้นต้นด้วยตัวเลข
> alert(Hi123);
> ```
>
> ```javascript
> let message-me = 'My name is program'; // ⛔ ใช้ไม่ได้ เพราะมีเครื่องหมายพิเศษ
> alert(message-me);
> ```
> {:.is-danger}
>
> ```javascript
> let message:me = 'My name is program'; // ⛔ ใช้ไม่ได้ เพราะมีเครื่องหมายพิเศษ
> alert(message:me);
> ```
> {:.is-danger}
>
> ```javascript
> let message me = 'My name is program'; // ⛔ ใช้ไม่ได้ เพราะการเว้นวรรค (Space) จะเป็นการมองเป็นคำสั่งแยกกัน
> alert(message me);
> ```
> {:.is-danger}
>
> ```javascript
> let message_me = 'My name is program'; // ✅ ใช้ได้ โดยการใช้เครื่องหมาย _ (Underscore) แทนซึ่งไม่จัดว่าเป็นเครื่องหมายพิเศษของโปรแกรม
> alert(message_me);
> ```
>
> ```javascript
> let $message = 'My name is program'; // ✅ ใช้ได้ โดยการใช้เครื่องหมาย $ (Dollar-sign) ไม่จัดว่าเป็นเครื่องหมายพิเศษของโปรแกรม
> alert($message);
> ```
{:.is-warning}

## การแทนที่ค่าตัวของแปร

จากตัวอย่างเก่า เราจะทำการกดหนดค่าใหม่ให้กับตัวแปร `message` ได้โดยการใช้ **Reassignment** ผ่านเครื่องหมาย `=` อีกครั้งกับชื่อตัวแปรเดิม โดยไม่ต้องใช้ `let` เพิ่มเพราะมีการประกาศตัวแปรไว้ก่อนหน้านั้นแล้ว

```javascript
let message; // ประกาศตัวแปรชื่อ message แบบไม่มีค่า
message = 'Hello World!'; // กำหนดให้ตัวแปร message มีค่าเท่ากับ 'Hello World!'
alert(message); // แสดงผล message
message = 'Welcome home!'; // กำหนดให้ตัวแปร message ใหม่อีกครั้ง ให้มีค่าเท่ากับ 'Welcome home!'
alert(message); // แสดงผล message
```

จากตัวอย่างจะพบว่า `message` มีการเปลี่ยนค่าไปหลังจาก **บรรทัดที่ 4** ทำให้ค่าของ `message` ถูกแทนที่ด้วยค่าใหม่

## การกำหนดตัวแปรหลายค่า

ในการกำหนดตัวแปรหลายๆค่าพร้อมกันจะใช้เครื่องหมาย `,` **(Comma)** ในการแบ่งตัวแปรได้โดยไม่ต้องเรียกใช้ `let` หลายๆครั้งได้ โดยในตัวอย่างเราต้องการทั้งหมด **3 ตัวแปร** เราก็ไม่จำเป็นต้องใช้ `let` ทั้งหมด 3 ครั้ง แต่ใช้ `,` ในการแบ่งชื่อตัวแปรที่เราประกาศต่างๆได้

และบางคนก็จะมีวิธีการจัดเรียงตัวแปรหลายค่าเหล่านี้มี **Format (รูปแบบ)** ต่างกันตามความถนัดหรือรูปแบบแต่ล่ะโปรแกรม โดยมีตัวอย่างดังนี้

```js
// ประกาศตัวแปร แบบประกาศชื่อ และกำหนดค่าแยกกัน
let firstname;
let lastname;
let age;
firstname = 'John';
lastname = 'Doe';
age = 18;
```

```js
// ประกาศตัวแปร แบบประกาศชื่อแยก let แต่ล่ะช่วง และกำหนดค่าภายใน Statement นั้นๆ
let firstname = 'John';
let lastname = 'Doe';
let age = 18;
```

```js
// ประกาศตัวแปร แบบประกาศชื่อบน let ตัวเดียวกันโดยการแบ่งชื่อด้วย , จากนั้นกำหนดค่าบน Statement ต่อๆไป
let firstname, lastname, age;
firstname = 'John';
lastname = 'Doe';
age = 18;
```

```js
// ประกาศตัวแปร แบบประกาศชื่อบน let ตัวเดียวกันร่วมกับการกำหนดค่าภายในบรรทัดทันที โดยจะเหลือเพียงบรรทัดเดียว
let firstname = 'John', lastname = 'Doe', age = 18;
```

```js
// ประกาศตัวแปร แบบเดียวกับตัวอย่างด้านบน แต่จะมีการจัดรูปแบบโดยการเว้นบรรทัดทุกครั้งที่มีการ , จากนั้นจบด้วย ; โดยมีย่อหน้าที่ตรงกันทุกตัวแปร
let firstname = 'John',
    lastname = 'Doe',
    age = 18; // ต้องดูให้ดีด้วยว่ามี ; ปิดท้ายด้วย
```

```js
// ประกาศตัวแปร แบบเดียวกับตัวอย่างด้านบน ต่างกันที่จัดให้เครื่องหมาย , อยู่ในบรรทัดต่อไป และอยู่ตำแหน่งย่อหน้าเดียวกับ let
let firstname = 'John'
  , lastname = 'Doe'
  , age = 18; // ต้องดูให้ดีด้วยว่ามีการแบ่ง , ที่ถูกต้อง และต้องมี ; ปิดท้ายด้วย
```

## ค่าคงที่

**ค่าคงที่ (Constants)** จะใช้ `const` ในการประกาศชื่อตัวแปร แทนการใช้ `let` เพื่อกำหนดให้ตัวแปรดังกล่าว **ไม่สามารถถูกแทนค่าได้อีกครั้ง**

```js
const birthday = '19/09/1999'; // ประกาศตัวแปร birthday เป็นค่าคงที่
```

โดยหากมีการเปลี่ยนตัวแปร `birthday` จะทำให้เกิดการ Exception ว่า `Assignment to constant variable.`

```javascript
const birthday = '19/09/1999'; // ประกาศตัวแปร birthday เป็นค่าคงที่
birthday = '10/10/2010'; // ⛔ ไม่สามารถเปลี่ยนได้ เนื่องจากเป็นค่าคงที่
```
{:.is-danger}

และตัวแปร `birthday` ก็จะไม่สามารถถูกประกาศตัวแปรใหม่อีกครั้งได้ โดยจะมี Exception ว่า `Identifier 'birthday' has already been declared`

```javascript
const birthday = '19/09/1999'; // ประกาศตัวแปร birthday เป็นค่าคงที่
let birthday = '10/10/2010'; // ⛔ ไม่สามารถประกาศชื่อตัวแปรทับค่าคงที่ได้
```
{:.is-danger}

> **หมายเหตุ:** การใช้งานของ `const` จะเป็นลักษณะกำหนดคุณสมบัติบางอย่างที่เราไม่ต้องการให้เปลี่ยนแปลงในภายหลัง เนื่องจากมีความสำคัญสูง โดยส่วนมากมักใช้ **Uppercase หรือตัวพิมพ์ใหญ่** ทั้งข้อความ เพื่อกันความสับสนของตัวแปรทั่วไปกับค่าคงที่ เช่น `const BIRTHDAY = '19/09/1999'`

## บทสรุป

- ใช้ `let` ในการ **ประกาศชื่อตัวแปร** ให้แก่ข้อความต่อไป และการระวังตั้งชื่อตัวแปรที่ไม่สามารถใช้ได้ ได้แก่
  - คำสงวนที่ซ้ำกับชื่อคำสั่งอื่นๆ
  - การนำตัวเลขนำหน้า
  - การใช้เครื่องหมายพิเศษ ยกเว้น `_` และ `$`
- การใช้ **Assignment** ด้วย `=` เพื่อกำหนดค่าต่างๆให้แก่ตัวแปรหรือค่าคงที่
- การแทนค่าตัวแปรเพื่อลบค่าเดิม **Reassignment** ด้วย `=` โดยกำหนดให้กับตัวแปรที่ถูกประกาศใช้งานไว้ก่อนหน้านั้นแล้ว
- การแบ่ง `,` ตัวแปรโดยไม่ต้องประกาศ `let` ซ้ำอีกครั้ง
- การใช้ **ค่าคงที่ (Constants)** ของ `const` จะไม่สามารถกำหนดเป็นค่าอื่นๆได้อีก
