---
title: Tìm hiểu về mảng trong Javascript
date: 2023-03-15 10:15
tags:
  - Javascript
description: Mảng trong JavaScript là một loại đối tượng toàn cục được sử dụng
  để lưu trữ dữ liệu. Mảng bao gồm một tập hợp hoặc danh sách có thứ tự chứa
  không hoặc nhiều kiểu dữ liệu và sử dụng các chỉ mục được đánh số bắt đầu từ 0
  để truy cập các mục cụ thể.
---
Mảng trong JavaScript là một loại đối tượng toàn cục được sử dụng để lưu trữ dữ liệu. Mảng bao gồm một tập hợp hoặc danh sách có thứ tự chứa không hoặc nhiều kiểu dữ liệu và sử dụng các chỉ mục được đánh số bắt đầu từ 0 để truy cập các mục cụ thể. Mảng rất hữu ích vì chúng lưu trữ nhiều giá trị trong một biến duy nhất, có thể cô đọng và tổ chức mã của chúng ta, làm cho nó dễ đọc và dễ bảo trì hơn. Mảng có thể chứa bất kỳ kiểu dữ liệu nào, bao gồm **number**, **string** và **object**.

# Tạo một mảng

Có hai cách để tạo một mảng trong JavaScript:

1. Mảng ký tự, sử dụng dấu ngoặc vuông **\[]** Ví dụ :

```none
const students = [
    "John",
    "Peter",
];
console.log(students)  // ["John","Peter"]

```

2. Phương thức tạo mảng, sử dụng từ khóa **new** Ví dụ :

```none
const students = new Array(
    "John",
    "Peter",
);
console.log(students)  // ["John","Peter"]

```

# Truy cập các phần từ trong mảng

Một phần tử trong một mảng JavaScript được truy cập bằng cách tham chiếu đến vị trí index của phần tử đó trong **\[]**. Ví dụ :

```none
const students = [
    "John",
    "Peter",
];
console.log(students[0])  // John

```

Nếu truy cập vào một phần tử không tồn tại sẽ trả về **undefined**. Ví dụ :

```none
const students = [
    "John",
    "Peter",
];
console.log(students[2])  // undefined

```

# Thêm phần tử vào mảng

Chúng ta sẽ dùng phươc thức **push()**, phương thức này sẽ thêm một phần tử vào cuối một mảng. Ví dụ :

```none
const students = [
    "John",
    "Peter",
];
students.push('Coca');
console.log(students)  // ["John","Peter", "Coca"]

```

Hoặc có thể dùng phương thức **unshift()**, phương thức này sẽ thêm một phần tử vào đầu mảng. Ví dụ:

```none
const students = [
    "John",
    "Peter",
];
students.unshift('Coca');
console.log(students)  // ["Coca","John","Peter"]

```

# Xóa phần tử ra khỏi mảng

Khi chúng ta muốn xóa một phần tử cụ thể khỏi một mảng, chúng ta sử dụng phương thức **splice()**. Ví dụ :

```none
const students = [
    "John",
    "Peter",
    "Naul",
    "Levi"
];
students.splice(0,2);
console.log(students); // ["Naul","Levi"]

```

Trong phương thức **splice ()**, tham số đầu tiên là vị trí index phần tử cần loại bỏ (trong trường hợp này là 0) và tham số thứ hai là số lượng phần tử bạn muốn xóa.

Để xóa phần tử cuối cùng trong mảng, ta sử dụng phương thức **pop()** Ví dụ :

```none
const students = [
    "John",
    "Peter",
    "Naul",
    "Levi"
];
students.pop();
console.log(students); // ["John","Peter","Naul"]

```

Để xóa phần tử đầu tiên trong mảng, ta sử dụng phương thức **shift()**

```none
const students = [
    "John",
    "Peter",
    "Naul",
    "Levi"
];
students.pop();
console.log(students); // ["Peter","Naul","Levi"]

```

# Vòng lặp trong mảng

Chúng ta có thể lặp lại toàn bộ mảng với từ khóa **for**, tận dụng thuộc tính **length**. Ví dụ :

```none
const students = [
    "John",
    "Peter",
    "Naul",
    "Levi"
];
for(let i = 0; i< students.length; i++) {
  console.log(i, students[i]); // 0 John 1 Peter 2 Naul 3 Levi
}

```

Chúng ta cũng có thể sử dụng vòng lặp\*\* for ... of\*\*, một tính năng mới hơn của JavaScript. Ví dụ :

```none
const students = [
    "John",
    "Peter",
    "Naul",
    "Levi"
];
for(let student of students) {
  console.log(student); // John Peter Naul Levi
}

```

Vòng lặp **for ... of** không truy xuất đến vị trí index của các phần tử trong mảng, nhưng nó là một cách đơn giản hơn, ngắn gọn hơn để lặp qua một mảng.

# Conclusion

Mảng là một phần cực kỳ linh hoạt và cơ bản của lập trình trong JavaScript. Trong hướng dẫn này, chúng ta đã học cách tạo mảng và một số tác vụ phổ biến nhất khi làm việc trong mảng, chẳng hạn như tạo, xóa và vòng lặp trong mảng. Hy vọng bài viết này sẽ giúp các bạn hiểu được cách làm việc với mảng. Cảm ơn các bạn đã đọc và mong rằng nó sẽ hữu ích với bạn

Link tham khảo : <https://www.digitalocean.com/community/tutorials/understanding-arrays-in-javascript>