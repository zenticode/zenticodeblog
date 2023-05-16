---
title: MONGODB LÀ GÌ? CÁC TÍNH NĂNG NỔI BẬT CỦA MONGODB
date: 2023-05-16 20:37
tags:
  - MongDB
description: MongoDB là một trong những cơ sở dữ liệu phi quan hệ (NoSQL) phổ
  biến nhất hiện nay, được sử dụng rộng rãi trong nhiều lĩnh vực. MongoDB cung
  cấp các tính năng hữu ích giúp cho việc phân tích, truy vấn và cập nhật dữ
  liệu trở nên dễ dàng và nhanh chóng. Vậy MongoDB là gì?
---
**MongoDB** là một trong những cơ sở dữ liệu phi quan hệ (NoSQL) phổ biến nhất hiện nay, được sử dụng rộng rãi trong nhiều lĩnh vực. MongoDB cung cấp các tính năng hữu ích giúp cho việc phân tích, truy vấn và cập nhật dữ liệu trở nên dễ dàng và nhanh chóng. Vậy MongoDB là gì?

## MongoDB là gì?

**MongoDB** là một hệ thống cơ sở dữ liệu phi quan hệ (NoSQL), mã nguồn mở, được phát hành lần đầu vào **tháng 2 năm 2009** bởi **MongoDB Inc** và quản lý theo **SSPL (Server Side Public License).**

MongoDB lưu trữ dữ liệu dưới dạng tài liệu (document) JSON, cho phép các ứng dụng lưu trữ và truy vấn dữ liệu một cách linh hoạt và hiệu quả.

MongoDB có nhiều ưu điểm như khả năng lưu trữ dữ liệu phân tán, linh hoạt trong cấu trúc dữ liệu, có thể mở rộng, tốc độ truy vấn nhanh và hỗ trợ các tính năng như indexing, replication, sharding và map-reduce.

MongoDB hỗ trợ tất cả các ngôn ngữ phổ biến như **C, C++, C# và .Net, Go,** [Java](https://200lab.io/blog/typescript-la-gi/), **Node.js, Perl**, [PHP](https://200lab.io/blog/html-la-gi/), [Python](https://200lab.io/blog/python-la-gi/), **Motor, Ruby**, [Scala](https://200lab.io/blog/scala-la-gi/), **Swift, Mongoid**. Vì vậy, bạn có thể tạo một ứng dụng bằng bất kỳ ngôn ngữ nào trong số này.

Hiện nay có rất nhiều công ty đang sử dụng MongoDB như Facebook, Nokia, eBay, Adobe, Google,... để lưu trữ lượng lớn dữ liệu của họ.

## MongoDB hoạt động như thế nào?

