# learn-typescript

Tôi sử dụng repo này để theo dõi tất cả các bài học tôi đã học về `typescript`

## Tài liệu tham khảo

- https://www.typescriptlang.org/docs

- https://www.w3schools.com/typescript/index.php

## Công cụ playground trực tuyến

- https://www.typescriptlang.org/play/

## TypeScript là gì?

`TypeScript` là một "Syntactic Superset" có nghĩa là nó chia sẻ cùng cú pháp cơ bản với `JavaScript`, nhưng bổ sung thêm một số tính năng.

## Tại sao nên sử dụng TypeScript?

`JavaScript` là một ngôn ngữ có kiểu dữ liệu lỏng lẻo. Điều này có thể khiến việc hiểu rõ các loại dữ liệu đang được truyền trong `JavaScript` trở nên khó khăn.

Trong `JavaScript`, các tham số của hàm và biến không có bất kỳ thông tin nào về kiểu dữ liệu! Vì vậy, các nhà phát triển cần xem tài liệu hoặc đoán dựa trên cách triển khai.

`TypeScript` cho phép chỉ định các kiểu dữ liệu đang được truyền trong mã và có khả năng báo lỗi khi các kiểu dữ liệu không khớp.
Ví dụ, `TypeScript` sẽ báo lỗi khi truyền một chuỗi vào một hàm mong đợi một số. `JavaScript` thì không.

`TypeScript` sử dụng kiểm tra kiểu tại thời điểm biên dịch, nghĩa là nó kiểm tra xem các kiểu đã chỉ định có khớp hay không trước khi chạy mã, chứ không phải trong khi chạy mã.

## Làm cách nào để sử dụng TypeScript?

Một cách thông dụng để sử dụng `TypeScript` là dùng trình biên dịch chính thức của `TypeScript`, trình biên dịch này chuyển đổi mã `TypeScript` thành `JavaScript`.

Một số trình chỉnh sửa mã phổ biến, chẳng hạn như `Visual Studio Code`, có tích hợp sẵn hỗ trợ `TypeScript` và có thể hiển thị lỗi khi bạn viết mã!

## Trình biên dịch TypeScript

`TypeScript` được chuyển đổi thành `JavaScript` có nghĩa là nó có thể chạy ở bất kỳ đâu mà `JavaScript` chạy!

### Cài đặt trình biên dịch

TypeScript có một trình biên dịch chính thức có thể được cài đặt thông qua npm.

```typescript
    npm install typescript --save-dev
```

Trình biên dịch được cài đặt trong thư mục `node_modules` và có thể chạy bằng lệnh: npx tsc.

```typescript
    npx tsc
```

### Cấu hình trình biên dịch

Theo mặc định, trình biên dịch `TypeScript` sẽ hiển thị thông báo trợ giúp khi chạy trong một dự án trống.

Trình biên dịch có thể được cấu hình bằng cách sử dụng tệp `tsconfig.json`.

Có thể để `TypeScript` tạo tệp `tsconfig.json` với các cài đặt được khuyến nghị bằng lệnh sau:

```typescript
    npx tsc --init
```

## TypeScript các Types đơn giản

### TypeScript hỗ trợ một số kiểu dữ liệu đơn giản (primitive) mà bạn có thể đã biết:

Có ba kiểu dữ liệu nguyên thủy chính trong `JavaScript` và `TypeScript`:

- boolean: Các giá trị đúng hoặc sai.

```typescript
let isActive: boolean = true;
```

- number: Các số nguyên và số thập phân.

```typescript
let age: number = 25;
let price: number = 19.99;
```

- string: Các giá trị chuỗi văn bản.

```typescript
let message: string = "HQGROUP";
```

Ngoài ra, còn có hai kiểu dữ liệu nguyên thủy ít phổ biến hơn được sử dụng trong các phiên bản `JavaScript` và `TypeScript` sau:

- bigint: Các số nguyên lớn hơn, cho phép các giá trị lớn hơn nhiều so với kiểu `number`.

```typescript
let largeNumber: bigint = 1234567890123456789012345678901234567890n;
```

\*symbol: Được sử dụng để tạo một định danh toàn cầu duy nhất.

```typescript
let uniqueId: symbol = Symbol("description");
```

## Cách triển khai biến.

Khi tạo một biến trong `TypeScript`, có hai cách chính để gán kiểu dữ liệu:

- Explicit

```typescript
let firstName: string = "Dylan";
```

- Implicit

```typescript
let firstName = "Dylan";
```

Lưu ý: Việc để `TypeScript` "đoán" kiểu dữ liệu của một giá trị được gọi là suy diễn kiểu (infer).

## Lỗi khi gán type cho biến.

### TypeScript sẽ báo lỗi nếu các kiểu dữ liệu không khớp.

```typescript
let firstName: string = "Dylan"; // type string
firstName = 33; // attempts to re-assign the value to a different type
```

Gán kiểu dữ liệu ngầm định có thể khiến `firstName` ít nổi bật hơn như một chuỗi, nhưng cả hai cách đều sẽ báo lỗi nếu kiểu dữ liệu không khớp:

```typescript
let firstName: string = "Alice"; // Gán kiểu rõ ràng
let firstName = "Alice"; // Gán kiểu ngầm định (suy diễn)

firstName = 123; // Lỗi: Không thể gán kiểu number cho kiểu string

firstName;
```

Trong cả hai trường hợp, `TypeScript` sẽ báo lỗi nếu bạn cố gắng gán một giá trị không khớp với kiểu dữ liệu đã chỉ định hoặc suy diễn.

### Không thể suy luận

Lưu ý: Bạn có thể thấy các kiểu dữ liệu nguyên thủy được viết hoa như `Boolean`.

boolean !== Boolean

Đối với hướng dẫn này, hãy chỉ sử dụng các kiểu dữ liệu viết thường (`boolean`, `number`, `string`, v.v.). Các kiểu viết hoa (`Boolean`, `Number`, `String`) thường được sử dụng trong các hoàn cảnh rất cụ thể và không phải là kiểu dữ liệu chính để khai báo biến trong `TypeScript`.

## Các Kiểu Dữ Liệu Đặc Biệt trong TypeScript.

### Type: any

`any` là một kiểu dữ liệu trong `TypeScript` vô hiệu hóa kiểm tra kiểu và cho phép sử dụng mọi kiểu dữ liệu.
Ví dụ dưới đây không sử dụng `any` và sẽ gây ra lỗi:

