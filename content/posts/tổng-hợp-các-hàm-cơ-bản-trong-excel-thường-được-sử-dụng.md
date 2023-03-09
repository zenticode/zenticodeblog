---
title: Tổng hợp các hàm cơ bản trong Excel thường được sử dụng
date: 2023-03-09 11:52
tags:
  - Excel
  - ""
description: Các hàm cơ bản trong Excel giúp bạn thực hiện các phép tính, xử lý
  số liệu trong quá trình học tập và làm việc. Cùng bài viết điểm qua các hàm
  Excel cơ bản nhất, cùng tìm hiểu nhé!
---
# Hàm tính toán Logic

#### **1. Hàm SUM**

Hàm SUM dùng để tính tổng tất cả các số trong dãy ô. Nghĩa là SUM có nhiệm vụ tính tổng giá trị các số hoặc dãy số trong ô mà bạn muốn tính.

Cú pháp:

**\=SUM(Number1,Number2,Number3)**

Với:

**Number1,Number2,Number3**: là giá trị các số hạng cần tính tổng

Kết quả của hàm SUM là tổng các giá trị được chọn.

Ví dụ: **\=SUM(20,40,60)** nghĩa là cộng các số hạng lại với nhau và cho ra kết quả 120.

![tổng các giá trị](https://cdn.tgdd.vn/Files/2021/06/24/1363094/tong-hop-cac-ham-trong-excel.jpg "tổng các giá trị")

Ví dụ: Tính tổng các dãy số từ A1 đến A3, **\=SUM(A1:A3)** cho ra kết quả làm 120.

![tổng các giá trị trong dãy](https://cdn.tgdd.vn/Files/2021/06/24/1363094/tong-hop-cac-ham-trong-excel-1.jpg "tổng các giá trị trong dãy")

**Xem thêm**: [Cách dùng hàm SUM trong Excel để tính tổng](https://www.dienmayxanh.com/kinh-nghiem-hay/cach-dung-ham-sum-de-tinh-tong-trong-excel-1346822 "Cách dùng hàm SUM trong Excel để tính tổng")

#### **2. Hàm MIN/MAX**

Hàm MIN/MAX dùng để tìm giá trị nhỏ nhất/lớn nhất trong một vùng dữ liệu hoặc trong cả bảng tính.

Cú pháp:

**\=MIN(Number1,Number2,...)**

Với:

**Number1,Number2**: Các giá trị cần so sánh

Kết quả trả về giá trị nhỏ nhất trong vùng dữ liệu

Ví dụ: Giá trị nhỏ nhất trong vùng dữ liệu của ví dụ này, ta có công thức **\=MIN(A2:C5)** và nhận được kết quả **25** là giá trị nhỏ nhất cần tìm.

![Tìm giá trị nhỏ nhất trong bảng dữ liệu](https://cdn.tgdd.vn/Files/2021/06/24/1363094/tong-hop-cac-ham-trong-excel-8.png "Tìm giá trị nhỏ nhất trong bảng dữ liệu")

Cú pháp:

**\=MAX(Number1,Number2,...)**

Với:

**Number1,Number2**: các giá trị cần so sánh

Kết quả trả về giá trị lớn nhất trong vùng dữ liệu

Ví dụ: Tìm giá trị lớn nhất trong vùng dữ liệu của ví dụ này, ta có công thức **\=MAX(A2:C5)** kết quả đạt được là **89** là giá trị lớn nhất cần tìm.

![Tìm giá trị lớn nhất trong vùng dữ liệu](https://cdn.tgdd.vn/Files/2021/06/24/1363094/tong-hop-cac-ham-trong-excel-10.png "Tìm giá trị lớn nhất trong vùng dữ liệu")

#### **3. Hàm COUNT/COUNTA**

Hàm COUNT dùng để đếm số lượng ô có chứa số trong vùng dữ liệu.

Cú pháp:

**\=COUNT(Value1,...)**

Với:

**Value1,...**: Tham chiếu ô hoặc phạm vi muốn đếm số

Ví dụ: Tìm số lượng mà giá trị trong ô của vùng dữ liệu là số, ta có công thức cho ví dụ này là **\=COUNT(A2:C5)**. Kết quả đạt được là tổng số lượng ô có chứa số.

![Đếm giá trị là số trong vùng dữ liệu](https://cdn.tgdd.vn/Files/2021/06/24/1363094/tong-hop-cac-ham-trong-excel-11.png "Đếm giá trị là số trong vùng dữ liệu")

\- [Hàm COUNTA](https://www.dienmayxanh.com/kinh-nghiem-hay/cach-su-dung-ham-dem-count-countif-counta-excel-1352900#hmenuid5 "Hàm COUNTA") dùng để đếm các ô không trống trong một vùng dữ liệu nhất định.

Cú pháp:

**\=COUNTA(Value1,...)**

Với:

**Value1,...:** Là những ô cần đếm hoặc một vùng cần đếm. Số ô tối đa có thể đếm là 255 (với Excel từ 2007 về sau) và tối đa 30 (với Excel từ 2003 về trước)

Ví dụ: Đếm số lượng ký tự là số trong bảng bên dưới, ta có công thức **\=COUNTA(A2:C5)**. Kết quả đạt được là số lượng ô có chứa kí tự hoặc số.

![Đếm số lượng ô không trống trong một vùng dữ liệu](https://cdn.tgdd.vn/Files/2021/06/24/1363094/tong-hop-cac-ham-trong-excel-12.png "Đếm số lượng ô không trống trong một vùng dữ liệu")

**4. Hàm ODD/EVEN**

\- Hàm ODD là hàm trả về số được làm tròn lên số nguyên lẻ gần nhất.

Cú pháp:

**\=ODD(Number)**

Với

**Number:** Bắt buộc phải có, là giá trị cần làm tròn

Ví dụ: Làm tròn số **4.6** đến số nguyên lẻ gần nhất nhận được kết quả là **5**.

![Trả về số nguyên lẻ gần nhất](https://cdn.tgdd.vn/Files/2021/06/24/1363094/tong-hop-cac-ham-trong-excel-13.png "Trả về số nguyên lẻ gần nhất")

\- Hàm EVEN là hàm trả về số được làm tròn lên số nguyên chẵn gần nhất.

Cú pháp:

**\=EVEN(Number**)

Với:

**Number**: Bắt buộc phải có, là giá trị cần làm tròn

Ví dụ: Làm tròn **53.4** đến số nguyên chẵn gần nhất nhận được kết quả là **54**.

![Làm tròn lên số nguyên chẵn gần nhất](https://cdn.tgdd.vn/Files/2021/06/24/1363094/tong-hop-cac-ham-trong-excel-14.png "Làm tròn lên số nguyên chẵn gần nhất")

#### **5. Hàm AVERAGE**

[Hàm AVERAGE](https://www.dienmayxanh.com/kinh-nghiem-hay/cach-dung-ham-average-de-tinh-trung-binh-cong-1361833 "Hàm AVERAGE") dùng để tính trung bình cộng của một dãy số trong trang tính.

Cú pháp:

**\=AVERAGE(number1,number2,…)**

Với:

**number1 (Bắt buộc):** Số thứ nhất, tham chiếu ô, hoặc phạm vi mà bạn muốn tính trung bình.

**number2,... (Tùy chọn)**: Các số, tham chiếu ô hoặc phạm vi bổ sung mà bạn muốn tính trung bình, tối đa là 255.

Ví dụ: Tính lương trung bình theo thông tin bên dưới, ta có công thức **\=AVERAGE(C3:C8)** và nhận được kết quả là giá trị trung bình của 6 tháng lương.

![Giá trị trung bình của vùng dữ liệu](https://cdn.tgdd.vn/Files/2021/06/24/1363094/tong-hop-cac-ham-trong-excel-15.png "Giá trị trung bình của vùng dữ liệu")

# Hàm điều kiện Logic

#### **1. Hàm COUNTIF**

Hàm COUNTIF được dùng để đếm ô thỏa mãn điều kiện trong một vùng dữ liệu được chọn.

Cú pháp:

**\=COUNTIF(range,criteria)**

Với:

**range**: Vùng dữ liệu cần đếm.

**criteria**: Điều kiện để đếm.

Ví dụ: Có bảng thống kê các mặt hàng và số lượng tồn như hình dưới.

Để thống kê xem có bao nhiêu mặt hàng còn tồn trên 150 sản phẩm, nhập công thức:

**\=COUNTIF(C2:C11,">150")**

Kết quả trả về cho thấy có tổng cộng **8 mặt hàng** còn tồn **trên 150 sản phẩm**.

![Ví dụ hàm COUNTIF](https://cdn.tgdd.vn/Files/2021/06/24/1363094/tong-hop-cac-ham-trong-excel-2.jpg "Ví dụ hàm COUNTIF")

**Xem thêm**: [Đếm theo điều kiện với COUNTIF/COUNTIFS](https://www.dienmayxanh.com/kinh-nghiem-hay/cach-su-dung-ham-dem-count-countif-counta-excel-1352900#hmenuid2 "Đếm theo điều kiện với COUNTIF/COUNTIFS")

#### **2. Hàm IF**

Hàm IF được dùng để kiểm tra dữ liệu có thỏa điều kiện người dùng đặt ra và trả về kết quả theo biểu thức logic đúng hoặc sai.

Cú pháp:

**\=IF(Logical_test;Value_if_true;Value_if_false)**

Với:

**Logical_test**: Điều kiện.

**Value_if_true**: Giá trị trả về nếu thỏa điều kiện

**Value_if_false**: Giá trị trả về nếu không thỏa điều kiện.

Lưu ý: Nếu bỏ trống **Value_if_true** và **Value_if_false**, nếu điều kiện thỏa thì giá trị trả về sẽ là 0 và điều kiện không thỏa thì giá trị trả về sẽ là FALSE.

Ví dụ: Xét học sinh có qua môn với điều kiện:

\- Điểm số từ 7 trở lên: Đạt

\- Điểm số thấp hơn 7: Không Đạt

Tại ô D2, ta có công thức: **\=IF(C2>=7,"Đạt","Không Đạt")**, và được kết quả như hình bên dưới.

![Sử dụng hàm IF](https://cdn.tgdd.vn/Files/2021/06/24/1363094/tong-hop-cac-ham-trong-excel-28.png "Sử dụng hàm IF")

**Xem thêm**: [Cách dùng hàm IF trong Excel | Có ví dụ đơn giản dễ hiểu](https://www.dienmayxanh.com/kinh-nghiem-hay/cach-dung-ham-if-trong-excel-co-vi-du-don-gian-d-1346707 "Cách dùng hàm IF trong Excel | Có ví dụ đơn giản dễ hiểu")

#### **3. Hàm SUMIF**

[Hàm SUMIF](https://www.dienmayxanh.com/kinh-nghiem-hay/ham-sumif-trong-excel-cach-su-dung-don-gian-va-de-1378866 "Hàm SUMIF") dùng để tính tổng các giá trị trong một phạm vi đáp ứng tiêu chí xác định.

Cú pháp:

**\=SUMIF(range,criteria,\[sum_range])**

Với:

**range**: Phạm vi ô bạn muốn đánh giá theo tiêu chí

**criteria**: Tiêu chí ở dạng số, biểu thức, tham chiếu ô, văn bản hoặc hàm xác định sẽ cộng ở ô nào

**sum_range**: Các ô thực tế để cộng nếu bạn muốn cộng các ô không phải là ô đã xác định trong đối số range. Nếu đối số sum_range bị bỏ qua, Excel cộng các ô được xác định trong đối số range.

Ví dụ: Tính tổng số màu cam ở cột A có số lượng xuất hiện trong cột B, có công thức =SUMIF(A1:A8,"cam",B1:B8)

![Hàm SUMIF](https://cdn.tgdd.vn/Files/2021/06/24/1363094/tong-hop-cac-ham-trong-excel-17.png "Hàm SUMIF")

# Hàm sử dụng trong văn bản

#### **1. Hàm LEFT/RIGHT/MID**

\- Hàm LEFT dùng để cắt chuỗi ký tự bên trái chuỗi văn bản mà người dùng chọn.

Cú pháp:

**\=LEFT(text,\[num_chars])**

Với:

**text**: Chuỗi văn bản chứa ký tự mà bạn muốn trích xuất

**num_chars**: Là số lượng ký tự mà hàm LEFT trích xuất

Ví dụ: Trong bảng dưới đây, dùng hàm LEFT để tìm 3 ký tự đầu tiên tại ô B2. Nhập công thức **\=LEFT(B3,3)**, nhấn **Enter** và được kết quả như hình.

![Ví dụ về hàm LEFT](https://cdn.tgdd.vn/Files/2021/06/24/1363094/tong-hop-cac-ham-trong-excel-18.png "Ví dụ về hàm LEFT")

\- Hàm RIGHT dùng để tách chuỗi ký tự từ bên phải trong một dãy ký tự mà người dùng chọn.

Cú pháp:

**\=RIGHT(text,\[num_chars])**

Với:

**text**: Chuỗi văn bản chứa ký tự mà bạn muốn trích xuất

**num_chars**: Là số lượng ký tự mà hàm RIGHT trích xuất

Ví dụ: Trong bảng dưới đây, dùng hàm RIGHT để tìm 7 ký tự cuối tại ô B2. Nhập công thức **\=RIGHT(B3,7)**, nhấn **Enter** và được kết quả như hình.

![Ví dụ về hàm RIGHT](https://cdn.tgdd.vn/Files/2021/06/24/1363094/tong-hop-cac-ham-trong-excel-19.png "Ví dụ về hàm RIGHT")

\- Hàm MID trả về một số lượng ký tự cụ thể từ một chuỗi văn bản, bắt đầu từ vị trí do bạn chỉ định và dựa vào số lượng ký tự do bạn chỉ định.

Cú pháp:

**\=MID(text, start_num, num_chars)**

Với:

**text**: Chuỗi văn bản có chứa các ký tự muốn trích xuất.

**start_num**: Ví trí của ký tự thứ nhất mà bạn muốn trích xuất trong văn bản

**num_chars**: Bắt buộc đối với mid. Chỉ rõ số ký tự mà bạn muốn hàm MID trả về từ văn bản.

Ví dụ: Trong bảng dưới đây, dùng hàm MID để tìm 7 ký tự tại ô B2 bắt đầu từ vị trí thứ 3. Nhập công thức **\=LEFT(B3,3,7)**, nhấn **Enter** và được kết quả **"ạm Văn "**

![Ví dụ về hàm MID](https://cdn.tgdd.vn/Files/2021/06/24/1363094/tong-hop-cac-ham-trong-excel-20.png "Ví dụ về hàm MID")

**Xem thêm**: [Cách sử dụng hàm MID trong Excel để cắt chuỗi](https://www.dienmayxanh.com/kinh-nghiem-hay/cach-su-dung-ham-mid-trong-excel-de-cat-chuoi-1352217 "Cách sử dụng hàm MID trong Excel để cắt chuỗi")

**2. Hàm LEN**

Hàm LEN dùng để đếm ký tự trong một chuỗi hoặc một ô chứa chuỗi ký tự và bao gồm cả khoảng trắng.

Cú pháp:

**\=LEN(chuỗi ký tự)**

hoặc

**\=LEN(ô chứa chuỗi ký tự)**

Ví dụ: Trong ví dụ ta thực hiện đếm ô A1 đang chứa chuỗi ký tự "**Điện máy XANH**"

![Ví dụ về hàm LEN](https://cdn.tgdd.vn/Files/2021/06/24/1363094/tong-hop-cac-ham-trong-excel-21.png "Ví dụ về hàm LEN")

**Xem thêm**: [Cách dùng hàm LEN trong Excel để đếm ký tự, có bài tập minh họa](https://www.dienmayxanh.com/kinh-nghiem-hay/cach-dung-ham-len-trong-excel-de-dem-ky-tu-1352017 "Cách dùng hàm LEN trong Excel để đếm ký tự, có bài tập minh họa")

#### **3. Hàm CONCAT**

Hàm CONCAT dùng để nối hai hay nhiều chuỗi văn bản thành một chuỗi văn bản.

Cú pháp:

**\=IF(Logical_test;Value_if_true;Value_if_false**)

Với:

**Logical_test**: Điều kiện.

**Value_if_true**: Giá trị trả về nếu thỏa điều kiện

**Value_if_false**: Giá trị trả về nếu không thỏa điều kiện.

Lưu ý: Nếu bỏ trống **Value_if_true** và **Value_if_false**, nếu điều kiện thỏa thì giá trị trả về sẽ là 0 và điều kiện không thỏa thì giá trị trả về sẽ là FALSE.

Ví dụ:

**\=CONCAT("Điện"," ","máy"," ","XANH"," ","Xin"," ","Cám"," ","ơn.")** sẽ trả về "**Điện máy XANH Xin Cám ơn.**"

# Hàm ngày tháng

#### **1. Hàm NOW**

Hàm NOW dùng để hiển thị ngày và thời gian hiện tại trên hệ thống của bạn, hoặc muốn tính toán giá trị dựa trên ngày và thời gian hiện tại và cập nhật lại mỗi khi bạn mở lại trang tính.

Cú pháp:

**\=NOW()**

Ví dụ:

\=NOW() : Trả về ngày và thời gian hiện tại trên hệ thống của bạn.

\=NOW()+7: Trả về ngày và thời gian 7 ngày trong tương lai

#### **2. Hàm DATE**

Hàm DATE trả về kết quả số cho ngày cụ thể.

Cú pháp:

**\=DATE(Year,Month,Day)**

Với:

**Year:** chỉ năm. Excel diễn giải đối số năm theo hệ thống ngày được thiết lập trên máy tính của bạn.

**Month**: chỉ tháng. Một số nguyên đại diện cho tháng trong năm, từ tháng 1 đến tháng 12.

**Day**: chỉ ngày. Một số nguyên dương ứng với ngày trong tháng.

Ví dụ: **\=DATE(2015,5,20)** trả về kết quả ngày 20 tháng 5 năm 2015.

# Hàm tra cứu dữ liệu

#### **1. Hàm VLOOKUP**

\- Hàm VLOOKUP là hàm được sử dụng khi cần dò tìm dữ liệu trong một bảng, một phạm vi theo hàng dọc và trả về dữ liệu tương ứng theo hàng ngang.

Cú pháp:

**\=VLOOKUP(Lookup_value, Table_array, Col\_index\_ num, Range_lookup)**

Với:

**Lookup_value**: Giá trị cần dò tìm, có thể điền giá trị trực tiếp hoặc tham chiếu tới một ô trên bảng tính.

**Table_array**: Bảng giới hạn để dò tìm.

**Col_index_num**: Số thứ tự của cột lấy dữ liệu trong bảng cần dò tìm, tính từ trái qua phải.

**Range_lookup**: tìm kiếm chính xác hay tìm kiếm tương đối với bảng giới hạn, nếu bỏ qua thì mặc định là 1.

* Nếu **Range_lookup = 1** (TRUE): dò tìm tương đối.
* Nếu **Range_lookup = 0** (FALSE): dò tìm chính xác.

Ví dụ: Xác định mức phụ cấp cho nhân viên. Tại ô E4, bạn điền công thức: **\=VLOOKUP(D4,$H$3:$I$8,2,0)**

Giải thích công thức (theo thứ tự các đối số trong công thức từ trái sang):

* Dấu **$** được sử dụng để cố định các dòng, các cột của bảng 2 khi bạn copy công thức sang các ô khác.
* **2** là số thứ tự của cột dữ liệu.
* **Range_lookup = 0** (FALSE) để dò tìm chính xác.

![Sử dụng hàm VLOOKUP](https://cdn.tgdd.vn/Files/2021/06/24/1363094/tong-hop-cac-ham-trong-excel-29.png "Sử dụng hàm VLOOKUP")

**Xem thêm**: [Hàm VLOOKUP trong Excel: Cách dùng hàm VLOOKUP, có ví dụ cụ thể](https://www.dienmayxanh.com/kinh-nghiem-hay/ham-vlookup-trong-excel-cong-thuc-vi-du-cu-the-d-1355993 "Hàm VLOOKUP trong Excel: Cách dùng hàm VLOOKUP, có ví dụ cụ thể")

#### **2. Hàm INDEX**

Hàm INDEX là hàm cho kết quả trả về là một giá trị hoặc tham chiếu tới một giá trị trong bảng hoặc một phạm vi nhất định.

Cú pháp: **\=INDEX(array, row_num, column_num)**

Với:

**array**: Phạm vi ô hoặc một hằng số mảng. Nếu mảng chỉ chứa một hàng hoặc cột thì **row_num** hoặc **column_num** tương ứng là tùy chọn. Nếu **mảng có nhiều hàng** và **nhiều hơn một cột** mà bạn chỉ khai báo 1 trong 2 đối số row_num hoặc column_num, hàm sẽ trả về một mảng của toàn bộ hàng hoặc cột trong mảng.

**row_num**: Thứ tự của hàng trong mảng chứa giá trị trả về. Đây là đối số bắt buộc phải có, trừ khi bạn khai báo column_num. Nếu bỏ qua row_num, bạn cần phải khai báo column_num.

**column_num**: Thứ tự của cột trong mảng chứa giá trị trả về. Nếu bỏ qua column_num, bạn cần khai báo row_num.

Ví dụ: Bây giờ, giả sử bạn cần tìm giá trị của phần tử ở dòng thứ 4, cột thứ 1 trong mảng. Mảng ở đây gồm 10 dòng và 4 cột (có địa chỉ là B4:E13). Bạn nhập công thức: **\=INDEX(B4:E13,4,1)**

Giải thích công thức (theo thứ tự các đối số trong công thức từ trái sang):

* **B4:E13** là mảng chứa giá trị cần trả về.
* **4** là số thứ tự của hàng trong mảng chứa giá trị cần trả về.
* **1** là số thứ tự của cột trong mảng chứa giá trị cần trả về.

Sau khi nhập xong, bạn nhấn Enter. Kết quả trả về sẽ như hình dưới.

![Ví dụ về hàm INDEX](https://cdn.tgdd.vn/Files/2021/06/24/1363094/tong-hop-cac-ham-trong-excel-24.png "Ví dụ về hàm INDEX")

**Xem thêm**: [Hàm INDEX trong Excel, cách sử dụng có bài tập cụ thể](https://www.dienmayxanh.com/kinh-nghiem-hay/ham-index-trong-excel-cach-su-dung-co-bai-tap-1359667 "Hàm INDEX trong Excel, cách sử dụng có bài tập cụ thể")

#### **3. Hàm MATCH**

Hàm MATCH là hàm tìm kiếm, xác định vị trí tương đối của một giá trị trong một mảng hoặc một ô.

Cú pháp:

**\=Match(Lookup_value, Lookup_array, Match_type)**

Với:

\- **Lookup_value**: Giá trị mà bạn muốn tìm kiếm.

\- **Lookup_array**: Mảng hoặc dải ô bạn muốn xác định vị trí của Lookup_value. Vùng dữ liệu mà bạn chọn chỉ có thể có duy nhất 1 hàng hoặc 1 cột.

\- **Match_type**: Xác định kiểu khớp là -1; 0 và 1.

* **Kiểu khớp là 0**: Trả về vị trí tương đối của giá trị trong trường hợp vùng dữ liệu chưa được sắp xếp.
* **Kiểu khớp là 1**: Trả về vị trí của giá trị lớn nhất nhưng nhỏ hơn hoặc bằng giá trị cần tìm. Giả sử vùng dữ liệu được sắp xếp theo thứ tự tăng dần.
* **Kiểu khớp là -1**: Trả về vị trí của giá trị nhỏ nhất nhưng lớn hơn hoặc bằng giá trị cần tìm. Giả sử vùng dữ liệu được sắp xếp theo thứ tự giảm dần.

Ví dụ: Dưới đây là hồ sơ thi tuyển của các học sinh và bạn muốn tìm vị trí của học sinh Lâm Thiên Trang.Tại ô G3 ta thực hiện công thức: **\=MATCH(G1,A2:A9,0)**

![ví dụ về hàm MATCH](https://cdn.tgdd.vn/Files/2021/06/24/1363094/tong-hop-cac-ham-trong-excel-30.png "ví dụ về hàm MATCH")

**Xem thêm**: [Hàm MATCH trong Excel - Cách tìm vị trí được chỉ định](https://www.dienmayxanh.com/kinh-nghiem-hay/ham-match-trong-excel-cach-tim-vi-tri-duoc-chi-d-1356755 "Hàm MATCH trong Excel - Cách tìm vị trí được chỉ định")

#### **4. Hàm HLOOKUP**

[Hàm HLOOKUP](https://www.dienmayxanh.com/kinh-nghiem-hay/ham-hlookup-trong-excel-cong-thuc-vi-du-cu-the-d-1363283 "Hàm HLOOKUP") là hàm tìm kiếm một giá trị trên dòng đầu tiên của bảng tham chiếu và cho kết quả tương ứng trong dòng chỉ định.

Cú pháp:

**\=HLOOKUP(Lookup\_value,Table\_ array,Row_index_Num,Range_lookup)**

Với:

**Lookup_value**: giá trị đối chiếu với dòng đầu tiên của bảng tham chiếu để lấy được giá trị cần tìm.

**Table_array**: là địa chỉ tuyệt đối của bảng tham chiếu, không lấy cột tiêu đề.

**Row_index_Num**: Số thứ tự dòng chứa giá trị cần lấy của bảng tham chiếu (theo thứ tự từ trên xuống dưới và bắt đầu từ số 1).

**Range_lookup**: Cách tìm kiếm trên bảng tham chiếu.

* **"+ 0"**: Dòng đầu tiên của bảng tham chiếu chưa sắp xếp.
* **"+ 1"**: dòng đầu tiên của bảng tham chiếu đã sắp xếp theo chiều tăng dần (ngầm định).

Ví dụ: Ta cần xếp loại học sinh trong Bảng 1 (B3:D8) với dữ kiện ở Bảng 2 (B11:F12), tại D4 ta có: **\=HLOOKUP(C4,$B$11:$F$12,2,1)**. Hàm HLOOKUP sẽ dò tìm điểm số ở ô C4 trong Bảng 2 từ trái qua phải. Khi tìm thấy giá trị gần bằng, nó sẽ trả về kết quả xếp loại tương ứng nằm ở hàng 2.

![Ví dụ về hàm HLOOKUP](https://cdn.tgdd.vn/Files/2021/06/24/1363094/tong-hop-cac-ham-trong-excel-23.png "Ví dụ về hàm HLOOKUP")

**N﻿guồn: [Điện máy xanh](https://www.dienmayxanh.com/kinh-nghiem-hay/tong-hop-cac-ham-co-ban-trong-excel-thuong-duoc-su-1363094)**