MongoDB hoạt động dưới dạng một hệ thống cơ sở dữ liệu phi quan hệ, lưu trữ dữ liệu dưới dạng tài liệu (document) JSON. Dữ liệu được lưu trữ trong collections và documents. Do đó, database, collection và documents sẽ có liên quan với nhau như hình dưới đây:![](https://images.viblo.asia/541a57ae-93b0-42f7-8022-8007c94e4bbe.jpeg)

* Cơ sở dữ liệu MongoDB lưu trữ tài liệu trong các collections, tương tự như bảng trong cơ sở dữ liệu quan hệ. Mỗi collection có thể chứa nhiều tài liệu (documents) có cấu trúc dữ liệu tùy ý.
* Bây giờ bên trong collection sẽ có tài liệu (documents). Các tài liệu này sẽ chứa dữ liệu mà bạn muốn lưu trữ trong MongoDB database. Mỗi document có thể chứa nhiều fields dữ liệu, mỗi field được định danh bằng tên và có giá trị tương ứng.
* Các tài liệu (documents) được tạo bằng cách sử dụng các field. Các field là các key-value pair trong tài liệu, nó giống như các cột trong cơ sở dữ liệu quan hệ. Giá trị của fields có thể thuộc bất kỳ loại dữ liệu BSON nào như double, string, boolean,...
* MongoDB hỗ trợ việc tạo index cho các field dữ liệu trong collection, giúp tăng tốc độ truy vấn. Chúng còn hỗ trợ sao chép dữ liệu giữa các node trong một cluster giúp đảm bảo tính khả dụng và độ tin cậy của hệ thống.
* MongoDB phân tán dữ liệu trên nhiều node, giúp tăng khả năng mở rộng của hệ thống, đồng thời chúng còn hỗ trợ tính toán phân tán bằng cách sử dụng MapReduce giúp xử lý dữ liệu lớn một cách hiệu quả. Khi sử dụng MongoDB, bạn có thể sử dụng API và driver của MongoDB để truy cập và thao tác với dữ liệu trong hệ thống cơ sở dữ liệu này.

## Các tính năng của MongoDB

### Schema-less Database

Trong MongoDB, bạn được phép lưu trữ dữ liệu dưới dạng tài liệu (document) mà không cần yêu cầu sự định nghĩa trước về cấu trúc của chúng, giống như trong hệ thống quản lý cơ sở dữ liệu phi quan hệ (NoSQL).

Bạn có thể lưu trữ các tài liệu với các fields và giá trị (values) khác nhau mà không cần tuân theo một cấu trúc cố định. Do đó, việc thêm, xóa hoặc sửa đổi các fields, giá trị của tài liệu được thực hiện một cách dễ dàng mà không cần phải thực hiện các bước định nghĩa cấu trúc cơ sở dữ liệu trước.

Tính năng schema-less giúp tăng tính linh hoạt và giảm thời gian phát triển các ứng dụng, đặc biệt là đối với các ứng dụng có tính chất thay đổi dữ liệu thường xuyên hoặc không có một cấu trúc dữ liệu cố định.

Tuy nhiên, tính năng này sẽ dẫn đến khó khăn trong việc truy vấn và xử lý dữ liệu nếu không có sự quản lý và thiết kế cẩn thận.

### Document Oriented

MongoDB được thiết kế để lưu trữ dữ liệu dưới dạng tài liệu (document) thay vì các bảng (table) như trong hệ quản trị cơ sở dữ liệu quan hệ (RDBMS). Mỗi tài liệu trong MongoDB được lưu trữ dưới một bản ghi độc lập bao gồm các fields (key-value pair) và giá trị tương ứng.

### Indexing

MongoDB tạo ra index để tăng tốc độ truy vấn và tìm kiếm dữ liệu trong cơ sở dữ liệu. Khi tạo một index trên một field hoặc tập hợp fields, MongoDB sẽ tạo ra một cấu trúc dữ liệu tương ứng, sắp xếp và lưu trữ các giá trị của fields hoặc tập hợp các fields đó theo một thứ tự nhất định.

Khi truy vấn dữ liệu, MongoDB sử dụng các Index để nhanh chóng tìm kiếm và trả về các tài liệu phù hợp với tiêu chí truy vấn. Việc sử dụng Index giúp giảm thời gian truy vấn tìm kiếm dữ liệu, đồng thời giúp tăng hiệu suất và khả năng mở rộng của MongoDB.

Có nhiều loại Index khác nhau trong MongoDB, gồm:

* Single Field Index: Index trên một Field duy nhất.
* Compound Index: cho phép đánh dấu Index cho nhiều Field.
* Multikey Index: Index trên các mảng dữ liệu.
* Text Index: Index dành riêng cho các tài liệu chứa văn bản. Việc thiết lập các Index phù hợp và tối ưu là một yếu tố quan trọng trong việc thiết kế và tối ưu hóa cơ sở dữ liệu MongoDB.

### Replication

Replication trong MongoDB là quá trình đồng bộ dữ liệu giữa các node trong một cluster MongoDB. Một cluster MongoDB sẽ gồm một node primary và nhiều node secondary.

Node primary là node chịu trách nhiệm ghi dữ liệu mới vào cơ sở dữ liệu, còn các node secondary chỉ đọc dữ liệu. Khi một node primary bị lỗi hoặc ngừng hoạt động thì một node secondary sẽ được chuyển đổi thành node primary để tiếp tục đảm nhận việc ghi dữ liệu.

Khi một node primary ghi dữ liệu mới vào cơ sở dữ liệu, nó sẽ đồng bộ dữ liệu mới này với các node secondary bằng cách sử dụng thủ tục replica set. Replica set là một tập hợp các node trong cluster gồm có một node primary và các node secondary, cùng với quy tắc đảm bảo sự sẵn sàng, độ tin cậy và khả năng phục hồi.

Với tính năng Replication, MongoDB có khả năng tự động sao lưu dữ liệu, đảm bảo độ tin cậy và khả năng phục hồi của cơ sở dữ liệu, đồng thời giúp tăng khả năng mở rộng của hệ thống.

### Sao lưu và phục hồi

MongoDB cung cấp tính năng sao lưu và phục hồi dữ liệu linh hoạt, cho phép lưu trữ các bản sao của dữ liệu và phục hồi dữ liệu trong trường hợp xảy ra sự cố.

### Bảo mật

MongoDB hỗ trợ nhiều tính năng bảo mật, bao gồm chứng thực người dùng (user authentication), mã hóa dữ liệu (data encryption) và kiểm soát quyền truy cập (access control).

## Ưu điểm của MongoDB

* Tính linh hoạt: MongoDB là một hệ thống cơ sở dữ liệu phi quan hệ, nó cung cấp khả năng lưu trữ dữ liệu bất cứ khi nào, bất cứ nơi đâu, không cần phải tuân thủ một mô hình quan hệ cụ thể.
* Khả năng mở rộng: MongoDB có khả năng mở rộng dễ dàng, nhờ tính năng sharding cho phép phân chia dữ liệu thành nhiều phần và lưu trữ trên nhiều máy chủ.
* Tốc độ truy xuất nhanh: MongoDB có thể đáp ứng các yêu cầu truy vấn dữ liệu trong thời gian ngắn hơn so với các hệ thống cơ sở dữ liệu quan hệ truyền thống.
* Tính khả dụng cao: MongoDB cung cấp tính năng sao lưu và phục hồi dữ liệu, giúp người dùng bảo vệ dữ liệu của mình khỏi những rủi ro.
* Dễ sử dụng: MongoDB cung cấp các công cụ quản lý dữ liệu trực quan và dễ sử dụng, giúp người dùng tối ưu hóa hiệu suất và quản lý cơ sở dữ liệu một cách dễ dàng.
* Dễ dàng tích hợp với Big Data Hadoop

## Nhược điểm của MongoDB

* Cần sử dụng bộ nhớ cao để lưu trữ dữ liệu (data storage).
* Không được phép lưu trữ hơn 16MB data trong tài liệu.
* Data nesting trong BSON cũng bị hạn chế, bạn không được phép nest data quá 100 cấp độ.

## Lời kết

Với tính năng linh hoạt, mở rộng và khả năng xử lý dữ liệu phân tán, **MongoDB** đã trở thành một trong những cơ sở dữ liệu phi quan hệ (NoSQL) phổ biến nhất hiện nay.

MongoDB không chỉ đơn thuần là một cơ sở dữ liệu, mà còn là một hệ sinh thái hoàn chỉnh với nhiều tính năng và công cụ hỗ trợ. Các tính năng và ưu điểm của MongoDB làm cho việc lưu trữ và xử lý dữ liệu trở nên dễ dàng và hiệu quả hơn, đáp ứng nhu cầu trong nhiều lĩnh vực, đặc biệt là trong Data analyst.

Data analyst có thể sử dụng MongoDB để lưu trữ, xử lý và truy vấn các loại dữ liệu khác nhau. Ngoài ra, MongoDB cũng cung cấp các công cụ để truy vấn dữ liệu, tạo báo cáo và thực hiện các phân tích dữ liệu phức tạp cho data analyst. Vì vậy, có thể nói rằng MongoDB là một công cụ hữu ích cho data analyst trong việc lưu trữ và phân tích dữ liệu.