# Javascript Змінні

Змінна - комірка пам'яті, яка призначена для зберігання даних. Вона використовується для збереження, отримання, зміни значення будь-якого типу даних.

Змінну в JavaScript можна оголосити використавши наступні ключові слова:

- **var**; 
- **let**; 
- **const**.

Щоб почати використовувати змінні, потрібно розуміти як:

- створити змінну та присвоїти їй значення;
- змінити значення змінної;
- правильно іменувати змінні відповідно до прийнятих стандартів.

Далі буде розглянуто ці етапи та іншу важливу інформацію з прикладами коду.

## Оголошення змінної в JavaScript

Оголошенням називається запис змінної за допомогою ключового слова та заданого імені.

**Example**

```javascript
var userName;
let distance;
const SPEED_OF_LIGHT = 299792458;
```

## Ініціалізація змінної в JavaScript

Ініціалізація - присвоєння початкового значення при оголошені змінної.

### Undefined value

У JavaScript змінній автоматично присвоюється значення **undefined** за замовчуванням, якщо не було встановлено конкретне значення одразу при оголошенні.

**Example**

```javascript
let age; // Оголошення та ініціалізація значенням undefined
```

## Присвоєння значення змінній у JavaScript

Присвоєння - надання змінній конкретного значення. Для цього використовується знак рівності. Він є оператором присвоєння.

**Example**

```javascript
let firstName;
firstName = "Oleh"; // Присвоєння

let lastName;
lastName = "Bilyk"; // Присвоєння
```

Оголошення змінної та присвоєння їй конкретного початкового значення.

**Example**

```javascript
let number = 10;
let description = "The best book ever";
let isOnline = true;
```

## Ключові слова для оголошення JavaScript змінної

### Ключове слово **var**

Воно було єдиним способом оголошення змінних з 1995 року до введення стандарту ECMAScript (ES6) у 2015 році. З виходом ES6 були додані нові ключові слова **let** та **const**, які надали більш зручні й безпечні інструменти для роботи зі змінними, забезпечивши блокову область видимості.

Наразі використання **var** може знадобитися скоріше для підтримки роботи систем, що працюють на застарілих версіях JavaScript та скриптів у старих версіях веб-браузера.

**Example**

```javascript
var price = 120;
var lastname;

lastname = "Black";
```

#### Особливості **var**

##### 1. Змінна, яка була оголошена з використанням **var**, має глобальну або функціональну область видимості.

Змінна, оголошена поза блоком функції, є частиною глобальної області видимості. Тобто доступна в будь-якому місці коду.

**Example**

```javascript
var number = 120;
console.log(number); 

function printNumber() {
    console.log(number);
}

printNumber();
```

**Output**

```
120
120
```

##### 2. Змінна, яка оголошена всередині функції, доступна в межах цієї функції. 
Навіть, якщо код виконується у вкладених блоках. Тобто **var** ігнорує блочну область, що властива конструкціям `if`, `for`, `while`.

**Example**

```javascript
var number = 120; 

function printResult() {
    if (number > 100) {
        var message = `The number ${number} is greater than 100.`;
    }
    console.log(message); 
}

printResult();
```

**Output**

```
The number 120 is greater than 100.
```

Змінні з **var** можна переоголосити в межах їхньої області й не отримати помилку. 

**Example**

  ```javascript
  var number = 10;
  var number = 35;

  console.log(number);
  ```
  **Output**

  ```
  35
  ```

### Ключове слово **let**

Змінні, які оголошені з використанням ключового слова **let**, мають блочну область видимості. Це означає, що вони доступні лише в межах блоку, у якому оголошені.

Використовуйте ключове слово **let**, якщо значення змінної може змінитися під час виконання програми.

Приклад коду з використанням **let**.

**Example**

```javascript
let x = 10;
let y = x + 2;
let sum = 0;

sum = x + y;
console.log(sum);
```

**Output**

```
22
```

Приклад коду, де демонструється блочна область видимості змінних з ключовим словом **let**.

**Example**

```javascript
let number = 150;
let message = "Hello, Jack!"; 

function printMessage() {
    if (number > 100) {
        let message = "Hello, Bob!";
        console.log(message);
    }
    console.log(message);
}

printMessage();
```

