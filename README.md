# learn-typescript

Tôi sử dụng repo này để theo dõi tất cả các bài học tôi đã học về typescript

## Tài liệu tham khảo

- https://www.typescriptlang.org/docs

- https://www.w3schools.com/typescript/index.php

## Công cụ playground trực tuyến

- https://www.typescriptlang.org/play/

## TypeScript là gì?

TypeScript là một "Syntactic Superset" có nghĩa là nó chia sẻ cùng cú pháp cơ bản với JavaScript, nhưng bổ sung thêm một số tính năng.

## Tại sao nên sử dụng TypeScript?

JavaScript là một ngôn ngữ có kiểu dữ liệu lỏng lẻo. Điều này có thể khiến việc hiểu rõ các loại dữ liệu đang được truyền trong JavaScript trở nên khó khăn.

Trong JavaScript, các tham số của hàm và biến không có bất kỳ thông tin nào về kiểu dữ liệu! Vì vậy, các nhà phát triển cần xem tài liệu hoặc đoán dựa trên cách triển khai.

TypeScript cho phép chỉ định các kiểu dữ liệu đang được truyền trong mã và có khả năng báo lỗi khi các kiểu dữ liệu không khớp.
Ví dụ, TypeScript sẽ báo lỗi khi truyền một chuỗi vào một hàm mong đợi một số. JavaScript thì không.

TypeScript sử dụng kiểm tra kiểu tại thời điểm biên dịch, nghĩa là nó kiểm tra xem các kiểu đã chỉ định có khớp hay không trước khi chạy mã, chứ không phải trong khi chạy mã.

## Làm cách nào để sử dụng TypeScript?

Một cách thông dụng để sử dụng TypeScript là dùng trình biên dịch chính thức của TypeScript, trình biên dịch này chuyển đổi mã TypeScript thành JavaScript.

Một số trình chỉnh sửa mã phổ biến, chẳng hạn như Visual Studio Code, có tích hợp sẵn hỗ trợ TypeScript và có thể hiển thị lỗi khi bạn viết mã!

## Trình biên dịch TypeScript

TypeScript được chuyển đổi thành JavaScript có nghĩa là nó có thể chạy ở bất kỳ đâu mà JavaScript chạy!

### Cài đặt trình biên dịch

TypeScript có một trình biên dịch chính thức có thể được cài đặt thông qua npm.

```typescript
    npm install typescript --save-dev
```

Trình biên dịch được cài đặt trong thư mục node_modules và có thể chạy bằng lệnh: npx tsc.

```typescript
    npx tsc
```

### Cấu hình trình biên dịch

Theo mặc định, trình biên dịch TypeScript sẽ hiển thị thông báo trợ giúp khi chạy trong một dự án trống.

Trình biên dịch có thể được cấu hình bằng cách sử dụng tệp tsconfig.json.

Có thể để TypeScript tạo tệp tsconfig.json với các cài đặt được khuyến nghị bằng lệnh sau:

```typescript
    npx tsc --init
```

## TypeScript các Types đơn giản

### TypeScript hỗ trợ một số kiểu dữ liệu đơn giản (primitive) mà bạn có thể đã biết:

Có ba kiểu dữ liệu nguyên thủy chính trong JavaScript và TypeScript:

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

Ngoài ra, còn có hai kiểu dữ liệu nguyên thủy ít phổ biến hơn được sử dụng trong các phiên bản JavaScript và TypeScript sau:

- bigint: Các số nguyên lớn hơn, cho phép các giá trị lớn hơn nhiều so với kiểu number.

```typescript
let largeNumber: bigint = 1234567890123456789012345678901234567890n;
```

\*symbol: Được sử dụng để tạo một định danh toàn cầu duy nhất.

```typescript
let uniqueId: symbol = Symbol("description");
```

## Cách triển khai biến.

Khi tạo một biến trong TypeScript, có hai cách chính để gán kiểu dữ liệu:

- Explicit

```typescript
let firstName: string = "Dylan";
```

- Implicit

```typescript
let firstName = "Dylan";
```

Lưu ý: Việc để TypeScript "đoán" kiểu dữ liệu của một giá trị được gọi là suy diễn kiểu (infer).

## Lỗi khi gán type cho biến.

### TypeScript sẽ báo lỗi nếu các kiểu dữ liệu không khớp.

```typescript
let firstName: string = "Dylan"; // type string
firstName = 33; // attempts to re-assign the value to a different type
```

Gán kiểu dữ liệu ngầm định có thể khiến firstName ít nổi bật hơn như một chuỗi, nhưng cả hai cách đều sẽ báo lỗi nếu kiểu dữ liệu không khớp:

```typescript
let firstName: string = "Alice"; // Gán kiểu rõ ràng
let firstName = "Alice"; // Gán kiểu ngầm định (suy diễn)

firstName = 123; // Lỗi: Không thể gán kiểu number cho kiểu string

firstName;
```

Trong cả hai trường hợp, TypeScript sẽ báo lỗi nếu bạn cố gắng gán một giá trị không khớp với kiểu dữ liệu đã chỉ định hoặc suy diễn.

## Không thể suy luận

Lưu ý: Bạn có thể thấy các kiểu dữ liệu nguyên thủy được viết hoa như Boolean.

boolean !== Boolean

Đối với hướng dẫn này, hãy chỉ sử dụng các kiểu dữ liệu viết thường (boolean, number, string, v.v.). Các kiểu viết hoa (Boolean, Number, String) thường được sử dụng trong các hoàn cảnh rất cụ thể và không phải là kiểu dữ liệu chính để khai báo biến trong TypeScript.
