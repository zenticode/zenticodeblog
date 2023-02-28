---
title: Những thói quen xấu làm kìm hãm sự tiến bộ của các lập trình viên, mới
  bắt đầu làm chưa lâu, mà tôi đã nhận ra trong khi kèm cặp họ
date: 2023-02-28 15:49
tags:
  - Code
description: Hàng ngày, tôi vẫn tự hỏi mình năng lực lập trình là do thứ gì
  quyết định? Có người học lập trình rất nhanh nhưng có người lại học rất chậm.
  Thông thường, người ta hay gọi cái đó là “ngộ tính tốt, ngộ tính chưa tốt” và
  cho qua.
---
*Nguồn* : <http://qiita.com/hirokidaichi/items/27c757d92b6915e8ecf7?utm_content=buffer65af1&utm_medium=social&utm_source=facebook.com&utm_campaign=buffer>

*Người dịch : Phan Hoàng Minh*

Gần đây, tôi được phân công hỗ trợ những người lập trình chưa giỏi, dưới hình thức một kèm một (pair programming).

Trong khi làm công việc đó, tôi nhận thấy có một vài thói quen xấu khiến họ khó tiến bộ và thói quen tốt nữa mà tôi sẽ liệt kê ra như dưới đây.

## **Sức mạnh của thói quen**

Hàng ngày, tôi vẫn tự hỏi mình năng lực lập trình là do thứ gì quyết định? Có người học lập trình rất nhanh nhưng có người lại học rất chậm. Thông thường, người ta hay gọi cái đó là “ngộ tính tốt, ngộ tính chưa tốt” và cho qua.

Nhưng tôi thấy rõ ràng có những yếu tố quyết định đến việc học nhanh hay chậm.

Vài năm trước vào một lần nọ, tôi có xem màn hình của đồng nghiệp ngồi bên cạnh và thỉnh thoảng đi quanh phòng làm việc xem màn hình của những người khác nữa. Có một điều làm tôi thực sự ngạc nhiên. Người hay “nộp bài” chậm thì màn hình lại thường có xu hướng hiển thị stack trace (dùng cho đầu ra của web application).

Đồng nghiệp ngồi cạnh tôi thường lập trình theo quy trình dưới đây. Tôi không thống kê chi tiết, nhưng đại loại là vậy.

* Viết code
* Lưu code
* Switch màn hình sang browser
* Reload
* Màn hình lỗi hiện ra
* Switch sang màn hình code luôn

Như thế này thì tôi nghĩ năng suất làm việc sẽ rất tồi. Phải nói thêm là cậu ta đang viết một phần thuộc model (và tất nhiên phần đó có ở bên controller nữa).

Ngay lập tức, tôi chỉ cho cậu ấy cách check syntax và cách chạy thử từng module. Dựa vào đó, tôi chỉ thêm cho cậu ấy cách viết những test code nhỏ cho phần logic nữa. Nhưng hình như cậu ấy vốn đã biết cả rồi.

Tuy nhiên, vì nghĩ là phiền phức nên cậu ấy đã bỏ qua.

Tôi hỏi tại sao lại phiền thì cậu ấy có hơi lúng túng, giải thích khá nhiều nhưng đại ý là “Đằng nào cũng phải hiển thị, nên xem nó hiển thị thế nào là nhanh nhất”.

Đây là vấn đề về thói quen. Ngày đó công ty tôi chưa có quy trình CI (continous integration) nên hầu như không ai có thói quen viết test cho code cả.

Về sau, quy trình CI được áp dụng, việc viết test cho code trở thành bắt buộc. Tuy nhiên khi đó thì sau khi hiển thị ngon hết rồi cậu ta mới viết, với một thái độ không lấy gì làm vui vẻ cho lắm.

Quy trình phía trên của cậu ấy, do chạy code sau khi đã ghép nên màn hình sẽ hiện một đống lỗi rất phức tạp làm cho công việc kéo dài ra. Cậu ta dường như không quan tâm đến chuyện đó mà có khi cũng chẳng đọc lỗi nữa.