```typescript
let u = true;
u = "string"; // Lỗi: Kiểu 'string' không thể gán cho kiểu 'boolean'.
Math.round(u); // Lỗi: Đối số kiểu 'boolean' không thể gán cho tham số kiểu 'number'.
```

Việc gán giá trị any cho kiểu dữ liệu đặc biệt `any` sẽ vô hiệu hóa kiểm tra kiểu dữ liệu:

```typescript
let u: any = true;
u = "string"; // Không có lỗi
Math.round(u); // Không có lỗi
```

`any` có thể là một cách hữu ích để vượt qua các lỗi vì nó vô hiệu hóa kiểm tra kiểu dữ liệu, nhưng `TypeScript` sẽ không thể cung cấp tính an toàn kiểu dữ liệu. Ngoài ra, các công cụ phụ thuộc vào dữ liệu kiểu, như tính năng tự động hoàn thành, sẽ không hoạt động. Hãy nhớ rằng, nên tránh sử dụng `any` bằng mọi giá...

### Type: unknown

`unknown` là một giải pháp an toàn hơn so với `any`, vì nó buộc bạn phải xử lý kiểu dữ liệu một cách rõ ràng trước khi sử dụng, tránh những lỗi tiềm ẩn khi kiểu dữ liệu không được kiểm tra.

```typescript
let u: unknown;
u = "string";
u = true;

Math.round(u); // Lỗi: Đối số kiểu 'unknown' không thể gán cho tham số kiểu 'number'.
```

`unknown` là lựa chọn tốt nhất khi bạn không biết trước kiểu dữ liệu sẽ được sử dụng. Để thêm kiểu dữ liệu sau này, bạn cần phải ép kiểu.
Ép kiểu là khi chúng ta sử dụng từ khóa `as` để chỉ định rằng một thuộc tính hoặc biến là của kiểu dữ liệu đã được ép.

```typescript
let u: unknown = "Hello, TypeScript";

// Ép kiểu `u` thành kiểu `string` để sử dụng
let s: string = u as string;

console.log(s.toUpperCase()); // Kết quả: "HELLO, TYPESCRIPT"
```

### Type: never

`never` là một kiểu đặc biệt trong `TypeScript`, đại diện cho các giá trị không bao giờ xảy ra. Khi một hàm hoặc đoạn mã có kiểu trả về là `never`, điều đó có nghĩa là nó không bao giờ hoàn thành một cách bình thường; thay vào đó, nó có thể ném ra một lỗi hoặc chạy mãi mãi.

```typescript
let x: never = true;
// Lỗi: Kiểu 'boolean' không thể gán cho kiểu 'never'.
```

`never` thường ít được sử dụng, đặc biệt khi nó đứng một mình. Sử dụng chính của `never` là trong các tình huống `generics` nâng cao.

```typescript
type IfTrue<T> = T extends true ? never : string;

function handleValue<T>(value: IfTrue<T>): void {
  // Hàm này sẽ chỉ chấp nhận giá trị kiểu `string` nếu `T` không phải là `true`
}
```

### Type: undefined & null

`undefined` và `null` là các kiểu dữ liệu đại diện cho các giá trị nguyên thủy `undefined` và `null` trong `JavaScript`.

các kiểu dữ liệu `undefined` và `null` không có nhiều ứng dụng nếu `strictNullChecks` không được bật trong tệp `tsconfig.json`.

`strictNullChecks`: Khi tùy chọn này được bật trong tsconfig.json, `TypeScript` yêu cầu bạn phải xử lý rõ ràng các giá trị `null` và `undefined`. Điều này có nghĩa là các biến với kiểu dữ liệu khác không tự động chấp nhận giá trị `null` hoặc `undefined` trừ khi được khai báo rõ ràng.

```typescript
{
  "compilerOptions": {
    "strictNullChecks": true
  }
}
```

```typescript
let a: string;
a = "Hello"; // Đúng
a = undefined; // Lỗi: Kiểu 'undefined' không thể gán cho kiểu 'string'
a = null; // Lỗi: Kiểu 'null' không thể gán cho kiểu 'string'
```

Để cho phép `null` và `undefined`, bạn có thể khai báo biến với `union type`:

```typescript
let b: string | null;
b = "Hello"; // Đúng
b = null; // Đúng
```

Khi `strictNullChecks` không bật, `TypeScript` tự động cho phép `null` và `undefined` trong hầu hết các tình huống, điều này có thể dẫn đến các lỗi không được phát hiện sớm. Bằng cách bật `strictNullChecks`, bạn có thể đảm bảo mã của mình được xử lý cẩn thận hơn và giảm nguy cơ gặp phải lỗi liên quan đến các giá trị `null` và `undefined`.

## TypeScript Arrays

### Khai Báo Mảng

#### Khai Báo Mảng Với Kiểu Dữ Liệu:

```typescript
let numbers: number[] = [1, 2, 3, 4, 5];
let names: string[] = ["Alice", "Bob", "Charlie"];
```

#### Sử Dụng Array<T>:

```typescript
let numbers: Array<number> = [1, 2, 3, 4, 5];
let names: Array<string> = ["Alice", "Bob", "Charlie"];
```

### Truy Cập và Thao Tác Với Mảng

#### Truy Cập Các Phần Tử:

```typescript
let firstNumber = numbers[0]; // 1
let secondName = names[1]; // "Bob"
```

#### Thay Đổi Các Phần Tử:

```typescript
numbers[2] = 10; // [1, 2, 10, 4, 5]
```

#### Các Phương Thức Mảng:

`TypeScript` hỗ trợ các phương thức mảng tiêu chuẩn của `JavaScript`, chẳng hạn như `push`, `pop`, `shift`, `unshift`, `map`, `filter`, và `reduce`:

```typescript
numbers.push(6); // [1, 2, 10, 4, 5, 6]
names.pop(); // ["Alice", "Bob"]
let upperCaseNames = names.map((name) => name.toUpperCase()); // ["ALICE", "BOB"]
```

### Mảng và Generics

Bạn có thể sử dụng `generics` để tạo các kiểu mảng tùy chỉnh:

```typescript
function createArray<T>(items: T[]): T[] {
  return new Array<T>().concat(items);
}

let numberArray = createArray<number>([1, 2, 3]);
let stringArray = createArray<string>(["a", "b", "c"]);
```

### Tuple (Tuple Arrays)

`Tuple` là một kiểu mảng đặc biệt cho phép bạn định nghĩa một mảng với các kiểu dữ liệu khác nhau ở các vị trí khác nhau:

