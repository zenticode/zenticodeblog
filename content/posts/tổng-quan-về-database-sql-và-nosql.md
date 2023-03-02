---
title: Tổng quan về Database, SQL và NoSQL
date: 2023-03-02 21:44
tags:
  - Database
  - SQL
  - NoSQL
description: Cơ sở dữ liệu có ở khắp mọi nơi và được sử dụng để nâng cao cuộc
  sống hàng ngày của chúng ta. Từ lưu trữ đám mây cho đến thương mại điện tử,
  nhiều dịch vụ chúng ta sử dụng ngày nay đều có thể thực hiện được nhờ có cơ sở
  dữ liệu.
---


Từ lâu, con người đã dùng những phương pháp thô sơ như khắc lên đá, ghi chép sổ sách,.. cho đến băng đĩa cassette, đĩa mềm,.. để ghi chép lại dữ liệu. Cơ sở dữ liệu có ở khắp mọi nơi và được sử dụng để nâng cao cuộc sống hàng ngày của chúng ta. Từ lưu trữ đám mây cho đến thương mại điện tử, nhiều dịch vụ chúng ta sử dụng ngày nay đều có thể thực hiện được nhờ có cơ sở dữ liệu. Cùng tìm hiểu về các loại cơ sở dữ liệu phổ biến hiện nay và tính ứng dụng của chúng nhé.

# Phân loại cơ sở dữ liệu