Cậu ấy không quen test từng phần một, mà sau khi ghép code sẽ khó test hơn rất nhiều.

Quy trình vốn sinh ra để tăng năng suất, bây giờ do thói quen của người làm việc, thành ra lại làm giảm năng suất.

## **Thói quen xấu**

Gần đây, tôi có pair programming với vài kĩ sư trẻ. Một ngày tôi làm với họ vài tiếng, chiếm phần lớn thời gian ở công ty của tôi.

Tôi sẽ giới thiệu vài thói quen xấu của họ mà trong khi làm việc tôi đã phát hiện và nhắc nhở.

## **Ít đọc code**

Tùy từng project mà thời gian đọc code khác nhau, nhưng nhìn chung thời gian đọc code luôn chiếm tỉ lệ lớn. Cách phân bố thời gian thường thấy là 80% đọc, 20% viết. Đọc code là bắt buộc để có thể hiểu được những phần liên quan, và hiểu framework.

Đối với những kĩ sư mà công việc hay bị trục trặc, không tiến triển, tôi thấy tỉ lệ thời gian họ dành cho việc đọc code là rất thấp.

Một ví dụ là có một cậu định sử dụng chức năng có trong framework thì bị lỗi. Tôi nói với cậu ấy là ở framework đang hiển thị lỗi sai đầu vào.

Tuy nhiên cậu ấy sau đó không hề xem chỗ tôi bảo trên framework.

Vậy thì cậu ấy làm gì?

* Nhìn chăm chú vào code của mình, ngẩn ngơ tìm chỗ sai.
* Nghiền ngẫm một đoạn code trên mạng để xem có nên copy paste không.

Nghĩa là cứ khi nào code không chạy thì cậu ấy đều ngồi xem code mình viết có gì sai.

### **Cách sửa**

Tôi chỉ cho cậu ấy cách tìm đoạn bị sai tương ứng trên framework. Đồng thời, tôi bảo cậu ấy đọc xem đoạn ấy xử lí cụ thể như thế nào và kết luận tại sao code không chạy.

### **Vấn đề tâm lí**

Tôi hỏi tại sao cậu ấy không đọc code của framework thì cậu ấy trả lời rằng “Nhìn phức tạp lắm, với lại em muốn làm xong sớm”. Tôi cũng công nhận là nội dung bên trong framework phức tạp thật, và đúng là rất khó để nắm được tổng thể.

Tuy nhiên bằng cách nghiên cứu nó, kiến thức về ngôn ngữ và khả năng đọc hiểu thư viện sẽ tăng lên, trình độ bản thân sẽ tăng lên.

Tôi đã cho cậu ấy trải nghiệm việc phá bỏ rào cản tâm lí đó, ngồi nghiên cứu code sẽ khiến vấn đề được giải quyết nhanh như thế nào.

Vì những lẽ ở trên, tôi nghĩ là người hướng dẫn cũng không nên nói những câu đại loại như “Phần này không hiểu cũng được”, “Đừng đọc nhiều làm gì, cứ cho chạy đi đã” - điều đó cũng rất quan trọng.

Tôi luôn nghĩ : giới hạn trưởng thành của bạn cao đến mức nào, phụ thuộc vào việc bạn hiểu code sâu đến mức nào.

## **Không test riêng những đoạn xử lí phức tạp**

Tôi đã từng nói ở bài viết trước là việc chia nhỏ các hàm rất quan trọng. Tại sao lại phải chia? “Vì như thế thì sẽ nhàn hơn”. Tuy nhiên đối với người chưa thuần thục thì lại cảm thấy như thế là “khổ hơn”.

Hàm có cấu trúc như thế này nghĩa là muốn thực hiện xử lí riêng từng phần một. Người chưa thuần thục thường có xu hướng cứ thế viết những gì muốn xử lí vào những chỗ comment ở trên.Những phần muốn xử lí viết tách ra ngoài, độc lập (gọi là sprout method). Làm như thế sẽ tránh cho hàm gốc bị phức tạp hóa, và giúp ta test được từng xử lí một.