```typescript
let tuple: [number, string, boolean] = [1, "hello", true];
```

### Kiểm Tra Kiểu

`TypeScript` cung cấp tính năng kiểm tra kiểu để đảm bảo rằng các phần tử trong mảng đều thuộc cùng một kiểu dữ liệu:

```typescript
let validArray: number[] = [1, 2, 3]; // Đúng
let invalidArray: number[] = [1, "two", 3]; // Lỗi: Kiểu 'string' không thể gán cho kiểu 'number'
```

### Readonly

Từ khóa chỉ đọc có thể ngăn chặn việc thay đổi mảng.

```typescript
const names: readonly string[] = ["Dylan"];
names.push("Jack");
// Lỗi: Thuộc tính 'push' không tồn tại trên kiểu 'readonly string[]'.

// thử bỏ từ khóa readonly và xem liệu nó có hoạt động không?
```

### Type Inference

`TypeScript` có thể suy luận kiểu của một mảng nếu mảng đó có các giá trị.

```typescript
let numbers = [1, 2, 3];
// TypeScript suy luận kiểu của `numbers` là `number[]`

let mixedArray = [1, "two", true];
// TypeScript suy luận kiểu của `mixedArray` là `(number | string | boolean)[]`

const numbers = [1, 2, 3]; // suy luận kiểu là number[]
numbers.push(4); // không có lỗi
// comment dòng dưới để xem phép gán thành công
numbers.push("2"); // Lỗi: Đối số có kiểu 'string' không thể gán cho tham số có kiểu 'number'.
let head: number = numbers[0]; // không có lỗi
```

## TypeScript Tuples

### Typed Arrays

`Tuple` là một mảng có kiểu với độ dài và kiểu dữ liệu được xác định trước cho từng chỉ số.
`Tuples` rất hữu ích vì chúng cho phép mỗi phần tử trong mảng là một kiểu giá trị đã biết.
Để định nghĩa một `Tuple`, chỉ định kiểu của từng phần tử trong mảng:

```typescript
// định nghĩa tuple của chúng ta
let ourTuple: [number, boolean, string];

// khởi tạo đúng cách
ourTuple = [5, false, "Coding God was here"];
```

Mặc dù chúng ta có một giá trị `boolean`, `string`, và `int`, nhưng thứ tự quan trọng trong `tuple` của chúng ta và sẽ gây ra lỗi nếu sắp xếp sai.

```typescript
// define our tuple
let ourTuple: [number, boolean, string];

// initialized incorrectly which throws an error
ourTuple = [false, "Coding God was mistaken", 5];
```

### Readonly Tuple

Một tuple `readonly` trong `TypeScript` đảm bảo rằng các phần tử của tuple không thể bị thay đổi sau khi khởi tạo. Điều này đặc biệt hữu ích khi bạn muốn đảm bảo tính bất biến của dữ liệu trong `tuple`.

#### Khai Báo Tuple Readonly

Để khai báo một tuple readonly, bạn sử dụng từ khóa readonly trước định nghĩa kiểu của tuple:

```typescript
const tuple: readonly [number, string, boolean] = [1, "hello", true];
```

#### Đặc Điểm Của Tuple Readonly

Phần Tử Không Thay Đổi: Sau khi tuple `readonly` được khởi tạo, bạn không thể thay đổi các phần tử của nó.

Không Có Phương Thức Thay Đổi: Các phương thức thay đổi `tuple`, chẳng hạn như push, pop, splice, và sort, không được phép sử dụng.

### Named Tuples

`Named tuples` cung cấp nhiều ngữ cảnh hơn về những gì các giá trị tại các chỉ số đại diện.

```typescript
const graph: [x: number, y: number] = [55.2, 41.3];
```

### Destructuring Tuples

Vì tuples là các mảng, chúng ta cũng có thể giải cấu trúc chúng.

```typescript
const graph: [number, number] = [55.2, 41.3];
const [x, y] = graph;
```

## Các loại Object Types trong TypeScript.

### syntax.

```typescript
const car: { type: string; model: string; year: number } = {
  type: "Toyota",
  model: "Corolla",
  year: 2009,
};
```

### Type Inference

`TypeScript` có thể suy luận kiểu của các thuộc tính dựa trên giá trị của chúng."
Điều này có nghĩa là `TypeScript` có khả năng tự động xác định kiểu dữ liệu của các thuộc tính trong `Object` dựa trên giá trị mà bạn gán cho chúng.

```typescript
const car = {
  type: "Toyota",
};
car.type = "Ford"; // không có lỗi
car.type = 2; // Lỗi: Loại 'number' không thể gán cho loại 'string'.
```

### Các thuộc tính tùy chọn.

Trong `TypeScript`, thuộc tính tùy chọn là những thuộc tính mà không bắt buộc phải có trong một đối tượng. Để khai báo một thuộc tính là tùy chọn, bạn thêm dấu hỏi ? sau tên thuộc tính. Ví dụ:

- Ví dụ không có thuộc tính tùy chọn:

```typescript
const car: { type: string; mileage: number } = {
  // Lỗi: Thuộc tính 'mileage' bị thiếu trong kiểu '{ type: string; }' nhưng bắt buộc trong kiểu '{ type: string; mileage: number; }'.
  type: "Toyota",
};
car.mileage = 2000;
```

- Ví dụ với thuộc tính tùy chọn:

```typescript
const car: { type: string; mileage?: number } = {
  // không có lỗi
  type: "Toyota",
};
car.mileage = 2000;
```

- Ví dụ với thuộc tính tùy chọn:

```typescript
const car: { type: string; mileage?: number } = {
  // không có lỗi
  type: "Toyota",
};
car.mileage = 2000;
```

### Index Signatures (Chỉ mục).

`Index Signatures` có thể được sử dụng cho các đối tượng mà không có danh sách thuộc tính được định nghĩa sẵn."
Điều này có nghĩa là khi bạn không biết trước các thuộc tính của một đối tượng, bạn có thể sử dụng `Index Signatures` để xác định kiểu dữ liệu cho các thuộc tính đó một cách linh hoạt.

```typescript
const nameAgeMap: { [index: string]: number } = {};
nameAgeMap.Jack = 25; // không có lỗi
nameAgeMap.Mark = "Fifty"; // Lỗi: Loại 'string' không thể gán cho loại 'number'.
```

## TypeScript Enums

`Enums` là một 'lớp' đặc biệt đại diện cho một nhóm các hằng số (các biến không thể thay đổi).
`Enums` có hai dạng là chuỗi và số.