[Cơ sở dữ liệu (Database)](https://en.wikipedia.org/wiki/Database) là một tập hợp dữ liệu có tổ chức được lưu trữ và truy cập điện tử.\
Các kỹ luật liên quan đến Database mà ta thường gặp bao gồm :

* [Mô hình hóa dữ liệu](https://vi.wikipedia.org/wiki/M%C3%B4_h%C3%ACnh_h%C3%B3a_d%E1%BB%AF_li%E1%BB%87u)
* [Lưu trữ dữ liệu hiệu quả](https://vi.wikipedia.org/wiki/L%C6%B0u_tr%E1%BB%AF_d%E1%BB%AF_li%E1%BB%87u)
* [Ngôn ngữ truy vấn](https://vi.wikipedia.org/wiki/Ng%C3%B4n_ng%E1%BB%AF_truy_v%E1%BA%A5n)
* [Bảo mật](https://en.wikipedia.org/wiki/Database_security)
* [Tính toán phân tán](https://vi.wikipedia.org/wiki/%C4%90i%E1%BB%87n_to%C3%A1n_ph%C3%A2n_t%C3%A1n) - bao gồm hỗ trợ truy cập đồng thời và khả năng chịu lỗi.

Các công nghệ cơ sở dữ liệu từ khi hình thành cho đến nay đã trải qua nhiều thế hệ với nhiều hình thái khác nhau nhằm mục đích cung cấp một cách phù hợp và hiệu quả để lưu trữ và truy cập dữ liệu liên tục thông qua việc phát triển các hệ thống quản lý.

![era](https://images.viblo.asia/138b7c36-4bf9-45f4-a26b-35377cacc18b.png)

*Sự phát triển liên tục của các công nghệ cơ sở dữ liệu chính và một số hệ thống cơ sở dữ liệu đại diện.*

Cơ sở dữ liệu quan hệ (relational-database) được sinh ra và sử dụng rộng rãi trong thập niên 1970, 1980. Hệ quản trị cơ sở dữ liệu quan hệ, hay RDBMS, đã trở thành một thuật ngữ được công nhận và dùng như một chuẩn và tới tận ngày hôm nay vẫn còn kế thừa.

Bên cạnh đó vào khoảng cuối của thế kỉ 20 xuất hiện một dạng cơ sở dữ liệu mang tên NoSQL (Non-Relation Database). Tuy nhiên phải đến năm 2009-2010, khi lượng dữ liệu trở lên quá lớn khiến SQL thông thường gặp khó khăn, ta mới thấy sự trở lại vô cùng mạnh mẽ của NoSQL cùng với hàng loạt công nghệ về xử lý dữ liệu lớn và tính toán phân tán.

Ngày nay, hai phân hệ hệ quản trị cơ sở dữ liệu phổ biến nhất được dùng vẫn là:

* [Relational Database](https://vi.wikipedia.org/wiki/C%C6%A1_s%E1%BB%9F_d%E1%BB%AF_li%E1%BB%87u_quan_h%E1%BB%87)
* [Non-Relation Database](https://en.wikipedia.org/wiki/NoSQL)

# Cơ sở dữ liệu quan hệ (SQL)

[Cơ sở dữ liệu quan hệ](https://vi.wikipedia.org/wiki/C%C6%A1_s%E1%BB%9F_d%E1%BB%AF_li%E1%BB%87u_quan_h%E1%BB%87), còn được gọi là cơ sở dữ liệu SQL, là hệ thống lưu trữ dữ liệu theo dạng bảng và hàng(còn được gọi là các bản ghi). Trong mỗi bảng lưu trữ thông tin về một đối tượng và giá trị các thuộc tính của chúng. Chẳng hạn dưới đây ta có ví dụ về lưu trữ thông tin khách hàng sản phẩm và lịch sử mua hàng.

![example](https://images.viblo.asia/d95b9d34-392f-462a-b984-7d5bc66a60f1.png)



*Ví dụ về dữ liệu trong Relational Database*

Một cơ sở dữ liệu quan hệ bao gồm các thành phần:

* **Bảng (Tables)**: Dữ liệu được cấu trúc dưới dạng các bảng chứa thông tin, một cơ sở dữ liệu thường gồm nhiều bảng tạo nên một lược đồ quan hệ (relational schema).
* **Bản ghi (Records/Rows)**: Các hàng của bảng trong cơ sở dữ liệu, tương ứng với một đối tượng và chứa thông tin về đối tượng cần lưu trữ đó
* **Trường thuộc tính (Columns/Fields)**: Đặc điểm của đối tượng được lưu trữ trong csdl, ví dụ đối với thông tin khách hàng, ta cần các trường thuộc tính như tên, địa chỉ,...
* **Khóa (Keys)**: Khóa là một trường (field) đặc biệt, chúng tạo ra mối quan hệ giữa các bảng với nhau

  * *Khóa chính (Primary key)*: Trong mỗi bảng có một trường khóa chính và có giá trị duy nhất cho mỗi bản ghi, mang ý nghĩa định danh cho bản ghi đó.
  * *Khóa ngoại (Foreign keys)*: là một trường trong một bảng trỏ đến trường khóa chính của bảng khác, có tác dụng liên kết các bảng.
* **Quan hệ (Relationals)**: Mô tả cách các bảng liên kết qua khóa và chia sẻ thông tin.

  * *One-to-one*: từng bản ghi trong bảng này đều tương ứng chính xác với bản ghi trong bảng kia. Vd: một người chỉ có 1 căn cước công dân duy nhất.
  * *One-to-many*: mỗi bản ghi trong bảng có thể liên kết với nhiều bản ghi trong bảng khác. Vd: Một người có thể có nhiều địa chỉ nhà
  * *Many-to-many*: tương tự như one-to-many nhưng là hai chiều. Vd: một người có thể có nhiều địa chỉ và ngược lại trong một địa chỉ có thể có nhiều người sinh sống.
* **Lược đồ csdl (Database Schema)**: bản thiết kế cho cơ sở dữ liệu, mô tả cách ta sẽ lưu trữ thông tin và thông tin đó sẽ liên quan đến nhau như thế nào. Bao gồm quy tắc cho các trường, mối quan hệ các bảng, ...
* **Chỉ mục (Indexes)**: lập chỉ mục cho một hoặc nhiều trường giúp tìm kiếm trong csdl trở nên dễ dàng và nhanh hơn.

Ngoài ra, cơ sở dữ liệu quan hệ nổi tiếng với khả năng xử lý giao dịch, đảm bảo 4 thuộc tính [ACID](https://en.wikipedia.org/wiki/ACID) (atomicity, consistency, isolation, và durability) dưới đây.

| Attribute   | Function                    | Description                                                                 |
| ----------- | --------------------------- | --------------------------------------------------------------------------- |
| Atomicity   | Transaction Manager         | Giao dịch gồm nhiều thao tác chỉ thành công khi toàn bộ thao tác thành công |
| Consistency | Application programmer      | Dữ liệu cần trở lại trạng thái trước khi giao dịch nếu gặp lỗi (rollback)   |
| Isolation   | Concurrency Control Manager | Thực thi các giao dịch độc lập với nhau một cách đồng thời                  |
| Durability  | Recovery Manager            | Đảm bảo dữ liệu giao dịch được lưu trữ trong cả trường hợp lỗi hệ thống     |

Các cơ sở dữ liệu quan hệ phổ biến nhất hiện nay là [Microsoft SQL Server](https://www.microsoft.com/en-us/sql-server), [Oracle Database](https://www.oracle.com/database/), [MySQL](https://www.mysql.com/) và [IBM DB2](https://www.ibm.com/products/db2). Một số phiên bản miễn phí của các nền tảng RDBMS này đã trở nên phổ biến trong những năm qua, chẳng hạn như `SQL Server Express, PostgreSQL, SQLite, MySQL và MariaDB.`

**Ưu điểm:**

* Hoạt động với dữ liệu có cấu trúc, được định hướng bảng và hàng nên rất trực quan
* Các mối quan hệ trong hệ thống có những ràng buộc, điều này thúc đẩy mức độ toàn vẹn dữ liệu cao.
* Cung cấp khả năng viết các truy vấn SQL (ngôn ngữ truy vấn có cấu trúc) phức tạp để thao tác dữ liệu, phân tích và báo cáo dữ liệu một cách mạnh mẽ

**Nhược điểm:**

* Một nhược điểm lớn ta dễ dàng có thể thấy đó là khó sửa đổi, mở rộng do số lượng kết nối ngày một tăng cao.
* Cần phải định nghĩa trước về cấu trúc dữ liệu trước khi thêm dữ liệu vào.

# Cơ sở dữ liệu phi quan hệ (NoSQL)

Trên thực tế, các hệ thống phần chúng ta xây dựng không nhất thiết yêu cầu dữ liệu có quan hệ. Không phải mọi phần mềm đều yêu cầu tính nhất quán, chính xác trong các giao dịch hay truy vấn phức tạp. Điển hình là [Facebook Messenger](https://www.messenger.com/), nơi chúng ta hy vọng có thể nhắn tin 24/24 với nhiều người truy cập hơn là các giao dịch chính xác. Facebook cũng hiểu được điều đó nên đã xây dựng Cassandra, một trong những opensource NoSQL-Database nổi tiếng sau này được Apache cấp phép.

![CV](https://images.viblo.asia/b80b54e5-f5fc-45b4-bd68-c5e2b7aeb487.png)

*nosql funny meme*

Nhiều cơ sở dữ liệu NoSQL hy sinh tính nhất quán (đề cập trong [định lý CAP](https://vi.wikipedia.org/wiki/CAP_theorem)) để ưu tiên cho tính sẵn sàng, dung lượng của phân vùng, và tốc độ truy cập.

Có 4 loại Nosql-Database phổ biến:![nosql-type](https://images.viblo.asia/39b568ad-842e-4df4-b624-35ed98f622aa.jpg)



*NoSQL data models*

## 1. Column:

Cũng như tên gọi của nó, dữ liệu trong database được lưu dưới dạng các cột thay vì các hàng.\
Lấy cảm hứng từ [Google Bigtable](https://en.wikipedia.org/wiki/Bigtable), dữ liệu được tổ chức dưới dạng các cột, phân tách theo giá trị của một hoặc nhiều thuộc tính nào đó. Mỗi column thường chỉ có các trường `Name, Value, TimeStamp`![column](https://images.viblo.asia/1ec41bc3-3029-4750-96c7-82f8dd6d9099.png)

*Row-store and Column-store*

[Column-DBMS](https://en.wikipedia.org/wiki/Column-oriented_DBMS) sử dụng không gian khóa giống như lược đồ cơ sở dữ liệu trong RDBMS do đó có thể được coi là bán quan hệ (semi-realtional database). Mỗi khóa được sử dụng để lưu trữ metadata cho các column-family. Column-family có thể được coi giống như một bảng trong RDBMS, bao gồm họ các column liên quan tới nhau. Ví dụ dưới đây cho thấy sự tương đương giữa bẳng AuthorProfile và column-family của nó.![example](https://images.viblo.asia/0b63ba1a-b432-4709-a5e2-6054c19ae520.png)

*Row-store and Column-store Example*

\
Như ta thấy dữ liệu được tách thành các cột và được nhóm thành các column-family kèm theo khóa (trong hình là dựa trên tên author). Rõ ràng ta thấy nếu như lưu trữ như SQL thông thường sẽ có rất nhiều giá trị `null`, dẫn đến tốn không gian lưu trữ. Ngoài ra, khi truy vấn sẽ tách thành các truy vấn trên cột, đem lại hiệu suất nhanh hơn trong các chức năng query, tìm kiếm và tổng hợp.

Cơ sở dữ liệu dạng cột được dùng trong trường lưu trữ dữ liệu lớn, thao tác đọc nhiều hơn là ghi dữ liệu.

Các cơ sở dữ liệu nổi tiếng dựa trên Column: [Cassandra](https://cassandra.apache.org/_/index.html), [HBase](https://hbase.apache.org/), [Vertica](https://www.vertica.com/)

## 2. Key-value:

Dữ liệu đơn giản được lưu trữ dưới dạng `(key,value)`, giá dữ liệu có thể không cùng loại với nhau. Về tốc độc truy vấn vô cùng nhanh và có khả năng mở rộng cao.

![key-val](https://images.viblo.asia/9b1e1479-fcd2-452c-9dd0-818cc165e881.png)

*Key-Value sample*

\
Về cơ bản key-value được coi là các bảng chỉ có 2 cột và không có tính năng joins như các bảng trong SQL. Các cơ sở dữ liệu dạng này thường đơn giản, kích thước nhỏ, lưu phân tán tại nhiều nơi và lưu ở trong RAM nhằm tăng tốc độ xử lý.

Các cơ sở dữ liệu key-value điển hình: [CouchDB](https://couchdb.apache.org/), [Dynamo](https://aws.amazon.com/vi/dynamodb/), [Redis](https://redis.io/), [Riak](https://riak.com/), [Berkeley DB](https://www.oracle.com/database/technologies/related/berkeleydb.html)

## 3. Document:

Là một phần mở rộng của `Key-Value`, nơi các giá trị được lưu trữ trong các document có cấu trúc như XML hoặc JSON. Document giúp bạn dễ dàng ánh xạ các đối tượng trong hướng đối tượng sang database.

Cơ sở dữ liệu document không có lược đồ cố định, bạn không cần phải xác định trước lược đồ và tuân thủ nó. Nó cho phép ta lưu trữ dữ liệu phức tạp ở các định dạng document (JSON, XML, v.v.) một cách rất linh hoạt.![doc](https://images.viblo.asia/ac119d4b-f016-4109-969b-152776a18762.png)

*Document Database Example*

\
Cơ sở dữ liệu document không hỗ trợ quan hệ. Mỗi document trong kho lưu trữ là độc lập và không có tính toàn vẹn quan hệ. Điều này giúp ta giảm rất nhiều bảng liên kết cũng như nested-joins như ở SQL. Chúng ta hoàn toàn có thể truy cập thuộc tính lồng nhau nhiều mức thay vì phải joins các bảng một cách phức tạp.

Một số Document Database thường thấy hiện nay: [Apache CouchDB](https://couchdb.apache.org/), [DocumentDB](https://aws.amazon.com/vi/documentdb/), [MongoDB](https://www.mongodb.com/), [OrientDB](https://orientdb.org/), [Elasticsearch](https://www.elastic.co/)

## 4. Graph:

Các mô hình dữ liệu phi quan hệ kể trên lưu trữ thông tin về các thực thể như các giá trị key-value, hàng trong các bảng nhiều cột hoặc tài liệu. Tuy nhiên, số lượng ngày càng tăng của các bộ dữ liệu có liên kết định hướng đồ thị, chẳng hạn như [Semantic Web](https://en.wikipedia.org/wiki/Semantic_Web), [Web Mining](https://static.hlt.bme.hu/semantics/external/pages/inform%C3%A1ci%C3%B3-visszakeres%C3%A9s/en.wikipedia.org/wiki/Web_mining.html) đã tạo ra nhu cầu về các mối quan hệ thực thể một cách hiệu quả. Điều này đã thúc đẩy sự xuất hiện của các cơ sở dữ liệu đồ thị để lưu trữ các bộ dữ liệu này một cách hiệu quả và cung cấp các hoạt động hiệu quả cho truy vấn và phân tích.

![graph](https://images.viblo.asia/ae5a7ede-0be9-42b6-86b1-8a250c71b1d9.png)



*Một ví dụ về dữ liệu đồ thị trên mạng xã hội Facebook*

Các csdl này dựa trên nền tảng lý thuyết đồ thị mạnh mẽ, trong đó biểu đồ bao gồm các đỉnh đại diện cho các thực thể và các cạnh đại diện cho mối quan hệ giữa chúng. Có nhiều cách để xây dựng graph-database như dựa trên đồ thị vô hướng, đồ thị gắn nhãn hay đồ thị thuộc tính,... dưới đây là một ví dụ trong biểu diễn Web sematic bằng chuẩn [RDF](https://www.w3.org/RDF/). Các mối quan hệ được thể hệ qua các bộ ba `(Subject, Predicate, Object)` và được mapping bởi ngôn ngữ RML mỗi khi truy vấn qua URI.![example](https://images.viblo.asia/2f4131dc-9e85-4d46-b94c-2538fb80f645.png)

*Metadata Description in Graph Database*

\
Các cơ sở dữ liệu đồ thị phổ biến: [AllegroGraph](https://allegrograph.com/), [Neo4J](https://neo4j.com/), [OrientDB](https://orientdb.org/), [Virtuoso](https://virtuoso.openlinksw.com/), [Stardog](https://www.stardog.com/).

## Ưu điểm:

* Available: Dữ liệu thường được phân tán trên một số máy chủ và khu vực, do đó ổn định và linh hoạt hơn.
* Performance: NoSQL đem lại hiệu suất truy vấn tuyệt vời trên cả thông lượng và độ trễ.
* Scalability: Các csdl phi quan hệ có khả năng mở rộng một cách linh hoạt và được scale theo chiều ngang thay vì theo chiều dọc, điều này mang lại lợi thế rõ ràng so với cơ sở dữ liệu SQL.
* Flexible: Kiểu dữ liệu không được cấu trúc và định nghĩa trước giúp ta linh hoạt trong quá trình phát triển hệ thống.
* Data models: các mô hình dữ liệu đa dạng, có xu hướng cực kỳ chuyên biệt trong các trường hợp sử dụng cụ thể, cho phép chúng hoạt động tốt hơn cơ sở dữ liệu quan hệ.

## Nhược điểm:

* Chưa hỗ trợ tốt các giao dịch trên nhiều tài liệu. Điển hình như tính nhất quán (Consistency - “C” in ACID) sẽ cần được trade-off với tính Available và Performance như đã đề cập trong [định lý CAP](https://vi.wikipedia.org/wiki/CAP_theorem).
* Không hiệu quả đối với những truy vấn phức tạp cần sử dụng nhiều liên kết.
* Chưa hoàn thiện: Các mô hình quan hệ đã xuất hiện được một thời gian so với các mô hình NoSQL và kết quả là chúng đã phát triển thành các hệ thống ổn định và có nhiều chức năng hơn trong những năm qua.

# SQL vs NoSQL

| SQL                                 | NoSQL                                                          |
| ----------------------------------- | -------------------------------------------------------------- |
| Dữ liệu vài Gigabytes tới Terabytes | Dữ liệu từ Petabytes(1kTB) tới Exabytes(1kPB), Zetabytes(1kEB) |
| Tập trung                           | Phân tán                                                       |
| Có cấu trúc                         | Bán cấu trúc hoặc không có cấu trúc                            |
| Structured Query Language           | No declarative query language                                  |
| Complex Relationships               | Less complex relationships                                     |
| ACID Property                       | Eventual Consistency                                           |
| Ưu tiên transaction                 | Ưu tiên tính khả dụng, mở rộng                                 |
| Joins Tables                        | Embedded structures                                            |

# Tổng kết

Cũng giống như sự khởi đầu của lịch sử cơ sở dữ liệu và quản lý cơ sở dữ liệu, tương lai sẽ gắn liền với sự phát triển tổng thể trong việc xử lý và tính toán trên dữ liệu. Học máy và trí tuệ nhân tạo sẽ tiếp tục cải thiện và trở thành một phần không thể thiếu trong cơ sở dữ liệu và quản trị cơ sở dữ liệu. Các công cụ quản lý cơ sở dữ liệu ngày càng nhanh hơn và hiệu quả hơn sẽ được xây dựng và phát triển kế thừa trên các chuẩn cũ. Cuối cùng, tương lai có vẻ vô cùng tươi sáng cho ngành cơ sở dữ liệu. ⭐

Mong rằng qua bài viết này có thể giúp các bạn dễ hình dung hơn về các hệ quản trị cơ sở dữ liệu và tính ứng dụng của chúng. Trong các phần tiếp theo mình sẽ tiếp tục nói về các thành phần và kỹ thuật trong Database nếu các bạn quan tâm hãy đón đọc nhé. 💖

**Reference:**

* <https://en.wikipedia.org/wiki/Database>
* <https://blog.airtable.com/what-is-a-relational-database/>
* [Davoudian, A., Chen, L., & Liu, M. (2018). A survey on NoSQL stores. ACM Computing Surveys (CSUR), 51(2), 1-43.](https://www.researchgate.net/publication/324640550_A_survey_on_NoSQL_stores)
* <https://www.quickbase.com/articles/timeline-of-database-history>
* <https://database.guide/what-is-a-column-store-database/>