### **Cách sửa**

Tôi cho họ làm quen với quy trình là trước khi động tay vào hàm gốc thì hãy tách những gì mình cần xử lí ra thành những hàm rời, sau đó viết và test những cái rời trước. Sau đó họ đã thấy kết quả là việc giải quyết lỗi phát sinh trở nên nhanh như thế nào. Đồng thời, tôi giúp họ ý thức đầu ra đầu vào là gì, phần mình làm ảnh hưởng các phần khác như thế nào.

### **Vấn đề tâm lí**

Nguyên nhân của chuyện cảm thấy việc chia nhiều hàm là khổ chính là từ suy nghĩ “muốn xong sớm” mà ra. Họ nghĩ “Sau này có lỗi thì chỉ cần xem lỗi ở đâu rồi sửa là xong” nên họ thấy chia nhiều hàm rất là “phức tạp hóa vấn đề”, chỉ là chuyện “nếu thừa thời gian thì làm”.

Tuy nhiên, nếu gộp hết tất cả thành 1 hàm rồi chạy, thì việc hiểu code sẽ rất khó và cái vòng luẩn quẩn “chạy và lỗi” sẽ kéo dài, lỗi lại còn rất nặng. Như thế mới chính là đang làm mất thời gian.

Cũng như trong Hình học để giải bài toán ta hay phải kẻ đường phụ. Việc học cách kẻ đường đó như thế nào là một điều rất quan trọng.

## **Không kiểm tra quy trình làm việc của bản thân**

Như phần đầu tôi đã nói, thói quen chính là sức mạnh. Chúng ta cần phải có một quy trình làm việc nhanh nhất có thể, hướng đến mục tiêu là tự động hóa.

Từ hôm pair programming, tôi mới nhận ra một cậu hay ngồi nhìn code chằm chằm sau khi viết. Tôi hỏi là đang làm gì thế thì cậu ấy bảo “Em đang kiểm tra”. Cậu ấy đúng là đang kiểm tra từng dòng code một, xem mình có viết sai gì không.

Tôi bảo cậu ấy trước tiên hãy check syntax đi thì cậu ấy hỏi “Check syntax nghĩa là sao ạ?”. Sau khi tôi chỉ cậu ấy cách làm thì cậu ấy sau đó cứ liên tục hỏi tôi “Câu này đúng chưa anh?”, “Thế này được chưa?”.

Tôi trả lời là trước hết cứ tự mình kiểm tra đi đã, cậu ấy không hiểu ý tôi là gì.

Tôi đã nhận ra rằng ngoài quy trình check xem code của mình sau khi build và cho chạy thật đã ngon chưa, họ không có thêm một quy trình nào khi làm việc cả. Unit test vốn là thứ được sinh ra để xem từng phần có hoạt động chính xác không. Nếu trong khi làm không chuẩn bị trước, không phải là người có thói quen vừa làm vừa test (test first), thì sau này làm unit test sẽ rất mệt.

### **Cách sửa**

Phần code dùng để check syntax hãy để riêng ra editor và dùng thường xuyên. Nếu cần thiết, cứ khi save code là tự động cho chạy luôn để test.

Vì cậu ấy dùng editor là vim nên cần cài plugin như quickrun hay syntastic.

<https://github.com/thinca/vim-quickrun>

<https://github.com/scrooloose/syntastic>

Các class và các hàm cũng vậy, ở đâu cũng được, nhưng cần phải tạo môi trường để kiểm tra từng cái một. Nếu kiểm tra thấy ngon rồi, thì hãy lưu lại vào một file test.

Đó là quy trình mà tôi muốn cậu ấy thực hiện. Trước khi hỏi “Thế này được chưa” thì hãy làm tất cả những việc trên đã.

