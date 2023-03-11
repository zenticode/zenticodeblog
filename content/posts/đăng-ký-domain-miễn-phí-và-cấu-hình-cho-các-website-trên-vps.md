---
title: Đăng ký domain miễn phí và cấu hình cho các website trên VPS
date: 2023-03-11 09:22
tags:
  - VPS
description: Đôi khi vì nhu cầu công việc bạn cần một domain miễn phí để tiết
  kiệm chi phí và thuận tiện hơn. Có khá nhiều nhà cung cấp tên miền miễn phí.
  Tuy nhiên trong bài viết này mình sẽ hướng dẫn cách kiếm 1 tên miền trên
  freenom và cấu hình nó cho 1 website thực tế.
---




![](https://images.viblo.asia/02538421-c96e-40f3-9abf-d45b0284e308.png)

Đôi khi vì nhu cầu công việc bạn cần một domain miễn phí để tiết kiệm chi phí và thuận tiện hơn. Có khá nhiều nhà cung cấp tên miền miễn phí. Tuy nhiên trong bài viết này mình sẽ hướng dẫn cách kiếm 1 tên miền trên freenom và cấu hình nó cho 1 website thực tế.

Demo cấu hình được sử dụng cho 1 website chạy trên Google VPS, bạn có thể sử dụng nó trên một VPS bất kỳ hoặc ngay chính chiếc PC của bạn.

Dịch vụ freenom [http://www.freenom.com](http://www.freenom.com/) .

## Index

1. Đăng ký nhanh freenom domain
2. Quản lý DNS, thêm subdomain
3. Cấu hình domain/subdomain với apache trên VPS

Mình có một số thông tin sau :

* VPS Linux của Google có External IP : `35.201.177.xxx`
* Domain sẽ đăng ký : `traigakyky.ga`.
* Subdomain cho admin site : `admin.traigakyky.ga`

## Đăng ký freenom domain

> Chỉ cần có một tài khoản freenom là bạn có thể đăng ký ngay nhiều domain free, hiện freenom hỗ trợ 5 domain sau `.tk`, `.ml`, `.ga`, `cf`, `.gq`

Đăng ký nhanh một tài khoản trên [freenom.com](http://freenom.com/), hoặc sử dụng Google Social Signin. Sau đó thực hiện các bước sau để đăng ký

* Dưới menu `Services` chọn `Register a New Domain` , hoặc link <https://my.freenom.com/domains.php>
* Nhập tên domain và click `Check Availability`
* `Get It Now!` một domain và chọn Checkout
* Mục `Use DNS` , IP Address là External IP của VPS `35.201.177.xxx` ( xem ảnh phía dưới)
* Xác thực lại ( nếu có) hoặc chuyển sang bước tiếp theo
* Review & Checkout lần cuối, các thông tin form là không bắt buộc vì vậy bạn chỉ cần accept `I have read and agree to Terms & Conditions` là đủ. `Complete Order`
* Order Comfirmation - Chúc mừng bạn đã hoàn tất đăng ký

![](https://images.viblo.asia/20ece73b-25b5-4865-b9f6-686c50087bbd.png)

Nhập tên domain và click `Check Availability` ![](https://images.viblo.asia/02880081-dcb3-416f-a774-fd3985a8dada.png)

Chọn một domain và Checkout![](https://images.viblo.asia/7c54d3eb-e425-45b9-81b3-d140e9e05777.png)

Tại mục này chọn `Use DNS` và thiết lập các thông số tương ứng VPS của bạn --> `Continue` ![](https://images.viblo.asia/6392533a-326c-4fee-af00-364a171f3ca7.png)

Review & Checkout , bạn chỉ cần nhập các thông tin cơ bản. Các thông tin này không bắt buộc vì vậy bạn chỉ cần accept `I have read and agree to Terms & Conditions` là đủ. `Complete Order` ![](https://images.viblo.asia/a1bc86f4-ad36-4c7e-861e-619094cc1dfa.png) ![](https://images.viblo.asia/50a7e0be-70cf-4a3f-baeb-7a818a9db78f.png)

Như vậy là đã hoàn tất việc đăng ký.

> Lưu ý : ở bước Review & Checkout có thể bạn cần phải đăng nhập lại trước khi `Complete Order`.

## Quản lý DNS, thêm subdomain

Tại đây bạn có thể quản lý DNS cho domain, cập nhật DNS nếu như sau này có sự thay đổi. Hoặc thêm các bản ghi DNS tương ứng.

Sau khi hoàn tất đăng ký, tiếp theo mình thêm một bản ghi Address Mapping - `A Record` cho subdomain trỏ về VPS.

### Tạo subdomain

Dưới menu `Services` -> chọn `My Domains` hoặc link sau <https://my.freenom.com/clientarea.php?action=domains>

Tại đây bạn sẽ thấy các domains đã đăng ký --> Chọn `Manage Domain` để vào trang quản lý ![](https://images.viblo.asia/1dc1e75f-ea03-477d-905f-fd33f6915126.png)

Chọn tab `Manage Freenom DNS` ![](https://images.viblo.asia/d7155f37-dd1d-417b-8b73-13fa2cc04c3a.png)

Trang DNS MANAGEMENT xuất hiện, dưới phần **Add Record** .

* `Name` : Tên bản ghi, ở đây là `admin` ( sẽ được hiểu là [admin.traigakyky.ga](http://admin.traigakyky.ga/))
* `Type` : là `A` ( Address Mapping)
* TTL (Time To Live) : thời gian mà name server được cập nhật, đơn vị second
* Target : DNS mà domain sẽ trỏ tới, ở đây mình nhập External IP của VPS

![](https://images.viblo.asia/47c9be3e-7fcd-486d-9142-27531c1db899.png)

Kết quả sẽ như dưới.![](https://images.viblo.asia/7120b20c-7122-4a68-b773-15b476fdf0f3.png)

Như vậy việc cấu hình DNS cho Domain để trỏ về VPS đã hoàn tất. Tiếp theo là cấu hình domain name trên apache server

## Cấu hình domain/subdomain với apache trên VPS

Phần demo cấu hình này được thực hiện trên apache với kiến trúc luồng hệ thống như sau![](https://images.viblo.asia/02538421-c96e-40f3-9abf-d45b0284e308.png)

Mọi request sẽ đi qua apache , khi client request với domain tương ứng , apache --> sẽ điều hướng sang services tương ứng.

Trong bài này mình có 3 services

* 1 website cho phía user
* 1 website cho phía admin
* 1 service deploy website chạy trên Tomcat port 8080 ( port internal)

#### Cấu hình domain cho các website

Tạo file `my_domain.conf` trong thư mục `/etc/apache2/sites-available` như sau ( tên file tùy ý)

```ApacheConf
# Domain user
<VirtualHost *:80>
    ServerName traigakyky.ga

    # Thư mục triển khai web
    DocumentRoot /var/www/webapp/frontend
    <Directory /var/www/webapp/frontend>
        Options Indexes FollowSymLinks MultiViews
        AllowOverride All
        Order allow,deny
        allow from all
    </Directory>
</VirtualHost>

# Domain admin
<VirtualHost *:80>
    ServerName admin.traigakyky.ga

    # Thư mục triển khai web
    DocumentRoot /var/www/webapp/backend
    <Directory /var/www/webapp/backend>
        Options Indexes FollowSymLinks MultiViews
        AllowOverride All
        Order allow,deny
        allow from all
    </Directory>
</VirtualHost>

# Domain build - behind proxy
<VirtualHost *:80>
    ServerName build.traigakyky.ga
    ProxyRequests Off
    ProxyVia Off
    ProxyPreserveHost On
    AllowEncodedSlashes On

    #sử dụng behind proxy, redirect port 80 --> sang 8080 của tomcat
    ProxyPass /     http://localhost:8080/
</VirtualHost>
# Để sử dụng behind proxy, bạn cần enable proxy module trên apache2

```

Enable site config

```none
sudo a2ensite my_domain.conf

```

Reload lại apache2

```none
sudo service apache2 reload 

```

Với domain `build.traigakyky.ga` , do service đó sử dụng port 8080 trên tomcat. Áp dụng kỹ thuật behind proxy để redirect toàn bộ request external port 80 --> sang internal port 8080. Điều đó có nghĩa là, mọi request từ domain `build.traigakyky.ga` với port 80, thì các xử lý đó đều forward request đó đến port 8080 và xử lý internal.

> Trong bài viết không đề cập đến việc tạo domain `build.traigakyky.ga`. Đó là một domain nằm ngoài nội dung - mục đích để chúng ta thấy việc áp dụng domain trong nhiều bài toán khác nhau.

Giờ hãy thử nhập từng domain trên trình duyệt để thử kết quả nhé!

N﻿guồn: [Viblo](https://viblo.asia/p/dang-ky-domain-mien-phi-va-cau-hinh-cho-cac-website-tren-vps-ORNZqP48K0n)