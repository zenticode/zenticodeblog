---
title: Cách cài nhiều Node.js version trên cùng một máy
date: 2023-05-16 09:05
tags:
  - NodeJS
  - NVM
description: Trong bài viết này, chúng ta sẽ tìm hiểu cách cài đặt nhiều phiên
  bản Node.js trên cùng một máy tính sử dụng Node Version Manager (nvm). Thư
  viện cho phép chúng ta cài đặt nhiều phiên bản Node.js và chuyển qua lại giữa
  các phiên bản chỉ bằng một câu lệnh.
---
Nếu bạn đang là một lập trình viên hoặc đang học lập trình, bạn có thể đã biết rằng phiên bản Node.js được cập nhật thường xuyên.

Vì vậy, khi bạn phát triển một ứng dụng sử dụng Node.js, có thể cần phải sử dụng nhiều phiên bản khác nhau của Node.js để đảm bảo tính tương thích của ứng dụng với các phiên bản Node.js khác nhau.

Trong bài viết này, chúng ta sẽ tìm hiểu cách cài đặt nhiều phiên bản Node.js trên cùng một máy tính sử dụng **Node Version Manager (nvm)**. Thư viện cho phép chúng ta cài đặt nhiều phiên bản Node.js và chuyển qua lại giữa các phiên bản chỉ bằng **một câu lệnh**.

- - -

![image.png](https://images.viblo.asia/661164be-b367-4dfb-b50f-8570879a5b0f.png)

# Cách Cài Đặt nvm

## Windows

* Đầu tiên, tải xuống phiên bản mới nhất của **nvm-windows** [ở đây](https://github.com/coreybutler/nvm-windows/releases/latest).
* Tiếp theo, tải file `nvm-setup.zip` và tiến hành cài đặt như bao chương trình khác.
* Cuối cùng, để kiểm tra ta chạy lệnh sau ở terminal/powershell:

```none
nvm version

```

*(Nếu **nvm-windows** không hoạt động ngay sau khi cài đặt, hãy thử khởi động lại terminal/powershell)*

*(Hoặc bạn có thể follow theo [trang hướng dẫn cài đặt chính chức cho Windows](https://github.com/coreybutler/nvm-windows#installation--upgrades) của **nvm-windows**)*

## Mac/Linux

Để cài đặt trên Mac/Linux bạn có thể sử dụng:

* **cURL**:

```none
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.3/install.sh | bash

```

* Hoặc **Wget**:

```none
wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.3/install.sh | bash

```

Cuối cùng, để kiểm tra ta chạy lệnh sau ở terminal:

```none
command -v nvm

```

*(Hoặc bạn có thể follow theo [trang hướng dẫn cài đặt chính chức cho Mac/Linux](https://github.com/nvm-sh/nvm#installing-and-updating) của **nvm-sh**)*

# Cách Sử Dụng nvm

## Liệt kê tất cả các phiên bản available

Cho **Windows**:

```none
nvm ls available

```

Cho **Mac/Linux**:

```none
nvm ls-remote

```

## Cài đặt phiên bản Node.js mới nhất

```none
nvm install node

```

## Cài đặt phiên bản LTS Node.js mới nhất

```none
nvm install --lts

```

## Cài đặt phiên bản Node.js cụ thể

```none
nvm install 8.11.1 // để cài phiên bản 8.11.1

nvm install 12.13.1 // để cài phiên bản 12.13.1
```

## Xóa phiên bản Node.js

```none
nvm uninstall 8.11.1

```

# Cách Chuyển Qua Lại Giữa Các Phiên Bản

## Liệt kê tất cả các phiên bản đã cài đặt

Cho **Windows**:

```none
nvm list

```

Cho **Mac/Linux**:

```none
nvm ls

```

## Chuyển đổi qua lại các phiên bản

```none
nvm use 8.11.1  // chuyển qua phiên bản 8.11.1

nvm use 12.13.1 // chuyển qua phiên bản 12.13.1
```

## Cài Alias cho từng phiên bản

```none
nvm alias awesome-project 12.13.1

```

Để xóa alias, ta sử dụng lệnh sau:

```none
nvm unalias awesome-project

```

## Chạy trực tiếp, không cần chuyển

```none
nvm run 8.11.1 app.js

```

hoặc

```none
nvm exec 8.11.1 node app.js

```

# Một Số Lệnh Khác

> `$ nvm`+ `Tab`

```sh
alias               deactivate          install             list-remote         reinstall-packages  uninstall           version
cache               exec                install-latest-npm  ls                  run                 unload              version-remote
current             help                list                ls-remote 
```

# Tổng Kết Lại

**Node Version Manager (nvm)** là một công cụ tuyệt vời giúp chuyển đổi giữa nhiều phiên bản Node.js trong khi làm việc trên các dự án với nhiều phiên bản khác nhau. Nó giúp cách anh em Develoepr tiết kiệm thời gian bằng cách thay đổi nhanh chóng qua lại giữa các phiên bản Node.js

N﻿guồn: [Viblo](https://viblo.asia/p/cach-cai-nhieu-nodejs-version-tren-cung-mot-may-0gdJz72jLz5)