**Output**

```
Hello, Bob!
Hello, Jack!
```

### Ключове слово **const**

Змінні, які було оголошено з використанням ключового слова **const**, також мають блочну область видимості.

Вони є незмінними, тобто константами. При оголошенні константи потрібно одразу присвоїти їй конкретне значення. Спроба зміни значення константи призведе до помилки.

Приклад оголошення змінних з **const**.

**Example**

```javascript
const PI = 3.14;
const COLOR_BLACK = "#000";
const myBirthday = "10.02.2000";
```

Приклад, який демонструє, що відбудеться, якщо спробувати присвоїти нове значення константі.

**Example**

```javascript
const myBirthday = "10.02.2000";

myBirthday = "12.03.2000"; // TypeError: Assignment to constant variable
```

## Одна інструкція для оголошення багатьох змінних

Використовуючи одне з ключових слів **var**, **let**, **const**, можна оголосити кілька змінних в одній інструкції. У такому разі вони повинні бути розділені комою, а тип даних при цьому може бути різним.

Оголошення кількох змінних в одній інструкції та на одному рядку.

**Example**

```javascript
let x = 10, y = 21, z = 5;
let userName = "Mykola", userAge = 15;
```

Кожна змінна розташована на новому рядку.

**Example**

```javascript
let toy = "Teddy Bear", 
toyCount = 8,
price = 100;

let userName = "Mykola", 
userAge = 15;
```

### Оголошення кількох змінних за допомогою деструктуризації

Деструктуризація дозволяє розпаковувати значення з масивів або властивості з об'єктів в окремі змінні в одному рядку. Особливо корисна при роботі з масивами та об'єктами.

Далі на прикладі з масивом показано, що:
- ліворуч від знака рівності `=` описано змінні в квадратних дужках `[]`. Це місце, де розпаковуються елементи масиву.
- праворуч вказано масив, значення якого розподіляються між змінними зліва.

**Example**

```javascript
const [x, y, z] = [10, 32, 89];
let [firstName, lastName, age] = ["James", "Brown", 43];

console.log(x);
console.log(y);
console.log(lastName);
```

**Output**

```javascript
10
32
Brown
```

## Типи даних JavaScript

Змінні можуть зберігати такі типи даних як:
- числа;
- текст; 
- логічні значення; 
- об'єкти та інші типи даних.

Рядками називають текстові значення. У JavaScript рядки можуть записуватися в подвійних, одинарних, або зворотніх лапках. Зворотні лапки надають можливість вбудовувати змінні всередину них, що продемонстровано у прикладі зі змінною `finalGreeting`.

**Example**

```javascript
let itemCount = 122; // Ціле число
let total = 68.12; // Дробове число

const name = "Alya";
let greeting = 'Hi there!';
let finalGreeting = `${greeting} My name is Pavlo.`;

let hasAccess = false;

let user = { name: "Nick", age: 30 }; // об'єкт

console.log(finalGreeting);
console.log(user);
console.log(user.age);
```

**Output**

```javascript
Hi there! My name is Pavlo.
{ name: "Nick", age: 30 }
30
```

## Області видимості JavaScript

Область видимості - область, яка визначає доступність змінних.

JavaScript має декілька областей видимості:

- глобальна;
- функціональна;
- блокова;

### Глобальна область видимості

Змінні, функції можуть використовуватися в усьому коді, де були визначені. Тобто вони доступні в різних функціях, блоках коду, у будь-якій іншій частині програми, де необхідні.

Змінні, які оголошенні з **var**, **let**, **const** мають схожу поведінку, коли оголошені поза блоком. Вони всі відносяться до глобальної області видимості.

**Example**

```javascript
var globalVar = "I am a global var";
let globalLet = "I am a global let";
const globalConst = "I am a global const";

function showGlobalVariables() {
  console.log(globalVar);   
  console.log(globalLet);  
  console.log(globalConst); 
}

function modifyVariables() {
  globalVar = "Changed global var";   
  globalLet = "Changed global let";

  console.log(globalVar);  
  console.log(globalLet);  
  console.log(globalConst); 
}

showGlobalVariables();
modifyVariables();
```

**Output**

```javascript
I am a global var
I am a global let
I am a global const
Changed global var
Changed global let
I am a global const
```

