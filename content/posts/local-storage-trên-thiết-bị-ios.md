---
title: Local Storage trên thiết bị iOS
date: 2023-05-17 09:57
tags:
  - IOS
description: Local storage (lưu trữ cục bộ) là một trong những phần cần kiểm tra
  khi thực hiện kiểm thử an toàn cho các ứng dụng iOS. Tại đây sẽ lưu trữ các
  tệp tin cấu hình của ứng dụng, cache, dữ liệu sinh ra trong quá trình sử dụng
---
![](<>)

Local storage (lưu trữ cục bộ) là một trong những phần cần kiểm tra khi thực hiện kiểm thử an toàn cho các ứng dụng iOS. Tại đây sẽ lưu trữ các tệp tin cấu hình của ứng dụng, cache, dữ liệu sinh ra trong quá trình sử dụng,... Đôi khi lập trình viên sẽ lưu một số thông tin quan trọng, thông tin nhạy cảm trên thiết bị. Việc này thực ra không có vấn đề gì... cho đến khi bị hack. Vì vậy khi thực hiện kiểm thử an toàn chúng ta cần kiểm tra khu vực lưu trữ cục bộ, và đánh giá cho khách hàng xem việc lưu trữ thông tin nào có thể ảnh hưởng xấu đến người dùng nếu hacker can thiệp được vào thiết bị.

# 1. Cấu trúc thư mục lưu trữ

Cả Android và iOS đều chạy ứng dụng trong các sandbox, mỗi ứng dụng tương ứng với một sandbox riêng biệt. Việc này có 3 lợi ích:

* Đảm bảo tính bí mật của dữ liệu: các ứng dụng sẽ không thể truy cập vào dữ liệu nằm trong sandbox của ứng dụng khác.
* Đễ quản lý: hệ điều hành có thể quản lý dữ liệu của từng ứng dụng bằng cách truy cập sandbox tương ứng với ứng dụng đó.
* Bảo vệ hệ thống: trong trường hợp ứng dụng chứa mã độc, hành vi của mã độc sẽ bị hạn chế trong sandbox và khó lây lan ra ngoài sandbox được.

![](<>)

Mỗi sandbox của ứng dụng trên thiết bị iOS được chia thành 3 khối:

* Bundle container.
* Data container.
* iCloud container.

![](<>)

**Bundle container** là một thư mục có tên dạng ***appname.app*** chứa các dữ liệu được đóng gói trong tệp tin cài đặt (gồm ứng dụng và các tài nguyên). Người dùng không được cấp quyền ghi vào thư mục này. Thư mục appname.app sẽ được **ký tại thời điểm cài đặt** ứng dụng. Nếu hệ điều hành kiểm tra thấy chữ ký bị thay đổi (tức dữ liệu trong Bundle đã bị thay đổi) thì sẽ ngăn chặn việc chạy ứng dụng.

![](<>)

**Data container** chứa các dữ liệu của ứng dụng và người dùng, gồm có 3 thư mục con:

* Documents: dữ liệu của người dùng sinh ra trong quá trình sử dụng ứng dụng, hoặc các dữ liệu mà ứng dụng muốn cho phép người dùng truy cập sẽ được lưu tại đây.
* Library: chứa những dữ liệu không thuộc về người dùng, những dữ liệu không muốn người dùng đọc được. Tại thư mục này sẽ gồm vài thư mục con, trong đó 2 thư mục con thường được các ứng dụng iOS sử dụng nhiều nhất là:

  * Application Support: chứa toàn bộ dữ liệu chính của ứng dụng.
  * Caches: chứa những dữ liệu có thể tái tạo lại, hoặc không tạo ảnh hưởng lớn khi chẳng may bị thay đổi nội dung hoặc chỉnh sửa.
  * Preferences: chứa các tệp tin cấu hình của ứng dụng. Trong đó có tệp tin tên là ***<BundleID>.plist*** chứa các thông tin chính, tệp tin này được quản lý qua class NSUserDefaults.
* Temp: lưu các dữ liệu tạm thời trong quá trình ứng dụng hoạt động. Khi ứng dụng ngừng hoạt động, hệ điều hành sẽ cưỡng ép xoá dữ liệu trong thư mục này.

![](<>)

**iCloud container** chứa các dữ liệu của ứng dụng được tải lên iCloud.

![](<>)

# 2. Local storage