### Numeric Enums - Initialized

Trong `TypeScript`, `Numeric Enums` là kiểu enum trong đó các thành viên được gán giá trị số. Khi khởi tạo, bạn có thể chỉ định giá trị cho từng thành viên hoặc để `TypeScript` tự động gán giá trị theo thứ tự tăng dần, bắt đầu từ 0.

```typescript
enum Direction {
  Up = 1,
  Down,
  Left,
  Right,
}

console.log(Direction.Up); // Output: 1
console.log(Direction.Down); // Output: 2
console.log(Direction.Left); // Output: 3
console.log(Direction.Right); // Output: 4
```

### Numeric Enums - Fully Initialized

Bạn có thể chỉ định giá trị số cụ thể cho mỗi thành viên của enum, và nếu bạn làm vậy, `TypeScript` sẽ không tự động tăng giá trị cho các thành viên còn lại. Ví dụ:

```typescript
enum Status {
  Active = 3,
  Inactive = 7,
  Pending = 10,
}

console.log(Status.Active); // Output: 3
console.log(Status.Inactive); // Output: 7
console.log(Status.Pending); // Output: 10
```

### String Enums

`Enums` chuỗi trong `TypeScript` cho phép bạn gán các giá trị chuỗi có ý nghĩa cụ thể cho các thành viên, giúp mã dễ hiểu hơn. Ví dụ:

```typescript
enum Direction {
  Up = "UP",
  Down = "DOWN",
  Left = "LEFT",
  Right = "RIGHT",
}

console.log(Direction.Up); // Output: "UP"
console.log(Direction.Down); // Output: "DOWN"
```

- Lưu ý: Về mặt kỹ thuật, bạn có thể kết hợp và sử dụng cả giá trị chuỗi và số trong một `enum`, nhưng không được khuyến khích làm như vậy.

## TypeScript Type Aliases and Interfaces

### Type Aliases

Các `Type Aliases` cho phép định nghĩa các kiểu dữ liệu với tên tùy chỉnh (một bí danh).
Các `Type Aliases` có thể được sử dụng cho các kiểu cơ bản như chuỗi hoặc các kiểu phức tạp hơn như đối tượng và mảng.

```typescript
// Alias kiểu cho kiểu cơ bản
type ID = string;
type Age = number;

// Alias kiểu cho đối tượng
type User = {
  name: string;
  age: Age;
};

// Alias kiểu cho mảng
type UserList = User[];
```

### Interfaces

Trong `TypeScript`, `interface` được sử dụng để định nghĩa cấu trúc của các đối tượng, bao gồm các thuộc tính và phương thức mà một đối tượng phải có. Mặc dù `interface` và `type` có nhiều điểm tương đồng, `interface` chủ yếu được sử dụng cho các kiểu đối tượng và hỗ trợ mở rộng và kế thừa, trong khi `type` có thể định nghĩa nhiều kiểu khác nhau, bao gồm các kiểu cơ bản, đối tượng và mảng.

```typescript
interface User {
  name: string;
  age: number;
}

const user1: User = {
  name: "Alice",
  age: 30,
};
```

### Extending Interfaces

Trong `TypeScript`, bạn có thể mở rộng một `interface` bằng cách sử dụng từ khóa `extends`. Điều này cho phép bạn kế thừa các thuộc tính từ một `interface` hiện có và thêm các thuộc tính mới vào `interface` mở rộng.

```typescript
interface Person {
  name: string;
  age: number;
}

interface Employee extends Person {
  employeeId: string;
}

const employee1: Employee = {
  name: "Bob",
  age: 40,
  employeeId: "E123",
};
```

## TypeScript Union Types

Trong `TypeScript`, `union types` cho phép bạn định nghĩa một kiểu dữ liệu có thể là một trong nhiều loại khác nhau. Đây là cách hữu ích để mô tả các biến có thể chứa nhiều kiểu giá trị khác nhau.

Trong `TypeScript`, ký hiệu | được sử dụng để biểu diễn union type. Nó cho phép một biến hoặc thuộc tính có thể thuộc nhiều kiểu khác nhau.

```typescript
let id: string | number;

id = "abc123"; // hợp lệ
id = 456; // hợp lệ
id = true; // lỗi: Loại 'boolean' không thể gán cho loại 'string | number'
```

### Union Type Errors

Lưu ý: bạn cần phải biết kiểu dữ liệu của bạn khi sử dụng các kiểu hợp nhất để tránh lỗi kiểu dữ liệu:

```typescript
function printId(id: string | number) {
  // TypeScript không biết id là chuỗi hay số, nên bạn cần kiểm tra kiểu trước khi sử dụng
  if (typeof id === "string") {
    console.log("String ID:", id.toUpperCase()); // Hợp lệ, vì id là chuỗi
  } else {
    console.log("Number ID:", id.toFixed(2)); // Hợp lệ, vì id là số
  }
}

printId("abc123"); // Output: String ID: ABC123
printId(456); // Output: Number ID: 456.00
```

## TypeScript Functions

### Return Type

Cú pháp của `TypeScript` để định kiểu cho tham số và giá trị trả về của hàm có dạng như sau:

```typescript
// `: number` ở đây chỉ định rằng hàm này trả về một số
function getTime(): number {
  return new Date().getTime();
}
```

### Void Return Type

Kiểu `void` có thể được sử dụng để chỉ ra rằng một hàm không trả về bất kỳ giá trị nào.

```typescript
function printHello(): void {
  console.log("Hello!");
}
```

### Parameters

Các tham số của hàm được định kiểu với cú pháp tương tự như khai báo biến.

```typescript
function multiply(a: number, b: number) {
  return a * b;
}
```

Nếu không có kiểu tham số nào được định rõ, `TypeScript` sẽ mặc định sử dụng `any`, trừ khi có thông tin kiểu bổ sung như được trình bày trong các phần Tham Số Mặc Định (Default Parameters) và Type Alias dưới đây.

### Optional Parameters

Mặc định, `TypeScript` sẽ cho rằng tất cả các tham số đều là bắt buộc, nhưng chúng có thể được đánh dấu rõ ràng là tùy chọn.

```typescript
// Toán tử `?` ở đây đánh dấu tham số `c` là tùy chọn
function add(a: number, b: number, c?: number) {
  return a + b + (c || 0);
}
```

### Default Parameters

Đối với các tham số có giá trị mặc định, giá trị mặc định sẽ nằm sau chú thích kiểu.

