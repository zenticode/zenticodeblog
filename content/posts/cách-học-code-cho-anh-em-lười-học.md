---
title: Cách học code cho anh em lười học
date: 2023-03-01 17:02
tags:
  - Code
  - Beginner
description: Tất cả những bài viết về cách học code sao cho nhanh ở trên mạng
  mình khuyên thật là các bạn nên quên hết đi. Hầu hết chỉ toàn là self help
  kiểu "Hãy code đi" "Hãy bắt tay vào làm" "Code ngay bây giờ", ... đây toàn là
  điều ai cũng biết.
---
**Tất cả những bài viết về cách học code sao cho nhanh ở trên mạng mình khuyên thật là các bạn nên quên hết đi. Hầu hết chỉ toàn là self help kiểu "Hãy code đi" "Hãy bắt tay vào làm" "Code ngay bây giờ", ... đây toàn là điều ai cũng biết.**

Hơn nữa, những cách khác như tìm một mentor giỏi, tìm bạn đồng hành, tìm nhóm học chung,... lại quá lý tưởng và không phải ai cũng có thể có được.

Dưới đây mình sẽ trình bày một cách học code mà mình tự giác ngộ ra trong quá trình học tập và làm việc. Lưu ý mình thấy nó hiệu quả với bản thân mình, chưa chắc đã hiệu quả với tất cả mọi người, nên anh em đọc với mục đích tham khảo, và nếu thấy hợp lý thì hãy áp dụng.

## 1. Cách học code của mọi người

Theo mình thấy đây là cách học code phổ biến hiện nay của sinh viên IT nói chung: *đọc qua document của framework đó để hiểu những hàm cần thiết build được server, xem youtube khóa học, sau đó làm một số project nho nhỏ hoặc nhận task làm đến đâu tìm hiểu đến đấy*.

