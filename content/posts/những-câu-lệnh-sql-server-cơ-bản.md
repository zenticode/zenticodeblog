---
title: Những câu lệnh SQL Server cơ bản
date: 2023-03-08 21:23
description: SQL Server là một trong những hệ quản trị cơ sở dữ liệu phổ biến
  nhất trên thế giới. Với sự phát triển của công nghệ, việc sử dụng SQL Server
  trở nên ngày càng đơn giản và tiện lợi. Những câu lệnh SQL Server cơ bản được
  giới thiệu trong bài viết này sẽ giúp bạn hiểu rõ hơn về cách sử dụng SQL
  Server để truy xuất và quản lý dữ liệu.
---
<!--StartFragment-->

1. SELECT: Câu lệnh SELECT được sử dụng để truy xuất dữ liệu từ một hoặc nhiều bảng. Ví dụ: SELECT * FROM employees;
2. WHERE: Câu lệnh WHERE được sử dụng để lọc dữ liệu dựa trên một hoặc nhiều điều kiện. Ví dụ: SELECT * FROM employees WHERE salary > 50000;
3. ORDER BY: Câu lệnh ORDER BY được sử dụng để sắp xếp kết quả truy vấn theo thứ tự tăng dần hoặc giảm dần. Ví dụ: SELECT * FROM employees ORDER BY salary DESC;
4. GROUP BY: Câu lệnh GROUP BY được sử dụng để nhóm dữ liệu theo các trường được chỉ định và tính toán các hàm số trên nhóm đó. Ví dụ: SELECT department, AVG(salary) FROM employees GROUP BY department;
5. JOIN: Câu lệnh JOIN được sử dụng để kết hợp các bảng dữ liệu với nhau dựa trên một hoặc nhiều trường. Ví dụ: SELECT employees.name, departments.department_name FROM employees JOIN departments ON employees.department_id = departments.id;
6. INSERT INTO: Câu lệnh INSERT INTO được sử dụng để chèn dữ liệu mới vào bảng. Ví dụ: INSERT INTO employees(name, age, salary) VALUES('John', 30, 60000);
7. UPDATE: Câu lệnh UPDATE được sử dụng để cập nhật dữ liệu trong bảng. Ví dụ: UPDATE employees SET salary = 65000 WHERE name = 'John';
8. DELETE: Câu lệnh DELETE được sử dụng để xóa dữ liệu từ bảng. Ví dụ: DELETE FROM employees WHERE name = 'John';

<!--StartFragment-->

Những câu lệnh SQL Server cơ bản trên đây là những công cụ giúp bạn truy xuất, quản lý và thao tác với dữ liệu trong SQL Server. Việc hiểu và sử dụng thành thạo những câu lệnh này sẽ giúp bạn làm việc hiệu quả với cơ sở dữ liệu của mình và đảm bảo tính toàn vẹn của dữ liệu.

<!--EndFragment-->

<!--EndFragment-->