```typescript
function pow(value: number, exponent: number = 10) {
  return value ** exponent;
}
```

`TypeScript` cũng có thể suy luận kiểu từ giá trị mặc định.

Định kiểu cho các tham số được đặt tên (named parameters) theo cùng một mẫu như định kiểu cho các tham số bình thường.

```typescript
function divide({ dividend, divisor }: { dividend: number; divisor: number }) {
  return dividend / divisor;
}
```

### Rest Parameters

Các tham số `rest` có thể được định kiểu giống như các tham số bình thường, nhưng kiểu phải là một mảng vì các tham số `rest` luôn là mảng.

```typescript
function add(a: number, b: number, ...rest: number[]) {
  return a + b + rest.reduce((p, c) => p + c, 0);
}
```

### Type Alias

Các kiểu hàm có thể được chỉ định riêng biệt khỏi các hàm thông qua type aliases.

```typescript
type Negate = (value: number) => number;

// Trong hàm này, tham số `value` tự động được gán kiểu `number` từ kiểu `Negate`
const negateFunction: Negate = (value) => value * -1;
```

## TypeScript Casting

### Casting with as

Một cách đơn giản để ghi đè kiểu của một biến là sử dụng từ khóa `as`, điều này sẽ thay đổi trực tiếp kiểu của biến đó.

```typescript
let x: unknown = "hello";
console.log((x as string).length);
```

Ghi đè kiểu thực chất không thay đổi kiểu dữ liệu bên trong biến. Ví dụ, đoạn mã sau sẽ không hoạt động như mong đợi vì biến x vẫn giữ kiểu số (number):

```typescript
let x: number = 10;
let y: string = x as unknown as string;
console.log(y.toUpperCase()); // Lỗi: `toUpperCase` không tồn tại trên kiểu `number`
```

`TypeScript` vẫn sẽ cố gắng kiểm tra kiểu khi thực hiện việc ghi đè kiểu để ngăn chặn các phép ghi đè không hợp lệ. Ví dụ, đoạn mã sau sẽ gây lỗi kiểu vì `TypeScript` biết rằng việc ghi đè kiểu từ `string` sang `number` không hợp lý nếu không chuyển đổi dữ liệu:

```typescript
let value: string = "123";
let numberValue: number = value as number; // Lỗi kiểu: không thể ghi đè kiểu từ string sang number

// Đúng cách: cần chuyển đổi dữ liệu từ string sang number
let correctNumberValue: number = Number(value); // Chuyển đổi giá trị thành số
```

Phần "Ghi đè kiểu mạnh" (Force Casting) bên dưới sẽ hướng dẫn cách ghi đè kiểu trong trường hợp này.

### Casting with <>

Sử dụng ký tự `<>` hoạt động tương tự như ghi đè kiểu với `as`.

```typescript
let value: unknown = "123";
let numberValue: number = <number>(<unknown>value); // Ghi đè kiểu bằng `<>`

// Đúng cách: cần chuyển đổi dữ liệu từ string sang number
let correctNumberValue: number = Number(value); // Chuyển đổi giá trị thành số
```

- Đúng vậy, cú pháp <type> không hoạt động trong các tệp `TSX` khi làm việc với `React`, vì nó có thể xung đột với cú pháp `JSX`. Trong các tệp `TSX`, bạn nên sử dụng cú pháp `as` để ghi đè kiểu.

### Force casting

Ghi đè kiểu mạnh (Force Casting) là một cách để ghi đè kiểu một biến khi `TypeScript` không cho phép bạn làm điều đó trực tiếp. Đây là một cách để buộc `TypeScript` chấp nhận kiểu của một biến, mặc dù bạn cần phải cẩn thận để đảm bảo rằng kiểu đó là hợp lệ và phù hợp với dữ liệu thực tế.

- Sử dụng `as`

```typescript
let value: unknown = "123";
let numberValue: number = value as number; // Ghi đè kiểu bằng `as`
```

- Sử dụng `<>`

```typescript
let value: unknown = "123";
let numberValue: number = <number>(<unknown>value); // Ghi đè kiểu bằng `<>`
```

- Ví dụ Ghi Đè Kiểu Mạnh

```typescript
let someValue: any = "hello";
let strLength: number = (someValue as string).length; // Ghi đè kiểu để đảm bảo `someValue` là `string`
```

- Ghi đè kiểu không thực sự thay đổi kiểu dữ liệu nội bộ của biến. Nó chỉ là một cách để `TypeScript` chấp nhận kiểu bạn cung cấp. Điều này có thể dẫn đến lỗi nếu kiểu bạn ghi đè không phù hợp với dữ liệu thực tế, vì `TypeScript` không thể kiểm tra các lỗi đó trong thời gian biên dịch. Do đó, hãy sử dụng ghi đè kiểu một cách thận trọng và chỉ khi bạn chắc chắn về kiểu dữ liệu của biến.

## TypeScript Classes

### Members: Types

Các thành viên của `Classes` (bao gồm các `properties` và `methods`) được định kiểu bằng cách sử dụng chú thích kiểu, tương tự như khai báo biến.

```typescript
class Person {
  name: string;
}

const person = new Person();
person.name = "Jane";
```

### Members: Visibility

Các thành viên của `Classes` cũng có thể được gán các bộ điều chỉnh đặc biệt ảnh hưởng đến khả năng truy cập.
Có ba bộ điều chỉnh khả năng truy cập chính trong `TypeScript`:

`public` - (mặc định) cho phép truy cập vào thành viên của `Classes` từ bất kỳ đâu.
`private` - chỉ cho phép truy cập vào thành viên của `Classes` từ bên trong lớp đó.
`protected` - cho phép truy cập vào thành viên của `Classes` từ chính nó và bất kỳ `Classes` nào kế thừa nó, điều này sẽ được đề cập trong phần kế thừa bên dưới.

```typescript
class Person {
  private name: string;

  public constructor(name: string) {
    this.name = name;
  }

  public getName(): string {
    return this.name;
  }
}

const person = new Person("Jane");
console.log(person.getName()); // person.name không thể truy cập từ bên ngoài lớp vì nó được đánh dấu là private
```

Từ khóa `this` trong một lớp thường chỉ đến thể hiện của lớp đó.

### Parameter Properties

`TypeScript` cung cấp một cách tiện lợi để định nghĩa các thành viên của `Classes` trong hàm khởi tạo (constructor) bằng cách thêm bộ điều chỉnh khả năng truy cập vào tham số.

