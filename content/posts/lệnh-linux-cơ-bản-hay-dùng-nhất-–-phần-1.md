---
title: "# Lệnh linux cơ bản hay dùng nhất – Phần 1"
date: 2023-03-16 10:47
tags:
  - Linux
  - Beginner
description: Linux là một trong các hệ điều hành phổ biến nhất với dân lập trình
  chúng ta. Nhưng để hiểu và quen với nó thì không phải ai cũng có thể làm được,
  đặc biệt là với những người mới bắt đầu. Bài viết này chúng ta sẽ tìm hiểu các
  lệnh cơ bản về Linux nha.
---
# Lệnh linux cơ bản hay dùng nhất – Phần 1

## 1. ls

Hiển thị danh sách các tập tin và thư mục trong thư mục hiện tại. Ví dụ: ls – hiển thị danh sách các tập tin và thư mục trong thư mục hiện tại

Khi bạn muốn hiển thị ngày giờ (2) cùng với đó là quyền sở hữu của user (3), các quyền mà user có thể làm (đọc, chỉnh sửa, xóa) (4) ta có thể dùng:

```none

ls -l

```

![](https://images.viblo.asia/00deea04-e8b0-48cf-a727-d9346d47af75.png)

```none

ls -lh 

```

Nhìn rõ dung lượng của file ( dùng cho thư mục có thể bị sai )

## 2. cd

Chuyển đến các thư mục theo ý muốn. (dùng khá nhiều để di chuyển)

Trước khi sử dụng cần nên học cách phân biệt các thư mục đặc trưng.

cd ~ là ở đâu ? cd / là ở đâu ? (nếu còn bối rối có thể xem qua video youtube để hiểu rõ hơn)

~: là thư mục của user mà ta đang đăng nhập

/: là thư mục gốc của server

vd:

```none
cd /home/user/Documents

```

## 3. mkdir

Tạo thư mục

Vd:

```none
cd /

mkdir home

```

Nếu bạn muốn tạo một đường dẫn dài hơn có them option -p vào

Vd

`mkdir -p /home/download/picture`

## 4. Touch

Tạo file mới . Đến giờ vẫn chưa hiểu sao gọi là touch :v, chắc là muốn chạm là phải tạo. Mình nghĩ vậy

Vd

```none

cd /home

```

```none

touch test.txt

```

## 5. cp

Nhân bản (copy) một thư mục hoặc một file nào đó

```none

`cp test.txt test1.txt`

```

Nếu muốn copy một thư mục thì bạn them option -r nhé

```none
cp -r home home_bk`

```

## 6. mv

Đem tệp hoặc thư mục đặt ở chỗ khác. Đặc biệt nó cũng có thể dung để đổi tên 1 tệp hoặc 1 thư mục

Vd:

```none
mv file.txt /home/user`

```

Vd:

```none

`mv file.txt file1.txt`

```

## 7. rm

Lệnh này khá nguy hiểm, biết tại sao nguy hiểm thì bạn cũng có thể mờ mờ đoán ra Tiếng Anh của nó rồi phải không ? Là remove đấy 😊. Khi xài lệnh này nhớ đừng có uống bia rượu gì nha. Có khi một dự án bay mất chỉ vì lệnh này đấy !!!

Cú pháp của nó là

rm

Khi nhấn nó sẽ hỏi lại bạn là có muốn xóa hay không.

Nếu thấy phiền quá thì bạn them option sau

```none
rm -f  file

```

Xóa khỏi cần hỏi luôn.

Còn nếu muốn xóa thư mục thì thêm option -r

```none

rm -r thư mục

```

hay

```none

rm -rf  thư mục

```

## 8. cat

Hiển thị nội dung của tập tin trên terminal luôn.

vd:

```none

`cat file1.txt``

```

## 9. grep

Lệnh này rất thần thánh nếu bạn biết dùng nó kết hợp với các lệnh khác. Hãy tìm hiểu nó vì mình nghĩ sẽ dùng cũng khá là nhiều đấy.

Nó dùng để tìm các từ khóa liên quan nếu bạn kết hợp với :

```none

`ls -l | grep ‘từ khóa ’`

```

Liệt kê ra các file có từ khóa trong grep.

Dùng với lệnh

```none

`history | grep <từ khóa>`

```

Liệt kê các lệnh đã sử dụng có từ khóa trong grep

## 10. chmod

Khi làm DBA hay Devops liên quan đến hệ điều hành có thể bạn sẽ được hay nhờ phân quyền file này, phân quyền thư mục nọ thì đây sẽ là lệnh giúp bạn.

Thông thường mình xài lệnh

```none

`chmod 777 file`

```

(Phân quyền full, ai dô làm gì làm, nhưng mà chỉ xài khi hiểu rằng chắc chắn không ai sẽ phá hư file đó)

Nếu muốn phân quyền như vậy với thư mục và các file con trong thư mục đó bạn thêm option -R

```none

chmod -R 777 thư mục

```

## Kết.

Chúc các bạn làm quen với các lệnh cơ bản này nhé, thuần thục thì sau này công việc sẽ rất dễ dàng đấy. Đón xem thêm phần 2 nếu muốn biết thêm nha.

Xem thêm tại: <https://beatcomputer.com/>

N﻿guồn: [Viblo](https://viblo.asia/p/lenh-linux-co-ban-hay-dung-nhat-phan-1-r1QLxQjdVAw)