![image.png](https://images.viblo.asia/18fef1c9-7112-44af-b3a6-7671727db5ca.png)

Ngoài ra có thằng bạn mình có cách học khác. Cách học này là đọc toàn bộ document về một framework, bao gồm tất cả những điều không dùng tới cho một dự án.

***Theo những cách trên, mình nhận ra một số mặt lợi và hại.***

*Thứ nhất*, cách học thông thường của mọi người là đọc docs, tutorial một vài điều cơ bản rồi sau đó làm những project nho nhỏ. Cách học này phổ biến bởi vì ai cũng có thể nghĩ ra được, và nó dễ tiếp cận, ít gây nhàm chán vì có thể áp dụng được ngay vào thực tiễn. Tuy nhiên điểm yếu là anh em bị lệ thuộc vào tutorial đó, những gì trong hướng dẫn không có thì anh em không làm được, hoặc sẽ mất thêm thời gian lâu hơn để tìm hiểu. Nó sẽ tốt hơn với việc copy paste code một chút, nhưng bản chất là gần như nhau. Các tutorial chỉ có những phần cực kì cơ bản và không có những trường hợp khó.

Một người mới về Spring sẽ không bao giờ tìm kiếm tutorial Spring + Elastic Search, trong khi thực tế rất nhiều hệ thống sử dụng chúng. Nếu anh em được tuyển dụng vào một công ty sử dụng các công nghệ này với những kiến thức ít ỏi có được từ các video tutorial thì việc tiếp cận với hệ thống trở nên cực kì khó khăn.

*Thứ hai*, cách học như thằng bạn của mình là đọc toàn bộ document, hiểu tường tận một framework rồi mới làm. Ưu điểm thì quá rõ ràng, đó là mình nắm trong tay toàn bộ công nghệ, chiến được mọi dự án cùng con framework đó. Nhược điểm là mất rất nhiều thời gian. Một framework có hàng trăm cách khác nhau để connect đến các loại database, có hàng trăm các API cùng chức năng. Đặc biệt những ngôn ngữ như Python thư viện đồ sộ thì có thể có rất nhiều thư viện hỗ trợ cho 1 chức năng nhỏ lẻ.

*Việc học sâu một framework sẽ giúp người học thuần thục nó hết cỡ*. Như thằng bạn mình giờ cũng phải trình ngang Senior Nodejs rồi (đúng cái framework mình cay cú nhất). Bù lại, thằng bạn mình đã mất 3 năm chỉ sử dụng một framework đó để làm Web.

Mình không đánh giá cách nào là đúng, cách nào là sai, chỉ là nó phù hợp với người nào mà thôi. Và mình cũng đã đưa ra ưu nhược điểm của các cách học. Sau đây là cách học của mình

## 2. Cách học code của mình

Cách học thứ nhất mình trình bày trên kia là học qua loa framework, sau đó vào dự án thật thì mới bắt đầu tìm hiểu những thứ cần thiết cho task đó.

Cách học thứ 2 là học thật kĩ framework đó, làm bố của framework sau đó dùng nó chiến mọi dự án.

***Lúc trước mình hay học theo cách thứ 1***. Framework lúc đó mình dùng là Flask trong Python vì phải học nhanh để thi Hackathon, giờ gần như là quên hết rồi. Sau đó mình học theo cách thứ 2 với Windows MFC trong C++ để làm app Windows, học từng cái button, text box, ... Công nhận là đến lúc vào code thì làm vù vù, chỉ có điều giờ chẳng còn ai dùng thằng này nữa vì nó low tech quá nên mình cũng bỏ rồi.

Mình cảm thấy cách 1 vẫn hiệu quả với mình hơn vì mình không kiên trì, và đã nghĩ là đây chắc là chân ái rồi, cho đến khi ông anh ở công ty thứ 2 mở ra chân trời mới trong code cho mình.

**Người đã cho mình biết như thế nào mới là code.** (Dear Mr.D, if you read this article, I would like to say a big thank to you, you're like a benefactor that saved my life 🫠)![image.png](https://images.viblo.asia/5fc6b455-ecb0-43f2-91c7-902e781ab093.png)

Mình đã tìm ra được cách trung hòa 2 cách học trên, đọc docs không ít (như cách 1) mà cũng không nhiều (như cách 2) - **học dựa trên code base**.

**Code base là một project đã được xây cấu trúc tốt, có sẵn kết nối với một database nào đó, viết sẵn các phần nền phải dùng cho mọi project (như http response, route, ...)**. Việc anh em cần làm ở đây là hiểu nó đã support những chức năng gì, cụ thể dùng ra sao, phải thêm những cái gì để phục vụ cho project riêng của mình. Quá trình đọc docs sẽ nhiều hơn so với cách 1, vì các hàm đã viết sẵn là rất nhiều, nhưng bù lại sẽ đọc vào các hàm quan trọng nhất, sử dụng nhiều nhất trong framework đó, thế nên không mất công phải đọc vào các phần không sử dụng như cách số 2.

Lần đầu tiên mình học theo phương pháp này đó là khi mình làm project đầu trên công ty là xây dựng một bộ giải pháp bao gồm cả server và agent sử dụng framework *FastAPI* trong Python, database là *Postgresql*, deadline chỉ có 10 ngày tính từ khi có mô tả chi tiết. Code base được ông anh đưa cho với cấu trúc mà đến tận bây giờ mình còn không tin nổi là ông anh có thể xây dựng được cái code xịn như vậy (gần như support mọi thứ rồi - build web phút mốt), trong khi nó là framework mới ra lò, ít có người dùng nên code base trên mạng là không có.

Kết quả là mình hoàn thành xong đúng hạn, điều mà mình nghĩ không thể khi đây là framework hoàn toàn mới đối với mình, và cũng là lần đầu tiên mình làm web sử dụng thực tế, mặc dù bộ giải pháp cũng chỉ có vài chức năng thôi. Đến giờ FastAPI là framework chính của mình, dùng nó chinh chiến không biết bao nhiêu dự án, vì mình cảm giác mình là bố nó rồi.

Cách học này hiệu quả đến không ngờ, mình nhớ gần như toàn bộ code base, vì cấu trúc viết tốt quá, dễ học dễ thuộc.

**Điểm yếu của việc học thông qua code base, đó là anh em cần phải biết chút lập trình từ trước**. Một người mới về lập trình không thể học theo cách này được. Người mới hoàn toàn mình nghĩ nên học theo cách 1 sẽ hợp lý hơn, do chỉ đọc vào các phần dễ hiểu nhất và làm project demo không gây nhàm chán. Còn để đọc hiểu code base yêu cầu bạn phải biết những điều cơ bản về lập trình web. Vì vậy học theo code base thích hợp để áp dụng từ framework thứ 2.

**Điểm yếu số 2 là anh em phải biết được đâu là code base ngon**. Nếu code base không ngon, cấu trúc không linh hoạt thì học cũng như không, vì sẽ khiến anh em rối theo. Việc này được giải quyết bằng cách đi tìm những người pro về framework đó rồi ăn xin, hoặc lên github tìm code base + tên framework và tải về repo có lượt rate cao nhất là được.

**Điểm yếu số 3 là người dùng phải linh động với từng project sử dụng framework này**. Ví dụ code base là *[ASP.NET](http://asp.net/)* kết nối với *MySQL* nhưng trong dự án thực yêu cầu sử dụng *MongoDB* thì anh em cũng phải biết làm sao để sửa config cho server connect được tới db đó.

Bản thân mình thấy việc học theo cách này hiệu quả, vì 3 điểm yếu kia hiện tại mình không gặp phải. Kể cả học những thứ không thiên về dev như cách viết CICD cho project, k8s deployment, ... mình cũng sẽ dùng một template ngon rồi config lại phù hợp với project của mình, ít khi đọc docs ngay từ đầu.

Trên đây là trình bày về cách học code của mình, nhấn mạnh lại nó phù hợp với bản thân mình, anh em có thể tìm hiểu và áp dụng nếu thấy hợp lý.