### Функціональна область видимості

Надає можливість функції мати власну область, де вона може створювати та використовувати свої змінні. Змінні, які було визначено всередині функції, не доступні поза цією функцією.

Змінні, які оголошені з **var**, **let**, **const** мають схожу поведінку, коли оголошені всередині функції. Далі наведено приклади коду оголошених змінних з цими ключовими словами. 

Проте важливо пам'ятати, що змінні, які оголошені з ключовим словом **var**, ігнорують блочну область, яка властива конструкціям `if`, `for`, `while`.

**Example**

```javascript
function processStudentData() {
  var studentName = "John Doe";  
  var studentAge = 21;         
  var studentCourse = "Computer Science";

  if (studentAge > 18) {
    var status = "Adult";

    console.log(`Status inside if: ${status}`);
  }

  console.log(`Status outside if: ${status}`);
  console.log(`Student: ${studentName}, Age: ${studentAge}, Course: ${studentCourse}`);
}

processStudentDataVar();
```

**Output**

```javascript
Status inside if: Adult
Status outside if: Adult
Student: John Doe, Age: 21, Course: Computer Science
```

Приклад, де демонструється область видимості змінної із ключовим словом **let**.

**Example**

```javascript
function processProductData() {
  let productName = "Laptop";    
  let productQuantity = 3;       
  let productPrice = 500;        
  let totalPrice = productQuantity * productPrice;

  if (productQuantity > 2) {
    let discount = 0.1; 
    totalPrice = totalPrice * (1 - discount);

    console.log(`Discount applied inside if: ${discount * 100}%`);
  }

  // console.log(`Discount outside if: ${discount}`); // ReferenceError: discount is not defined
  console.log(`Product: ${productName}, Quantity: ${productQuantity}, Price per item: $${productPrice}`);
  console.log(`Total Price: $${totalPrice}`); 
}

processProductDataLet();
```

**Output**

```javascript
Discount applied inside if: 10%
Product: Laptop, Quantity: 3, Price per item: $500
Total Price: $1350
```

Приклад змінних, оголошених за допомогою ключового слова **const**.

**Example**

```javascript
function processInstrumentData() {
  const instrumentName = "Guitar";  
  const instrumentType = "String";  
  const instrumentPrice = 200;      

  console.log(`Instrument: ${instrumentName}, Type: ${instrumentType}, Price: $${instrumentPrice}`); 
}

processInstrumentDataConst();
```

**Output**

```javascript
Instrument: Guitar, Type: String, Price: $200
```

## Блокова область видимості

До 2015 року JavaScript мав тільки глобальну та функціональну область видимості.

Введення блокової області видимості через `let` і `const` в ECMAScript 6 забезпечило кращий контроль над видимістю змінних у межах блоків коду. Це дозволяє писати чистий, надійній код, де змінні обмежуються своїм блоком та не можуть випадково змінюватися або впливати на інші частини програми.

Змінні, які оголошені всередині блоку `{ }`, недоступні за його межами.

Змінні, оголошені всередині функції JavaScript, є *локальними* для цієї функції. Локальні змінні мають область видимості, обмежену межами функції:

- до локальних змінних можна звертатися тільки зсередини функції, у якій вони оголошені;
- оскільки кожна функція має власну область видимості, змінні з однаковими іменами можуть використовуватися в різних функціях без конфліктів. 

Локальні змінні створюються під час виклику функції й автоматично видаляються після її завершення.

**Example**

```javascript
function calculateTotal(price, quantity) {
  let total = price * quantity;
  
  if (total > 150) {
    let discount = 0.1;  
    total *= (1 - discount); 
    console.log(`Discount applied: ${discount * 100}%`);
  }

  console.log(`Total price: $${total}`);
}

calculateTotal(80, 2); 
calculateTotal(100, 2);
```

**Output**

```javascript
Total price: $160  
Discount applied: 10%
Total price: $180 
```

## Правила іменування змінних JavaScript

При оголошенні змінних важливо дотримуватися правил іменування.

