---
title: Tìm hiểu về DNS
date: 2023-03-29 17:31
tags:
  - DNS
description: DNS (Domain Name System) là hệ thống đứng trung gian để dịch từ tên
  miền ở ngôn ngữ tự nhiên như google.com thành địa chỉ IP như 172.168.23.14
---
## DNS là gì ?

Người dùng sử dụng web thông qua các tên miền (domain) của trang web như [beautyoncode.com](http://beautyoncode.com/). Các trình duyệt web thì lại tương tác bằng địa chỉ IP.

DNS (Domain Name System) là hệ thống đứng trung gian để dịch từ tên miền ở ngôn ngữ tự nhiên như [google.com](http://google.com/) thành địa chỉ IP như 172.168.23.14

Dễ hình dung nhất là DNS giống như cuốn danh bạ điện thoại vậy, tên là domain còn số địện thoại là địa chỉ IP cần tìm.

![](https://i0.wp.com/beautyoncode.com/wp-content/uploads/2023/03/what_is_dns.png)

DNS sử dụng cấu trúc phân cấp theo tên:

✅ top level domain (TLD): .com

✅ second level domain (SLD): [google.com](http://google.com/)

✅ sub domain: [www.google.com](http://www.google.com/), [api.beautyoncode.com](http://api.beautyoncode.com/)

## Các thuật ngữ về DNS

✅ **Domain registrar**: nhà đăng ký tên miền, như Godaddy, Route53

✅ **DNS records**: bản ghi DNS như A, AAAA, CNAME, NS

✅ **Zone file**: chứa các bản ghi

✅ **Name server**: nơi giải quyết các truy vấn DNS

✅ **Top level domain (TLD)**: như .com, .vn, .org

✅ **Second level domain (SLD)**: [beautyoncode.com](http://beautyoncode.com/), [amazon.com](http://amazon.com/)

**Thử phân tích url này: [https://api.www.beautyoncode.com](https://api.www.beautyoncode.com/)**

👉🏻 https: protocol

👉🏻 [api.www.beautyoncode.com](http://api.www.beautyoncode.com/): FQDN hay Fully Qualified Domain Name

👉🏻 [www.beautyoncode.com](http://www.beautyoncode.com/): sub domain

👉🏻 [beautyoncode.com](http://beautyoncode.com/): SLD, hay apex domain

👉🏻 .com: TLD

## DNS hoạt động như thế nào?

### Các loại DNS Server

Có 4 loại DNS servers liên quan trong quá trình tìm kiếm địa chỉ IP của server của một trang web:

– **DNS recurso**r: có thể hình dung như người thủ thư của thư viện, là người giúp tìm quyển sách ở trong thư viện. DNS recursor là server nhận yêu cầu từ máy client rồi có trách nhiệm yêu cầu thêm những request khác để tìm được địa chỉ IP.

– **Root nameserver**: là bước đầu tiên giúp chuyển đổi domain sang địa chỉ IP. Có thể hình dung nó giống như các chỉ mục index A, B, C trong thư viện nơi trỏ đến các giá sách khác nhau.

– **TLD nameserver**: là top level domain server, là bước tiếp theo sao root nameserver. Có thể hình dung nó như các giá sách.

– **Authoritative nameserver**: là máy chủ cuối cùng nơi chứa địa chỉ IP của tên miền. Có thể hình dung nó như một cuốn từ điển trên giá sách, nơi bạn có thể tra nghĩa của một từ.

![](https://i0.wp.com/beautyoncode.com/wp-content/uploads/2023/03/dns_record_request_sequence_recursive_resolver.png)(image from cloudflare)

**Cùng xem cách DNS hoạt động qua ví dụ sau:**

![](https://i0.wp.com/beautyoncode.com/wp-content/uploads/2023/03/dns-how-to-work.png)

Khi người dùng gõ một url vào trình duyệt, ví dụ gõ [google.com](http://google.com/):

– (2) máy tính gửi yêu cầu hỏi địa chỉ IP của [google.com](http://google.com/), Local DNS Server nhận được

– (3) **Local DNS server** không biết nên gửi yêu cầu đến Root DNS Server (.) hỏi địa chỉ IP của [google.com](http://google.com/)

– (4) **Root DNS Server** gửi về IP 1.2.3.4 của TLD DNS Server .com (hay .com NS) nơi chứa thông tin của [google.com](http://google.com/)

– (5) **Local DNS Server** tiếp tục gửi yêu cầu đến TLD DNS Server .com với IP 1.2.3.4 để hỏi địa chỉ IP của SLD DNS Server (hay [beautyoncode.com](http://beautyoncode.com/) NS)

– (6) **TLD DNS Server** gửi về IP của SLD DNS Server (hay google NS) là 5.6.7.8

– (7) **Local DNS Server** tiếp tục gửi yêu cầu đến SLD DNS Server [google.com](http://google.com/) với IP 5.6.7.8 để hỏi địa chỉ IP của “[beautyoncode.com](http://beautyoncode.com/)”

– (8) **SLD DNS Server** gửi về IP của [beautyoncode.com](http://beautyoncode.com/) là 9.10.11.12

– (9) **Local DNS Server** gửi IP 9.10.11.12 về cho máy của client, cũng lưu lại một bản cache cho mình.

– (10) **Client** gửi yêu cầu đến **server** có IP 9.10.11.12 để nhận trang nội dung trang web trả về (11) và hiển thị lên màn hình. Máy client cũng sẽ lưu lại IP ở cache để sử dụng cho lần yêu cầu tiếp theo.

Ở ví dụ bên trên:

– Local DNS Server là DNS recursor

– Root DNS Server là Root nameserver

– TLD DNS Server là TLD nameserver

– SLD DNS Server là Authoritative nameserver

## Bản ghi DNS (DNS Record)

![](https://i0.wp.com/beautyoncode.com/wp-content/uploads/2023/03/record-dns.png)

Bản ghi DNS là cách bạn cấu hình các lưu lượng gửi đến domain

Mỗi bản ghi bao gồm:

✅ Tên Domain hoặc sub domain

✅ Loại bản ghi (record type): phổ biến là A, AAAA, CNAME, NS

✅ Giá trị (value, data): địa chỉ IP của A record, url của của CNAME

✅ Chính sách định tuyến (Routing policy – có ở Route53)

✅ TTL: thời gian cache ở DNS resolver

## Record type A, CNAME và alias record

**Record type A** gắn với địa chỉ IPv4 cụ thể.

*Ví dụ:* khi bạn muốn domain của mình gắn đến địa chỉ IP của github page là 172.168.76.89 thì sẽ cần tạo một record loại A

**Record type CNAME** giúp gắn domain của bạn với đến domain khác, và domain này cần phải có địa chỉ IP hay record A gắn vào nó.

Không thể tạo CNAME cho SLD domain (apex domain) như [beautyoncode.com](http://beautyoncode.com/). Nhưng có thể tạo CNAME record cho sub domain như [www.beautyoncode.com](http://www.beautyoncode.com/)

*Ví dụ:* sau khi đã gắn IP của github vào record A ở trên, bạn tạo thêm một record loại CNAME để chuyển truy cập từ [www.beautyoncode.com](http://www.beautyoncode.com/) sang [beautyoncode.com](http://beautyoncode.com/).

Khi đó, trang web của bạn đã chuyển từ [account.github.io](http://account.github.io/) sang [domain.com](http://domain.com/) thành công (lưu ý TTL để kiểm tra lại, có thể là 24h)

**Alias** giúp gắn domain của bạn đến các nguồn tài nguyên khác như AWS ALB, và có thể sử dụng với apex domain. Loại record thường sử dụng cho alias là A và không gán TTL.

- - -

Bài viết đã giới thiệu đến bạn một số kiến thức cơ bản về DNS như khái niệm, các thuật ngữ, cách hoạt động, các loại bản ghi. Bài viết được đăng lại từ [bài gốc trên blog BeautyOnCode](https://beautyoncode.com/tim-hieu-ve-dns/)