```typescript
class Person {
  // name là biến thành viên private
  public constructor(private name: string) {}

  public getName(): string {
    return this.name;
  }
}

const person = new Person("Jane");
console.log(person.getName()); // "Jane"

class Person {
  constructor(public name: string, private age: number) {}

  public getName(): string {
    return this.name;
  }

  private getAge(): number {
    return this.age;
  }
}

const person = new Person("Jane", 30);
console.log(person.getName()); // "Jane"
// console.log(person.getAge()); // Lỗi: `age` không thể truy cập vì nó được đánh dấu là private
```

### Readonly

Tương tự như mảng, từ khóa `readonly` có thể ngăn chặn các thành viên của `Classes` không bị thay đổi.

```typescript
class Person {
  // name là một thuộc tính readonly
  public readonly name: string;

  public constructor(name: string) {
    this.name = name;
  }

  public getName(): string {
    return this.name;
  }
}

const person = new Person("Jane");
console.log(person.getName()); // "Jane"

// person.name = "John"; // Lỗi: thuộc tính 'name' không thể thay đổi vì nó được đánh dấu là readonly
```

### Inheritance: Implements

Giao diện (interfaces) có thể được sử dụng để định nghĩa kiểu mà một `Classes` phải tuân theo thông qua từ khóa `implements`.

```typescript
class Person {
  interface PersonInterface {
    name: string;
    getName(): string;
 }
}

class Person implements PersonInterface {
  public constructor(public name: string) {}

  public getName(): string {
    return this.name;
  }
}

const person = new Person("Jane");
console.log(person.getName()); // "Jane"
```

Một `Classes` có thể triển khai nhiều giao diện bằng cách liệt kê từng giao diện sau từ khóa `implements`, phân cách nhau bằng dấu phẩy như sau:

```typescript
interface Shape {
  getArea(): number;
}

interface Colored {
  color: string;
}

class Rectangle implements Shape, Colored {
  public constructor(
    public width: number,
    public height: number,
    public color: string
  ) {}

  public getArea(): number {
    return this.width * this.height;
  }
}

const rectangle = new Rectangle(5, 10, "red");
console.log(rectangle.getArea()); // 50
console.log(rectangle.color); // "red"
```

### Inheritance: Extends

Các `Classes` có thể kế thừa lẫn nhau thông qua từ khóa `extends`. Một `Classes` chỉ có thể kế thừa từ một `Classes` khác.

```typescript
class Animal {
  public constructor(public name: string) {}

  public speak(): void {
    console.log(`${this.name} makes a noise.`);
  }
}

class Dog extends Animal {
  public bark(): void {
    console.log(`${this.name} barks.`);
  }
}

const dog = new Dog("Rex");
dog.speak(); // "Rex makes a noise."
dog.bark(); // "Rex barks."
```

### Override

Trong `TypeScript`, bạn có thể ghi đè (`override`) phương thức của `Classes` cha trong `Classes` con bằng cách sử dụng từ khóa `override`. Điều này cho phép `Classes` con cung cấp một cài đặt mới cho phương thức đã được định nghĩa trong `Classes` cha.

```typescript
class Animal {
  public constructor(public name: string) {}

  public speak(): void {
    console.log(`${this.name} makes a noise.`);
  }
}

class Dog extends Animal {
  // Ghi đè phương thức speak từ lớp Animal
  public override speak(): void {
    console.log(`${this.name} barks.`);
  }
}

const dog = new Dog("Rex");
dog.speak(); // "Rex barks."
```

Theo mặc định, từ khóa `override` là tùy chọn khi ghi đè một phương thức và chỉ giúp ngăn ngừa việc ghi đè nhầm một phương thức không tồn tại. Để bắt buộc sử dụng từ khóa `override` khi ghi đè, bạn có thể sử dụng thiết lập `noImplicitOverride` trong cấu hình `TypeScript`.

```typescript
{
  "compilerOptions": {
    "noImplicitOverride": true
  }
}
```

### Abstract Classes

Các `Classes` có thể được viết theo cách cho phép chúng được sử dụng làm `Classes` cơ sở cho các `Classes` khác mà không cần phải triển khai tất cả các thành viên. Điều này được thực hiện bằng cách sử dụng từ khóa `abstract`. Các thành viên chưa được triển khai cũng sử dụng từ khóa `abstract`.

- Sai cách.

```typescript
abstract class Animal {
  constructor(public name: string) {}

  // Phương thức trừu tượng, lớp kế thừa phải triển khai phương thức này
  public abstract speak(): void;

  // Phương thức cụ thể có thể được sử dụng hoặc ghi đè trong lớp kế thừa
  public sleep(): void {
    console.log(`${this.name} is sleeping.`);
  }
}

class Dog extends Animal {
  // Phương thức abstract phải được triển khai trong lớp kế thừa
  public override speak(): void {
    console.log(`${this.name} barks.`);
  }
}

const dog = new Dog("Rex");
dog.speak(); // "Rex barks."
dog.sleep(); // "Rex is sleeping."
```

Các `Classes` trừu tượng (`abstract classes`) không thể được khởi tạo trực tiếp, vì chúng không triển khai đầy đủ tất cả các thành viên của mình.

- Đúng cách

```typescript
class Dog extends Animal {
  public override speak(): void {
    console.log(`${this.name} barks.`);
  }
}

const dog = new Dog("Rex"); // Đúng cách, lớp Dog đã triển khai tất cả các phương thức trừu tượng
dog.speak(); // "Rex barks."
dog.sleep(); // "Rex is sleeping."
```

## TypeScript Basic Generics

`Generics` cho phép tạo ra biến kiểu (type variables) có thể được sử dụng để tạo các lớp (classes), hàm (functions) và các kiểu `alias` mà không cần phải định nghĩa rõ ràng các kiểu mà chúng sử dụng.

`Generics` giúp việc viết mã tái sử dụng trở nên dễ dàng hơn.

### Functions

`Generics` với các hàm (functions) giúp tạo ra các phương thức tổng quát hơn, đại diện chính xác hơn cho các kiểu dữ liệu được sử dụng và trả về.

```typescript
function createPair<S, T>(v1: S, v2: T): [S, T] {
  return [v1, v2];
}
console.log(createPair<string, number>("hello", 42)); // ['hello', 42]
```

`TypeScript` cũng có thể suy luận kiểu của tham số `generic` từ các tham số của hàm.

### Classes

`Generics` có thể được sử dụng để tạo ra các lớp tổng quát, như `Map`.