Local storage là nơi đảm nhiệm việc lưu các dữ liệu của ứng dụng trên thiết bị iOS, tương ứng với khối Data container đã đề cập ở phần trên. Tại đây có rất nhiều thứ cần chú ý và kiểm tra khi thực hiện kiểm thử bảo mật cho ứng dụng iOS. Để kiểm tra và đọc dữ liệu trong local storage chúng ta có thể sử dụng phần mềm GrapeFruit (<https://github.com/ChiChou/grapefruit>).

## 2.1. Core data

Đây là phương pháp lưu trữ dữ liệu chủ yếu được Apple khuyên dùng. Mặc định thì phương pháp Core Data sẽ lưu trữ dữ liệu vào trong các file .db và thực hiện việc đọc ghi qua SQLite.

![](<>) ![](<>)

Tệp tin core data có thể được tìm thấy tại Home > Library > Application Support.

## 2.2. Property List (plist)

Các tệp tin plist lưu trữ dữ liệu bằng cấu trúc XML, tương tự như Shared Preferences đối với ứng dụng Android. Thường thì ứng dụng sẽ lưu trữ các thông tin cấu hình trong đây, tuy nhiên đôi khi một số dữ liệu nhạy cảm cũng có thể được lưu tại đây.

![](<>)

## 2.3. NSUserDefaults

Thường được sử dụng để lưu trữ các thông tin của user, các cấu hình cài đặt và trạng thái của ứng dụng. NSUserDefaults có thể lưu trữ được nhiều kiểu dữ liệu cơ bản như bool, int, float, string, dictionary,… và cả các kiểu dữ liệu tương thích với plist tuy nhiên, NSUserDefaults không lưu được các dữ liệu lớn và phức tạp. Dữ liệu sẽ được lưu tại đây theo cấu trúc **key - value**.

![](<>) ![](<>)

| Ưu điểm                                                                                     | Nhược điểm                       |
| ------------------------------------------------------------------------------------------- | -------------------------------- |
| \- Lưu trữ được nhiều kiểu dữ liệu. - Sử dụng đơn giản, ít tốn chi phí tài nguyên hệ thống. | \- Chỉ lưu được các dữ liệu nhỏ. |

## 2.4. Keychain

Keychain là một nơi lưu trữ thông tin rất an toàn cho các ứng dụng iOS. Ứng dụng thường được khuyến nghị sẽ lưu trữ các dữ liệu tuyệt mật như mật khẩu, khoá mã hoá, chứng chỉ SSL,… Việc lưu trữ và đọc dữ liệu từ Keychain sẽ được thực hiện qua API có sẵn.

![](<>)

Dữ liệu lưu trong Keychain sẽ được mã hoá. Thường thì khi lưu một dữ liệu vào Keychain, lập trình viên có thể lưu trữ dưới dạng đối tượng Keychain Item như sau:

![](<>)

Keychain có thể được trích xuất ra từ ứng dụng cài đặt trên thiết bị. Trong trường hợp dữ liệu lưu vào Keychain không được mã hoá thì việc bị lộ dữ liệu là hoàn toàn có thể xảy ra.

![](<>)

## 2.5. Webkit Caching

Ứng dụng sẽ cache lại một số nội dung khi duyệt web, trong đó có thể chứa những thông tin nhạy cảm. Các file cache này được lưu tại Data Container của ứng dụng.

![](<>)

## 2.6. Một số CSDL

Bên cạnh các nơi lưu trữ dữ liệu nói trên thì ứng dụng iOS còn có thể sử dùng các CSDL khác dưới đây.

### 2.6.1. Realm DB

Realm là một loại cơ sở dữ liệu được sử dụng bởi các ứng dụng di động, ứng dụng desktop, ứng dụng phát triển bằng React Native,... Realm có ưu điểm là dễ sử dụng nhờ các API được thiết kế đơn giản, trực quan, dễ hiểu; Realm cũng hỗ trợ tốt cho việc đẩy dữ liệu lên Cloud, giúp cho việc phát triển các ứng dụng hoạt động trên đa nền tảng tốt hơn.

Để đọc được dữ liệu trong Realm DB cần sử dụng phần mềm riêng tên là Realm Browser, không thể đọc dữ liệu trong Realm DB trên phần mềm GrapeFruit được. Người dùng MacOS có thể tải trực tiếp phần mềm này qua App Store.

![](<>)

![](<>)

![](<>)

### 2.6.2. Couchbase Lite DB và Yap DB

Hai cơ sở dữ liệu này ít được sử dụng hơn so với các phương pháp lưu trữ dữ liệu khác. Couchbase và Yap DB có thể đọc bằng phần mềm SQLite DB Browser và GrapeFruit.

![](<>)

![](<>)

- - -

Trên đây là những nơi chúng ta cần kiểm tra đối với Local Storage của một ứng dụng iOS. So với Android thì iOS có nhiều lựa chọn để lưu trữ dữ liệu trên thiết bị hơn, do đó cũng cần phải chú ý nhiều hơn để không bỏ sót.