Khi đã quen rồi, nên tạo một môi trường CI dựa trên cách dùng debug hoặc fswatch. Mỗi khi save code thì cho chạy luôn cái CI đó để test là tốt nhất.

### **Vấn đề tâm lí**

Vấn đề về môi trường như bên trên có vẻ như liên quan đến kiến thức chứ không liên quan đến tâm lí. Tuy nhiên sau khi phân tích, tôi thấy nó liên quan đến nhận thức về 2 khái niệm thường gặp khi lập trình là “code chuẩn” và “code lỗi mà không biết vì sao”.

Một thực tế là, không phải chỉ có duy nhất một “code chuẩn”.

Tuy nhiên, người hay copy paste thường có xu hướng nghĩ rằng : copy paste mà cũng không chạy được thì chắc là do mình thao tác sai chỗ nào đó, copy paste bị thiếu chỗ nào đó và thường có thói quen ngồi tìm kiếm những cái đó.

Vì lí do đó, code của họ sau khi viết xong chẳng khác nào mật mã ngoài hành tinh, và họ sẽ phải tìm lỗi sai trong đống mật mã đó. Phần mà họ tự viết ra cũng dựa trên những đoạn copy paste, mà sau này rồi cũng sẽ trở thành thứ mà họ không thể tự lí giải nổi.

Tâm lí của họ là luôn nghĩ việc đọc hiểu và kiểm tra từng dòng một, kém năng suất hơn việc copy paste cả một đoạn rất nhiều.

## **Không đọc error message, không đọc log**

Error message của ngôn ngữ lập trình, hay error message của thư viện đều có nhiệm vụ là chỉ ra chỗ sai bằng văn bản con người có thể hiểu được, viết bởi con người. Tuy nhiên, những lập trình viên tiến bộ chậm thường không đọc những cái đó. Họ chỉ ý thức được là có lỗi xảy ra.

Nếu là code trên IDE thì có thể kích chuột để jump ngay đến câu lệnh lỗi. Nhưng nếu làm trên vim hoặc Web browser thì việc đọc hiểu log message, và jump đến câu lệnh lỗi là nhiệm vụ của người lập trình.

Không đọc, cũng không jump đến câu lệnh lỗi nên màn hình error thường bị switch đi trong tích tắc. Trong khi pair programming với vài người, họ switch màn hình nhanh đến nỗi tôi còn tưởng họ đang thử độ phản ứng của mắt với vật thể chuyển động.

Kết quả là họ ngồi nhìn chằm chằm vào code họ vừa viết, tìm xem có lỗi chính tả, lỗi font nào không bằng cách ngó đi ngó lại method name.

Vấn đề là error message vừa nãy đâu có nói là method name có lỗi, hoặc không tồn tại.

Một khi không đọc error message thì phạm vi có thể phát sinh lỗi là vô hạn. Tuy nhiên, họ chỉ luôn nghĩ được là mình “viết sai một cái gì đó”.

### **Cách sửa**

Tất nhiên là đọc error message và tìm hiểu ý nghĩa của từng message một.

Thêm vào đó, tôi giúp họ lí giải mối liên hệ giữa error message và môi trường. Đồng thời, hướng dẫn họ tạo ra những đoạn code nhỏ để tái hiện các lỗi đó (snippet) có thể dùng cho sau này và dự trù các case tương tự có thể xảy ra.

### **Vấn đề tâm lí**

Có thanh niên nói “Em sợ tiếng Anh lắm, nhìn cứ như mật mã”. Có điều, ngữ pháp của các error message chỉ dừng ở mức học sinh cấp Hai, mà tôi biết là cậu ta thừa sức hiểu.

Cũng phải công nhận một thực tế là muốn hiểu những lỗi liên quan đến ngôn ngữ lập trình và framework thì phải hiểu cấu trúc và từ ngữ chuyên ngành của chúng. Điều này khó.

Nhưng như vậy không có nghĩa là ngôn ngữ hoặc framework đó “không thân thiện” mà vì bản thân error message không phải sinh ra chỉ để hiển thị những lỗi liên quan đến code người lập trình viết.