```typescript
class NamedValue<T> {
  private _value: T | undefined;

  constructor(private name: string) {}

  public setValue(value: T) {
    this._value = value;
  }

  public getValue(): T | undefined {
    return this._value;
  }

  public toString(): string {
    return `${this.name}: ${this._value}`;
  }
}

let value = new NamedValue<number>("myNumber");
value.setValue(10);
console.log(value.toString()); // myNumber: 10
```

### Type Aliases

`Generics` trong các kiểu `alias` cho phép tạo ra các kiểu dữ liệu có tính tái sử dụng cao hơn.

```typescript
type Wrapped<T> = { value: T };

const wrappedValue: Wrapped<number> = { value: 10 };
```

### Default Value

`Generics` có thể được gán các giá trị mặc định, giá trị này sẽ được áp dụng nếu không có giá trị nào khác được chỉ định hoặc suy luận.

```typescript
class NamedValue<T = string> {
  private _value: T | undefined;

  constructor(private name: string) {}

  public setValue(value: T) {
    this._value = value;
  }

  public getValue(): T | undefined {
    return this._value;
  }

  public toString(): string {
    return `${this.name}: ${this._value}`;
  }
}

let value = new NamedValue("myNumber");
value.setValue("myValue");
console.log(value.toString()); // myNumber: myValue
```

### Extends

Có thể thêm ràng buộc vào `generics` để giới hạn những gì được phép. Các ràng buộc này giúp có thể dựa vào một kiểu cụ thể hơn khi sử dụng kiểu `generic`.

```typescript
function createLoggedPair<S extends string | number, T extends string | number>(
  v1: S,
  v2: T
): [S, T] {
  console.log(`creating pair: v1='${v1}', v2='${v2}'`);
  return [v1, v2];
}
```

## TypeScript Utility Types

`TypeScript` đi kèm với một số lượng lớn các kiểu dữ liệu có thể hỗ trợ trong việc thao tác kiểu dữ liệu thông thường, thường được gọi là các kiểu dữ liệu tiện ích (utility types).

Chương này sẽ đề cập đến những kiểu dữ liệu tiện ích phổ biến nhất.

### Partial

`Partial` thay đổi tất cả các thuộc tính trong một đối tượng thành tùy chọn.

```typescript
interface Point {
  x: number;
  y: number;
}

let pointPart: Partial<Point> = {}; // `Partial` cho phép x và y là tùy chọn
pointPart.x = 10;
```

### Required

`Required` thay đổi tất cả các thuộc tính trong một đối tượng thành bắt buộc.

```typescript
interface Car {
  make: string;
  model: string;
  mileage?: number;
}

let myCar: Required<Car> = {
  make: "Ford",
  model: "Focus",
  mileage: 12000, // `Required` yêu cầu mileage phải được định nghĩa
};
```

### Record

`Record` là một cú pháp tắt để định nghĩa một kiểu đối tượng với một kiểu khóa cụ thể và kiểu giá trị cụ thể.

```typescript
const nameAgeMap: Record<string, number> = {
  Alice: 21,
  Bob: 25,
};

Record<string, number> tương đương với { [key: string]: number }

```

### Omit

`Omit` loại bỏ các khóa khỏi một kiểu đối tượng.

```typescript
interface Person {
  name: string;
  age: number;
  location?: string;
}

const bob: Omit<Person, "age" | "location"> = {
  name: "Bob",
  // `Omit` đã loại bỏ age và location khỏi kiểu và chúng không thể được định nghĩa ở đây
};
```

### Pick

`Pick` loại bỏ tất cả các khóa ngoại trừ các khóa được chỉ định từ một kiểu đối tượng.

```typescript
interface Person {
  name: string;
  age: number;
  location?: string;
}

const bob: Pick<Person, "name"> = {
  name: "Bob",
  // `Pick` chỉ giữ lại name, vì vậy age và location đã bị loại bỏ khỏi kiểu và không thể được định nghĩa ở đây
};
```

### Exclude

`Exclude` loại bỏ các kiểu dữ liệu khỏi một kiểu hợp nhất (union).

```typescript
type Primitive = string | number | boolean;
const value: Exclude<Primitive, string> = true; // một chuỗi không thể được sử dụng ở đây vì `Exclude` đã loại bỏ nó khỏi kiểu
```

### ReturnType

`ReturnType` trích xuất kiểu trả về của một kiểu hàm.

```typescript
type PointGenerator = () => { x: number; y: number };
const point: ReturnType<PointGenerator> = {
  x: 10,
  y: 20,
};
```

### Parameters

`Parameters` trích xuất các kiểu tham số của một kiểu hàm dưới dạng một mảng.

```typescript
type PointPrinter = (p: { x: number; y: number }) => void;
const point: Parameters<PointPrinter>[0] = {
  x: 10,
  y: 20,
};
```

### Readonly

`Readonly` được sử dụng để tạo ra một kiểu mới trong đó tất cả các thuộc tính là chỉ đọc (readonly), nghĩa là chúng không thể được thay đổi sau khi đã gán giá trị.
Hãy nhớ rằng `TypeScript` sẽ ngăn cản điều này ở thời điểm biên dịch, nhưng về lý thuyết, vì nó được biên dịch xuống `JavaScript`, bạn vẫn có thể ghi đè lên thuộc tính `readonly`.

```typescript
interface Person {
  name: string;
  age: number;
}

const person: Readonly<Person> = {
  name: "Dylan",
  age: 35,
};

person.name = "Israel"; // prog.ts(11,8): lỗi TS2540: Không thể gán giá trị cho 'name' vì nó là thuộc tính chỉ đọc.
```

## TypeScript Keyof

`keyof` là một từ khóa trong `TypeScript` được sử dụng để trích xuất kiểu khóa từ một kiểu đối tượng.

### keyof with explicit keys

Khi được sử dụng trên một kiểu đối tượng với các khóa rõ ràng, `keyof` tạo ra một kiểu hợp nhất (union type) với các khóa đó.

```typescript
interface Person {
  name: string;
  age: number;
}

// `keyof Person` ở đây tạo ra một kiểu hợp nhất của "name" và "age", các chuỗi khác sẽ không được phép
function printPersonProperty(person: Person, property: keyof Person) {
  console.log(`In ấn thuộc tính của người ${property}: "${person[property]}"`);
}

let person = {
  name: "Max",
  age: 27,
};

printPersonProperty(person, "name"); // In ấn thuộc tính của người name: "Max"
```

