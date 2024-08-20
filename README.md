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