Vì vậy ta cần theo sát cả framework, cả ngôn ngữ lập trình, và cả code. Có như vậy ta mới có thể móc nối error message và vấn đề cần giải quyết với nhau.

Để có thể tự mình làm như vậy, hàng ngày cần tự tạo thói quen tìm hiểu những thứ đó cho mình. Nếu không cho dù đến bao giờ chăng nữa, error message cũng vẫn mãi chỉ là những “mật mã” mà thôi.

## **Không biết cách đào sâu vấn đề**

Có lỗi xảy ra, nghĩa là chúng ta có thể tìm ra manh mối để giải quyết vấn đề bằng cách xem xét phần code bị báo lỗi.

Ở đó có lỗi, nghĩa là ít nhất thì code đã chạy được cho đến đó.

Hơn thế nữa, nguyên nhân lỗi phát sinh rất có thể là do ảnh hưởng của những gì mà chúng ta đã nhập vào.

Chẳng hạn, bằng cách dùng printf để debug, chúng ta có thể biết nhập cái gì vào module, biến đổi nó ra sao thì sẽ sinh ra lỗi. Thông qua việc đó, chúng ta sẽ hiểu khái quát vấn đề, sau đó tuần tự thử các bước chạy của chương trình là có thể chỉ ra được cụ thể phần nào bị lỗi.

Tuy nhiên, người không biết cách đào sâu vấn đề thường cho chương trình chạy với tâm lí là sẽ chạy ngon và check code với tâm lí “đáng ra nó phải chạy ngon”. Họ thường không quan tâm đến thứ tự các bước chạy của chương trình, cách làm việc của họ chẳng khác nào lần mò trong đám mây.

Trong một vài trường hợp, họ sẽ mãi “ngẩn ngơ” vì không hiểu sai từ đâu. Họ không có trong tay một chiến thuật để tìm ra chỗ sai nên sẽ nhanh chóng rơi vào trạng thái người ta vẫn gọi là “quay cuồng”.

### **Cách sửa**

Sau khi xảy ra lỗi, trước khi họ làm một động tác gì tôi đều yêu cầu họ trả lời câu hỏi này trước “Bây giờ chúng ta cần làm gì?”. Cụ thể, tôi muốn họ nêu ra phương pháp tìm ra chỗ sai. Tôi giúp họ xây dựng phương pháp đó bằng cách hỏi những câu như “Code chạy ngon đến đoạn nào?”. Sau khi tìm ra một manh mối gì đó, tôi lại hỏi “Thông tin này có ý nghĩa gì?”, “Có cần thay đổi phương pháp không?”.

Tôi muốn họ ý thức được là mình cần đào sâu có mục tiêu đàng hoàng, chứ không phải là lần mò trong đám mây.

### **Vấn đề tâm lí**

Đối với một chương trình, việc xảy ra lỗi là một minh chứng cho việc “đã gần hoàn thiện”. Tại sao? Vì nó thường chỉ cho ta sáng tỏ một điều mà trước đây ta không quan tâm, chỉ cho ta biết giả thiết mà ta đã tạo ra là sai, và chỉ cho ta hành động tiếp theo mà ta phải làm là sửa nó. Ta đã có định hướng.

Tuy nhiên, đối với những progammer không giỏi đào sâu vấn đề thì thường có xu hướng bị “ngây người” vì họ luôn nghĩ rằng “Đáng ra phải chạy ngon rồi chứ nhỉ?”. Và sau đó họ lại nghĩ “Toi rồi, sai hết rồi”.

Có thể nói rằng họ không bao giờ test những cái mà chắc sẽ thất bại, trong khi giá trị cao nhất của việc test là sau khi thất bại, nó sẽ cho ta một thông tin hữu ích nào đó.

Tôi bảo họ chạy thử thì họ thường nói “Lỗi là cái chắc” và không làm. Còn khi miễn cưỡng làm rồi chương trình không chạy thì họ bảo “Đấy, thấy chưa?”.