### keyof with index signatures

`keyof` cũng có thể được sử dụng với các chữ ký chỉ mục (index signatures) để trích xuất kiểu chỉ mục.

```typescript
type StringMap = { [key: string]: unknown };

// `keyof StringMap` ở đây được giải quyết thành `string`
function createStringPair(property: keyof StringMap, value: string): StringMap {
  return { [property]: value };
}
```

## TypeScript Null & Undefined

`TypeScript` có một hệ thống mạnh mẽ để xử lý các giá trị `null` hoặc `undefined`.

Theo mặc định, việc xử lý `null` và `undefined` bị tắt, và có thể được bật bằng cách đặt `strictNullChecks` thành `true`.

Các phần còn lại của trang này áp dụng khi `strictNullChecks` được bật.

### Types

`null` và `undefined` là các kiểu nguyên thủy và có thể được sử dụng giống như các kiểu khác, chẳng hạn như `string`.

```typescript
let value: string | undefined | null = null;
value = "hello";
value = undefined;
```

Khi `strictNullChecks` được bật, `TypeScript` yêu cầu các giá trị phải được thiết lập trừ khi `undefined` được thêm rõ ràng vào kiểu.

### Optional Chaining

`Optional Chaining` là một tính năng của `JavaScript` hoạt động tốt với việc xử lý `null` của `TypeScript`. Nó cho phép truy cập các thuộc tính trên một đối tượng, có thể tồn tại hoặc không, bằng một cú pháp gọn gàng. Nó có thể được sử dụng với toán tử ?. khi truy cập các thuộc tính.

```typescript
interface House {
  sqft: number;
  yard?: {
    sqft: number;
  };
}

function printYardSize(house: House) {
  const yardSize = house.yard?.sqft;
  if (yardSize === undefined) {
    console.log("Không có sân");
  } else {
    console.log(`Sân có diện tích ${yardSize} sqft`);
  }
}

let home: House = {
  sqft: 500,
};

printYardSize(home); // In ra 'Không có sân'
```

### Nullish Coalescence

`Nullish Coalescence` là một tính năng khác của `JavaScript` cũng hoạt động tốt với việc xử lý null của `TypeScript`. Nó cho phép viết các biểu thức có giá trị thay thế đặc biệt khi xử lý `null` hoặc `undefined`. Điều này hữu ích khi các giá trị `falsy` khác có thể xuất hiện trong biểu thức nhưng vẫn hợp lệ. Nó có thể được sử dụng với toán tử `??` trong một biểu thức, tương tự như việc sử dụng toán tử `&&`.

```typescript
function printMileage(mileage: number | null | undefined) {
  console.log(`Kilometra: ${mileage ?? "Không có sẵn"}`);
}

printMileage(null); // In ra 'Kilometra: Không có sẵn'
printMileage(0); // In ra 'Kilometra: 0'
```

### Null Assertion

Hệ thống suy luận của `TypeScript` không phải lúc nào cũng hoàn hảo, có những lúc việc bỏ qua khả năng giá trị là `null` hoặc `undefined` là hợp lý. Một cách đơn giản để làm điều này là sử dụng `casting`, nhưng `TypeScript` cũng cung cấp toán tử `!` như một cú pháp tắt tiện lợi.

```typescript
function getValue(): string | undefined {
  return "hello";
}
let value = getValue();
console.log("value length: " + value!.length);
```

Giống như `casting`, việc sử dụng toán tử `!` cũng có thể không an toàn và nên được sử dụng cẩn thận.

### Array bounds handling

Ngay cả khi `strictNullChecks` được bật, theo mặc định `TypeScript` sẽ giả định rằng việc truy cập vào mảng sẽ không bao giờ trả về `undefined` (trừ khi `undefined` là một phần của kiểu mảng).

Cấu hình `noUncheckedIndexedAccess` có thể được sử dụng để thay đổi hành vi này.

```typescript
let array: number[] = [1, 2, 3];
let value = array[0]; // với `noUncheckedIndexedAccess`, kiểu của `value` sẽ là `number | undefined`
```

## TypeScript Definitely Typed

Các gói `NPM` trong hệ sinh thái `JavaScript` rộng lớn không phải lúc nào cũng có sẵn các kiểu dữ liệu.

Đôi khi, các dự án không còn được duy trì, và đôi khi các dự án không quan tâm, không đồng ý với, hoặc không có thời gian để sử dụng `TypeScript`.

### Using non-typed NPM packages in TypeScript

Việc sử dụng các gói `NPM` không có kiểu với `TypeScript` sẽ không an toàn về kiểu do thiếu kiểu dữ liệu.

Để giúp các nhà phát triển `TypeScript` sử dụng các gói như vậy, có một dự án cộng đồng được duy trì gọi là `Definitely Typed`.

`Definitely Typed` là một dự án cung cấp một kho lưu trữ trung tâm các định nghĩa `TypeScript` cho các gói NPM không có kiểu.

```typescript
npm install --save-dev @types/jquery
```

Thông thường, không cần thêm bước nào khác để sử dụng các kiểu dữ liệu sau khi cài đặt gói khai báo, `TypeScript` sẽ tự động nhận diện các kiểu dữ liệu khi sử dụng chính gói đó.

## TypeScript 5.x Updates

`TypeScript` được `Microsoft` duy trì và cập nhật tích cực. Trong phiên bản 5.x, đã có nhiều cập nhật tiện ích và cải thiện chất lượng cuộc sống.

### Template Literal Types

Các kiểu `Literal Template` giờ đây cho phép chúng ta tạo ra các kiểu chính xác hơn bằng cách sử dụng các `literal template`. Chúng ta có thể định nghĩa các kiểu tùy chỉnh phụ thuộc vào các giá trị thực tế của các chuỗi tại thời điểm biên dịch.

```typescript
type Color = "red" | "green" | "blue";
type HexColor<T extends Color> = `#${string}`;

// Usage:
let myColor: HexColor<"blue"> = "#0000FF";
```

### Index Signature Labels

Những nhãn chữ ký chỉ mục (Index Signature Labels) cho phép chúng ta gán nhãn cho các chữ ký chỉ mục bằng cách sử dụng tên thuộc tính tính toán. Điều này giúp cung cấp thông tin kiểu dữ liệu mô tả hơn khi làm việc với các đối tượng động.

```typescript
type DynamicObject = { [key: string as `dynamic_${string}`]: string };

// Usage:
let obj: DynamicObject = { dynamic_key: "value" };
```