- Ім’я може містити букви, цифри, символи `$` і `_`.
- Перший символ імені не повинен бути числом.
- Змінна повинна мати чітке, зрозуміле ім'я. Наприклад, для збереження даних про користувача: `lastName`, `firstName`.
- При створенні імені, яке складається з кількох слів, зазвичай використовується `camelCase` (верблюжий регістр).
- JavaScript має свій список зарезервованих слів, які не дозволяється використовувати для імені змінної.
- Імена змінних чутливі до регістру. Наприклад, `age`та `AGE`є різними змінними.

## JavaScript Знак долара $

У JavaScript знак долара не має чітко визначеного призначення та не використовується як стандартний оператор мови програмування. Його значення визначається завдяки застосуванню в популярних бібліотеках і фреймворках, а також з його прийняття в якості допустимого символу в іменах змінних і функцій.

У JavaScript змінні, що починаються зі знака долара ($), можуть використовуватися для позначення об'єктів jQuery або для виокремлення їх серед інших типів змінних.

```javascript
let $paragraphs = $('p'); // Елемент обирається за типом
const $element = $('#myElement'); // Елемент обирається за ідентифікатором

$element.addClass('selected'); // Додавання класу
$element.removeClass('selected'); // Видалення класу
```

Знак долара використовується в шаблонних літералах, які були введені в ECMAScript 6 (ES6) для зручної інтерполяції рядків і роботи з багаторядковими текстами в JavaScript.

Шаблонні літерали оформлюються за допомогою зворотних лапок. Вони дозволяють вставляти вирази в рядок, використовуючи заповнювачі у форматі `${вираз}`.


**Example**

```javascript
let x = 10;
let y = 20;
let sum = `The sum of ${x} and ${y} is ${x + y}.`;
console.log(sum);
```

**Output**

```javascript
The sum of 10 and 20 is 30.
```

## JavaScript Підкреслення _

Символ підкресення не часто використовується в JavaScript.

Він може бути використаний при позначенні змінної як приватної.

**Example**

```javascript
let _firstName = "Olya";
let _lastName = "Black";
```

Цей символ може бути замінником змінної. Підкреслення вказує, що змінна є тимчасовою та слугує для певної мети, наприклад, для ітерації або вона є параметром зворотного виклику.

Далі наведено приклад його використання. Функція, яка визначена за допомогою синтаксису стрілочної функції. Вона приймає будь-яку кількість аргументів, що передаються в масив `args`. 

Метод масиву `args.find()`, який шукає перший елемент, що задовольняє умови:

- `!isNaN(_)`. Функція `isNaN()` перевіряє, чи є значення не числом (NaN). Оскільки використовується `!`, умова перевіряє, чи є значення числом.
- `typeof _ === "number"`. `typeof` визначає тип змінної, потім відбувається порівняння його з рядком `"number"`, щоб переконатися, що елемент є саме числом.

Підкреслення `_` представляє кожен окремий аргумент під час ітерації через масив `args`.

**Example**

```javascript
const findValidNumber = (...args) => 
  args.find(_ => !isNaN(_) && typeof _ === "number");
```

Та сама функція, але із вказаною назвою змінної. Такий варіант більше поширений на практиці.

**Example**

```javascript
const findValidNumber = (...args) => 
  args.find(arg => !isNaN(arg) && typeof arg === "number");
```

## Поширені запитання про змінні в JavaScript

### 1. Що таке змінна в JavaScript?

Вона є контейнером, який дозволяє зберігати дані будь-якого типу. Наприклад, рядки, числа, масиви тощо.

### 2. Яка різниця між var, let та const?

Змінна, яка оголошена за допомогою ключового слова `var`, має або функціональну, або глобальну область видимості. Вона є видимою за межами блоку.

`let` та `const`, які представлені в стандарті ES 6, мають блочну область видимості. Вони у свою чергу не надають можливості оголошувати змінну знову в тій самій області видимості.

Значення змінної, яка оголошена з `const`, не можна змінити після ініціалізації. Це ключове слово використовується для оголошення незмінних значень.

### 3. Чи можна змінити значення змінної, оголошеної через const?

Значення змінної, яка оголошена через `const`, не можна змінити після її ініціалізації. У разі, якщо змінна містить об'єкт або масив, то можна змінювати його вміст, тобто властивості чи елементи, але не саму змінну.

### 4. Що таке область видимості змінних?

Область видимості визначає, де змінна доступна в програмі. 