Thực tế là lỗi ở môi trường chạy thật thì không được phép, nhưng ở môi trường test thì sẽ chẳng có ai phàn nàn gì cả, thậm chí còn có ích.

Tôi nghĩ họ cần được tự mình trải nghiệm và lí giải những điều đó.

## **Thói quen tốt**

Dựa vào những thói quen xấu đã nói ở trên, chúng ta có thể biết được đâu là thói quen tốt.

* Đầu tư thời gian để đọc code và hiểu code.
* Luôn có xu hướng dùng kiến thức để đơn giản hóa vấn đề trước mắt
* Không sợ lỗi, luôn dùng test code để tìm kiếm thông tin, manh mối
* Luôn hành động với mục đích rõ ràng để từng bước một giải quyết vấn đề

Ngoài ra, còn vài thói quen mà tôi nghĩ là tốt như :

* Cải tiến công cụ và tự động các hóa quy trình
* Boy scout policy
* Học vài ngôn ngữ
* Học kiến thức một cách tổng thể

### **Cải tiến công cụ và tự động hóa các quy trình**

Thói quen tốt thường được hỗ trợ bởi công cụ tốt. Chẳng hạn mỗi khi học ngôn ngữ mới, tôi đều tìm kiếm code formatter của ngôn ngữ đó.

Ngoài ra, tôi có coding style của mình - không muốn ấn quá nhiều phím, nên tôi chọn IDE có chức năng tự động nhập space cho tôi.

### **Boy scout policy**

Có một tổ chức gọi là boy scout có phương châm là : nhặt hết rác trên các đoạn đường mình đi qua. Cũng như vậy, người lập trình cần có phương châm sửa hết lỗi của những code liên quan đến phần mình làm. Dĩ nhiên không đọc cẩn thận thì sẽ không sửa được, nhưng dù không sửa thì đọc code thôi cũng là có ích rồi.

Làm như vậy thì tự nhiên sẽ ngày càng hiểu sâu về code hơn, và code tổng thể sẽ đẹp hơn.

### **Học vài ngôn ngữ**

Nhiều khi vấn đề ở ngôn ngữ này ta có thể lí giải được trong khi học ngôn ngữ khác. Và nhiều khi, một khái niệm nghe có vẻ lạ, thực ra chỉ là đem từ ngôn ngữ khác vào.

Thế nên, việc học nhiều ngôn ngữ sẽ giúp ta lập trình mau thuần thục hơn.

### **Học kiến thức một cách tổng thể**

Như bài trước tôi đã viết, kiến thức về background, về lịch sử ngôn ngữ, và vài ba bài tập ta đọc ở đâu đó sẽ khiến cho chất lượng code của ta tăng lên.

Nếu mỗi ngày ta không gặm nhấm một ít kiến thức, không có cách hiểu về cú pháp, về sample của riêng ta thì kiến thức sẽ không còn là kiến thức mà chỉ dừng ở mức mẹo vặt vì ta không biết ứng dụng chúng sang những trường hợp khác. Cứ thế, ta sẽ chỉ mãi mãi chạy theo những mẹo vặt để giải quyết vấn đề mà thôi.

## **Lời kết**

Năng lực tạo ra bởi tập hợp các thói quen nên việc cải thiện các thói quen sẽ khiến cho năng lực của chúng ta tăng lên. Đó là suy nghĩ của tôi.

Tiếp theo là do những rào cản tâm lí nên bản thân việc cải thiện các thói quen cũng thường không mấy dễ dàng. Cải thiện xong rồi, cũng không phải ngay lập tức đạt đến trình độ siêu nhân ngay được.

Nhưng đừng bao giờ nghĩ rằng mình vô dụng. Điều ảnh hưởng nhất đến kết quả cuối cùng của bạn là việc bạn có nghĩ được rằng : con đường học những điều mới là con đường hạnh phúc, hay không.