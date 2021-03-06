# Câu hỏi phỏng vấn TypeScript

![](./assets/logo.png)

TypeScript là một dự án mã nguồn mở được phát triển bởi Microsoft, nó có thể được coi là một phiên bản nâng cao của Javascript bởi việc bổ sung tùy chọn kiểu tĩnh và lớp hướng đối tượng mà điều này không có ở Javascript. Nó có thể chạy ở bất cứ trình duyệt, hệ điều hành hay nền tảng nào. Mọi thứ dùng được code JavaScript thì cũng dùng được TypeScript. 

## Tại sao lại dùng TypeScript?

- **Dễ phát triển dự án lớn:** Với việc sử dụng các kỹ thuật mới nhất và lập trình hướng đối tượng nên TypeScript giúp chúng ta phát triển các dự án lớn một cách dễ dàng.
- **Nhiều Framework lựa chọn:** Hiện nay các Javascript Framework đã dần khuyến khích nên sử dụng TypeScript để phát triển, ví dụ như Angular và NestJs.
- **Hỗ trợ các tính năng của Javascript phiên bản mới nhất:** TypeScript luôn đảm bảo việc sử dụng đầy đủ các kỹ thuật mới nhất của Javascript, ví dụ như version hiện tại là ECMAScript 2015 (ES6).
- **Là mã nguồn mở:** TypeScript là một mã nguồn mở nên bạn hoàn toàn có thể sử dụng mà không mất phí, bên cạnh đó còn được cộng đồng hỗ trợ.
- **TypeScript là JavaScript:** Bản chất của TypeScript là biên dịch tạo ra các đoạn mã javascript nên ban có thê chạy bất kì ở đâu miễn ở đó có hỗ trợ biên dịch Javascript. Ngoài ra bạn có thể sử dụng trộn lẫn cú pháp của Javascript vào bên trong TypeScript, điều này giúp các lập trình viên tiếp cận TypeScript dễ dàng hơn.

![](./assets/Typescript_Compilation_Process.png)

TypeScript sử dụng file mở rộng `.ts`, tương tự với `.js` ở file JavaScript. Ở đây là chương trình cộng hai số trong TypeScript.

```ts
function add(a: number, b: number): number {
    const sum = a + b;
    return sum;
}
```

Khi ta biên dịch file TypeScript với lệnh `tsc`, trình biên dịch TypeScript tạo file JavaScript tương ứng. 

```js
function add(a, b) {
    const sum = a + b;
    return sum;
}
```

![](./assets/Typescript.png)

TypeScript có tất cả tính năng của JavaScript đồng thời bổ sung thêm các tính năng static typing, interface, class, modules và generics. TypeScript hoàn toàn là một công cụ compile-time. Khi biên dịch, chương trình sẽ chỉ còn là JavaScript đơn giản. TypeScript là một ngôn ngữ để phát triển quy mô ứng dụng JavaScript.

![](./assets/Typescript_Artboard_3.png)

## Câu hỏi phỏng vấn TypeScript cho Freshers

### 1. Các kiểu nguyên thuỷ trong TypeScript?

Trong TypeScript có loại kiểu dữ liệu là kiểu có sẵn (built-in) và kiểu người dùng định nghĩa (user-defined).

* Built-in:
    - string
    - number
    - boolean
    - void
    - symbol
    - null & undefined
* User-defined:
    - arrays
    - enums
    - classes
    - interfaces

![](./assets/Typescript_Types.png)

### 2. Giải thích các mảng làm việc trong TypeScript?

Ta sử dụng mảng cho lưu trữ các giá trị cùng kiểu. Mảng là tập hợp giá trị có thứ tự và được đánh chỉ mục. Phần tử đầu tiên có chỉ mục là 0, kế tiếp là 1, ....

Cú pháp khai báo và khởi tạo mảng trong TypeScript:

```ts
let values: number[] = [];
values[0] = 10;
values[1] = 20;
values[2] = 30;
```

Ta có thể tạo mảng với cú pháp đơn giản hơn:

```ts
let values: number[] = [15, 20, 25, 30];
```

Hoặc là dùng từ khoá Array:

```ts
let values: Array<number> = [15, 20, 25, 30];
```

### 3. Kiểu any là gì?

Khi bạn muốn lưu một biến mà không biết trước kiểu của biến đó. Ví dụ, giá trị từ lệnh gọi API hoặc đầu vào người dùng. Kiểu `any` cho phép gán bất kỳ giá trị nào cho biến.

```ts
let person: any = "Foo";
```

Ví dụ:

```ts
// json may come from a third-party API
const employeeData: string = `{"name": "John Doe", "salary": 60000}`;

// parse JSON to build employee object
const employee: any = JSON.parse(employeeData);

console.log(employee.name);
console.log(employee.salary);
```

### 4. Kiểu void là gì?

Void cho biết sự vắng mặt của kiểu với biến. Nó hoạt động như đối lập với bất kỳ kiểu nào. Nó hữu ích cho các hàm không trả về giá trị.

```ts
function notify(): void {
    alert("The user has been notified.");
}
```

### 5. Kiểu unknown là gì?

### 6. Các cách khai báo biến trong TypeScript?

**var** khai báo một biến cục bộ hoặc toàn cục. Bạn có thể thiết lập giá trị khi khai báo. Các hành vi và phạm vi của nó tương tự với ở JavaScript. Ví dụ:

```ts
var foo = "bar";
```

**let** khai báo biến cục bộ. Tương tự var, bạn có thể thiết lập giá trị biến khi khai báo. Ví dụ:

