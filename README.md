
# Function
## Function là gì
Function (hàm) là tập hợp các đoạn code dùng để thực hiện một tác vụ cụ thể nào đó.
Cú pháp định nghĩa function
```js
//Định nghĩa function
function sayHello() {
    console.log("Hello")
}
```
Thực thi function 
```js
sayHello()
```

## Một số loại function
Function có các loại sau
* Function có tham số,hoạc không có tham số
* Function có giá trị trả về hoặc không

### 1. Function không có tham số
```js
function sayHello() {
    console.log("Xin chào các bạn");
}

sayHello();
```
### Function có tham số
Với function kiểu này có thể một hoặc nhiều tham số(Không nên quá 3 tham số)

```js
//Function có một tham số
function sayHelloWithName (name) {
    console.log(`Xin Chào ${name}`)
}

sayHelloWithName ("Nguyễn Văn A")
sayHelloWithName("Trần Thị C")

//function 2 tham số
function sayHelloWithNameAndYear(name, year) {
    console.log(`Xin Chào ${name}. Năm nay ${2022-year} tuổi`)
}
sayHelloWithNameAndYear("Hoàng Hồng", 2003)
```
### 3. Function trả về kết quả
Để trả về kêt quả , sử dụng từ khóa **return** 
```js
//function có trả về kết quả
//function tính tổng 2 số bất kì
function sum(num1=10, num2=20) {
    let result = num1 + num2;

    console.log(num1)
    console.log(num2)

    return result;//các câu lệnh đừng sau từ khóa "RETURN" sẽ không đc thực thi

    console.log(num1)
    console.log(num2)
}

//Thực thi 
let data = sum(3, 4)
console.log(data)

console.log(sum(5,6))
console.log(sum(data,5))

console.log(sum())//Truyền thiếu 2 giá trị => num1 = 10, num2 = 20; 
console.log(sum(3))//Truyền thiếu 1 giá trị => num1 = 3, num2 = 20;
console.log(sum(2,3))//Truyền đủ giá trị => num1 = 2, num2 = 3;
```

### 4. Functiion không trả về kết quả
Đới với function không có từ khóa **return** thì coi như là function đó không trả về kết quả

## Default Parameter ES6
Cho phép khởi tạo function với những default value nếu như chúng được định nghĩa sai.

Khi sử dụng chức năng này sẽ giúp function dễ control và ít error hơn.

Ví dụ:
```js
function sayHello(name = "Nhaaoj tên") {
    console.log(`Xin chào ${name}`);
}

sayHello(); // Nhập tên
sayHello("Hoàng Hồng"); // Hoàng Hồng

```
## Phạm vi của biến(Scope)
```js
//Phạm vi sử dụng biến

//Biến Global
let number = 100
let name ="Hoàng Hồng"

console.log(number)
console.log(name)

//Function scope
function anSang (){
    let monAn = "Phở"//Thiếu "let" biến monAn trở thành biến Global 
    console.log(monAn)
}

anSang()

//Block Scope
{
    let message = "Hôm nay trời đẹp quá"
    console.log(message)
}
``` 
## Kiểu dữ liệu Boolean
Giá trị của kiểu dữ liệu này chỉ có thể là **true** hoặc **false**

Ví dụ
```js
let a = true;
let b = false;
let c = !a;
let d = !b;
```
## Xác định giá trị Boolean
Để xác định giá trị boolean cho biến, biểu thức,… ta sử dụng hàm **Boolean()**

Ví dụ
```js
let a = 5;
console.log(Boolean(a));

let b = 6;
let c = 10;
console.log(Boolean(b < c));
```

## Truthy & Falthy value
**Truthy value** là những giá trị mà khi ép kiểu về Boolean thì sẽ cho ra giá trị là **true**.

Ngược lại, **Falsy value** là những giá trị mà khi ép kiểu về Boolean thì cho ra giá trị là **falthy**

Note:

Có **6 giá trị** sau được coi là **falsy : false, 0, NaN, ‘’, null, undefined**
Các giá trị còn lại, ngoài các giá trị trên được gọi là **truthy**
```js
console.log(Boolean(false)); // false

console.log(Boolean(0)); // false

console.log(Boolean(NaN)); // false

console.log(Boolean("")); // false

console.log(Boolean(null)); // false

console.log(Boolean(undefined)); // false

```

## Câu lệnh điều kiện if - else if - else

### Câu lệnh if
Thực hiện câu lệnh trong if nếu điều kiện cho trước là đúng.
```js
// Cú pháp
if (điều kiện) {
    // Code được thực thi nếu điều kiện đúng
}

// Ví dụ
let hour = 6;
if (hour < 10) {
    console.log("Good morning!");
}
```
### Câu lệnh if - else
Nếu điều kiện đúng thực hiện câu lệnh trong if, ngược lại nếu điều kiện sai thì hiện câu lệnh trong else.
```js
// Cú pháp
if (điều kiện) {
    // Code được thực thi nếu điều kiện đúng
} else {
    // Code được thực thi nếu điều kiện sai
}

// Ví dụ
let hour = 6;
if (hour < 12) {
    console.log("Good morning!");
} else {
    console.log("Good afternoon!");
}
```
### Câu lệnh if - else if - else
Chỉ định một điều kiện mới nếu điều kiện đầu tiên là sai
```js
// Cú pháp
if (điều kiện 1) {
    // Code được thực thi nếu điều kiện 1 đúng
} else if (điều kiện 2) {
    // Code được thực thi nếu điều kiện 1 sai và điều kiện 2 đúng
} else {
    // Code được thực thi nếu điều kiện 1 và 2 sai
}

// Ví dụ
let hour = 6;
if (hour < 12) {
    console.log("Good morning!");
} else if (hour >= 12 && hour < 18) {
    console.log("Good afternoon!");
} else {
    console.log("Good evening!");
}
```
### Sự khác nhau giữa `==` và `===`
* `==` so sánh về giá trị 
* `===` so sánh về cả giá trị và kiểu giữ liệu

### Toán tử 3 ngôi : condition ? true : false
Toán tử 3 ngôi trong JavaScript cho phép chúng ta kiểm tra một điều kiện nào đó trong một dòng code duy nhất và trả về giá trị, thay vì phải sử dụng nhiều câu lệnh if-else, giúp cho việc code đơn giản và thông minh hơn.

Cú pháp
```js
condition ? true_value : false_value;
```
Trong đó:

**condition** : Biểu thức điều kiện
**true_value** : Được trả về nếu điều kiện đúng
**false_value** : Được trả về nếu điều kiện sai
**Condition = true** thực thi câu lệnh đằng sau dấu `?`
**Condition = false** thực thi câu lệnh đằng sau dấu `:`
```js
let hour = 20
hour < 12  ? console.log("Chào buổi sáng") : console.log(" Chào buổi chiều")
```
