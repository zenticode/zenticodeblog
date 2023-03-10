---
title: Thêm domain cho EC2 trên AWS
date: 2023-03-10 17:30
description: Hello ae, chắc ae cũng đã làm việc với cloud ít nhiều thì mới thấy
  đc bài của mình hihi😅😅😅. Bài này mình sẽ chia sẻ quá trình set up để con
  server của bạn mapping được với 1 cái domain, từ đó tha hồ nghịch mấy cái khác
  mà không cần đế mấy cái dịch vụ hosting. mình là sv nên mình hiểu, AWS free
  mấy cái thì mình xài thôi😁😁😁.
---
# Lời mở đầu

Hello ae, chắc ae cũng đã làm việc với cloud ít nhiều thì mới thấy đc bài của mình hihi😅😅😅. Bài này mình sẽ chia sẻ quá trình set up để con server của bạn mapping được với 1 cái domain, từ đó tha hồ nghịch mấy cái khác mà không cần đế mấy cái dịch vụ hosting. mình là sv nên mình hiểu, AWS free mấy cái thì mình xài thôi😁😁😁.

Nếu mình hiểu sai cái nào, xin ae bình luận để mình sửa lại nhé, cảm ơn ae

# Nguyên liệu

Để chơi được món này, bạn cần có:

* 01 Domain
* 01 Ec2
* 01 Elastic IP
* time, thường thì dưới 24h, nếu set up đúng, nếu sai thì đợi mai lại làm lại

Cụ thể:

1. Về domain, các bạn có thể mua domain ở đâu tùy thích, mình thì mua ở tenten nhé. Các bạn chịu khó bỏ vài chục mua cái domain cho chất lượng chứ kiếm free là éo ra đâu, tốn thời gian nữa.

Mình khuyên vậy thôi chứ ai mà kiếm được domain free thì cho mình xin link với😂😂😂

Như mình đã mua một cái .click đây, 20k thêm cái thuế là 22k cho 1 năm, sau đó các bạn có thể tạo thêm sub-domain nữa, tha hồ domain nhé. Mua sao thì các bạn cứ như mua hàng online nhé, thanh toán online ae ạ, éo có momo mới cay, ae phải có zalopay các kiểu kìa. Nhưng thôi, rẻ nên cứ chơi.![image.png](https://images.viblo.asia/a44b85ec-3d45-4cd1-b235-f0ae9a5c8b97.png)

2. Ok về ec2,

Ae cứ set up bình thường nhé, riêng cái khúc network setting thì ae click cả 3 cái tí nữa đỡ phải set up lại.🤐🤐🤐🤐![image.png](https://images.viblo.asia/498d7567-b6cf-4445-bdb1-f67b79ed8f3d.png)Nếu ae có sẵn ec2 r thì cứ make sure là nó connect được qua http với https là được, không phải cài lại cái mới nha,

sau đó thì ae set up nginx server đi nhé, setup nginx [theo thằng này cũng được nha](https://www.digitalocean.com/community/tutorials/how-to-install-nginx-on-ubuntu-20-04) Khi nào mà ae vào public IP mà nó ra được như này là ok để bước tiếp theo nhé![image.png](https://images.viblo.asia/bf2eadb7-be15-4bfc-b042-c8d45bd1c45f.png)

3. Về elastic IP

Ae start 1 elastic IP và sau đó connect với ec2 của mình, nhớ là allocate xong là connect với ec2 liền nha, không nếu mình tạo elastic IP mà để không không là nó trừ tiền theo giờ á,

Lý do mình tạo 1 elastic IP là vì mỗi khi start hay reboot ec2 nó sẽ gắn với một địa chỉ IP mới, nhưng với elastic IP nó sẽ luôn cố định cho ae,

Như mình hiện tại có 1 cái elastic IP là![image.png](https://images.viblo.asia/a2594fc7-666b-4854-b152-5e8387259403.png)52.76.158.xx

Ok nguyên liệu có hết r, giờ connect với domain thôi, cái này thì quá đơn giản luôn

# Nấu

1. Click vào cài đặt DNS

![image.png](https://images.viblo.asia/95fcdbf5-5b61-4190-8469-ed2e417bc773.png)2. Click vào cấu hình IP

![image.png](https://images.viblo.asia/75fd8b23-d009-4e0c-992e-7681818ea2f7.png)Nhập địa chỉ elastic IP của ae vào

Đợi xíu nó sẽ generate 1 cục ntn

![image.png](https://images.viblo.asia/90e9b1fd-dd24-4770-b15c-7d7819e0bfa7.png)

Như ae thấy đó, đợi nhiều nhất 24 giờ và tận hưởng thôi,

# Sẽ ngon hơn nếu

Mình hướng dẫn ae set up đơn giản, chủ yếu là mình sẽ kết nối qua domain, nó sẽ đơn giản hơn là sử dụng route 53 của AWS, nói đến cái này lại cay, mình mất vài chục vì cái route 53 này r, nên mong ae không mất tiền oan. sài AWS thì sướng mà tốn thui,

Cái này sẽ nằm trong seri

Set up nginx và laravel trên ec2

Kết nối RDS đến ec2

Connect ec2 to a domain

Http -> Https for nginx,

Nếu ae ủng hộ bài này mình sẽ làm những bài tiếp theo, Ok, ae ngồi đợi và thưởng thức thôi nha, nếu có lỗi gì thì cứ comment ở đây, không mình thì những ae khác sẽ giúp.

N﻿guồn: [Viblo](https://viblo.asia/p/them-domain-cho-ec2-yZjJYzwMLOE)