```ts
let a = 5;

if (true) {
    let a = 10;
    console.log(a);  // 10
}
console.log(a);  // 5
```

**const** khai báo hằng cục bộ không thể thay đổi sau khi khởi tạo.

```ts
const a = 5;

if (true) {
    a = 10; // Error: Cannot assign to 'a' because it is a constant.(2588)
} 
```

### 7. Cung cấp cú pháp cho hàm với chú thích kiểu

Hàm là các khối code để thực hiện một code cụ thể. Các hàm có thể tùy ý nhận một hoặc nhiều tham số, xử lý chúng và tùy chọn trả về một giá trị. Trong TypeScript hàm cần có chú thích kiểu là kiểu giá trị trả về của hàm.

```ts
function greet(name: string): string {
  return `Hello, ${name}`;
}

let greeting = greet("Anders");
console.log(greeting);  // "Hello, Anders"
```

### 8. Cách tạo đối tượng trong TypeScript?

Đối tượng là một tập hợp key/value. Key là duy nhất. Nó gần tương đồng với mảng nên còn gọi là mảng liên kết. Tuy nhiên, mảng sử dụng chỉ mục là giá trị số, trong khi đối tượng cho phép bất kỳ kiểu dữ liệu nào là key.

Trong TypeScript, kiểu đối tượng đề cập đến bất kỳ thuộc tính nào. Nó có thể định nghĩa danh sách thuộc tính và kiểu của nó. Ví dụ:

```ts
let pt: { x: number; y: number } = {
  x: 10,
  y: 20
};
```

### 9. Tuỳ chọn thuộc tính trong TypeScript?

Một đối tượng có thể có thuộc tính tuỳ chọn (có hoặc không có) bằng cách thêm `?` sau tên thuộc tính.

```ts
let pt: { x: number; y: number; z?: number } = {
  x: 10,
  y: 20
};
console.log(pt);
```

Trong ví dụ trên, thuộc tính `z` là tuỳ chọn, trình biên dịch không bắt buộc ta cung cấp khi khởi tạo đối tượng.

### 10. Giải thích khái niệm null trong TypeScript?

Trong lập trình, giá trị null cho biết không có giá trị. Một biến null không trỏ đến bất kỳ đối tượng nào. Do đó, bạn không thể truy cập bất kỳ thuộc tính nào trên biến hoặc gọi một phương thức trên đó.

Trong TypeScript, giá trị null được chỉ định bằng từ khoá `null`. Ví dụ

```ts
function greet(name: string | null) {
    if (name === null) {
        console.log("Name is not provided");
    } else {
        console.log("Good morning, " + name.toUpperCase());
    }
}

var foo = null;
greet(foo); // "Name is not provided"

foo = "Anders";
greet(foo);  // "Good morning, ANDERS"
```

### 11. undefined trong TypeScript là gì?

Khi một biến được khai báo mà không tạo giá trị, nó sẽ được gán giá trị undefined. 

```ts
console.log(null == null); // true
console.log(undefined == undefined); // true
console.log(null == undefined); // true, with type-conversion
console.log(null === undefined); // false, without type-conversion
console.log(0 == undefined); // false
console.log('' == undefined); // false
console.log(false == undefined); // false
```

### 12. Giải thích kiểu never trong TypeScript?

Kiểu never trong TypeScript là một kiểu không chứa giá trị. Do đó, bạn không thể gán bất kỳ giá trị nào cho biến có kiểu never.

```ts
function error(message: string): never {
    throw new Error(message);
}
```

Câu hỏi đặt ra là tại sao cần kiểu `never` khi ta đã có `void`. Vì cả hai khá giống nhau, nhưng thực sự chúng lại là đại diện cho hai khái niệm khác nhau.

Một hàm không trả về một giá trị nào ngầm hiểu là giá trị undefined trong JavaScript. Do đó, khi ta dùng `void` với một hàm thực tế nó vẫn nhận về kiểu undefined. Để đảm bảo hàm không nhận bất cứ giá trị nào, kiểu `never` được dùng cho những trường hợp như vậy.

```ts
const test = (arg): void => {
    console.log(arg)
}

console.log(test('test'))

// "test"
// undefined
```

### 13. Cách enum hoạt động trong TypeScript?

Enums cho phép chúng ta tạo các hằng số được đặt tên. Đây là một cách đơn giản để đặt tên thân thiện hơn cho các giá trị hằng số. Một enum được định nghĩa bởi từ khóa enum, theo sau là tên và các thành viên của nó.

Ví dụ:

```ts
enum Team {
    Alpha,
    Beta,
    Gamma,
    Delta
}

let t: Team = Team.Delta;
```

Mặc định, enum bắt đầu đánh số từ 0. Bạn có thể ghi đè lên giá trị mặc định bằng cách gán giá trị cho các thành viên của nó. Ví dụ:

```ts
enum Author {
  Anders = "Anders",
  Hejlsberg = "Hejlsberg"
};
```

### 14. Toán tử typeof trong TypeScript là gì?

Tương tự JavaScript, đây là toán tử trả về kiểu dữ liệu của toán hạng.

```ts
console.log(typeof 10);  // "number"

console.log(typeof 'foo');  // "string"

console.log(typeof false);  // "boolean"

console.log(typeof bar);  // "undefined"
```

### 15. Tham số còn lại trong TypeScript?

Tham số còn lại (`...`) cho phép một hàm nhận một lượng không giới hạn tham số như là một mảng. 

```ts
function add(...values: number[]) {
    let sum = 0;
    values.forEach(val => sum += val);
    
    return sum;
}

const sum = add(5, 10, 15, 20);
console.log(sum);  // 50
```