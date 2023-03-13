---
title: Sử dụng ChatGPT để xây dựng Sơ đồ hệ thống - Translators
date: 2023-03-13 17:57
tags:
  - ChatGPT
  - AI
description: Sự phổ biến của ChatGPT ngày càng tăng và hiện nay nó đang được sử
  dụng trong rất nhiều ứng dụng. Là một kiến trúc sư phần mềm, tôi đã có cơ hội
  khám phá khả năng của ChatGPT để sử dụng trong lĩnh vực tài chính, đặc biệt là
  quản lý tài sản.
---
Sự phổ biến của ChatGPT ngày càng tăng và hiện nay nó đang được sử dụng trong rất nhiều ứng dụng. Là một kiến trúc sư phần mềm, tôi đã có cơ hội khám phá khả năng của ChatGPT để sử dụng trong lĩnh vực tài chính, đặc biệt là quản lý tài sản.

![Đồ thị minh họa](https://oss.congdongchatgpt.com/congdongchatgpt/2023-03-13/1678701382-767531-graph.jpg)

Tôi muốn xác nhận xem ChatGPT có thể tạo ra các sơ đồ để giải thích một trường hợp sử dụng và phân tích nhiều yếu tố cùng một lúc.

Vì vậy, tôi đã đăng nhập vào [chat.openai.com](http://chat.openai.com/) và đây là cuộc trò chuyện của tôi:

**Bước 1: Hãy xác định trường hợp sử dụng**

Tôi có thể xác định trường hợp sử dụng của riêng mình, nhưng tôi muốn kiểm tra tất cả các khía cạnh của ChatGPT, vì vậy tôi đã yêu cầu nó xác định một trường hợp sử dụng cho tôi.

![](https://oss.congdongchatgpt.com/congdongchatgpt/2023-03-13/1678701425-394741-usecase-definition.webp)

**Bước 2: Hãy xác định một mô hình dữ liệu cho trường hợp sử dụng**

Trông có vẻ tốt đẹp đối với tôi, hãy bắt đầu bằng cách xác định mô hình dữ liệu - vì vậy tôi đã yêu cầu ChatGPT thực hiện điều đó và đây là kết quả tôi nhận được.

![](https://oss.congdongchatgpt.com/congdongchatgpt/2023-03-13/1678701459-395400-data-model.webp)

Nghe có vẻ đúng, hãy xem nó có thể làm gì cho các sơ đồ. Tôi muốn khám phá sâu hơn về mô hình dữ liệu, vì vậy lời nhắn tiếp theo của tôi là...

> Prompt: describe the data model in more detail or tabular format using markdown ChatGPT: I can describe the structure of the data model in a tabular format using markdown.

![](https://oss.congdongchatgpt.com/congdongchatgpt/2023-03-13/1678701510-21734-datatable.webp)

Điều này là một bước khởi đầu tốt. Tiếp theo, tôi yêu cầu định nghĩa các mối quan hệ.

**Bước 3: Hãy định nghĩa các mối quan hệ - Sơ đồ mối quan hệ thực thể.**

> Prompt: this is perfect, I would like to depict the relationships in a mermaid diagram, can you give me the markdown code to do this ChatGPT: I apologize, but as a text-based model, I am not able to generate Mermaid diagrams or any other visual diagrams. However, I can provide you with an example of how the relationships could be represented in Mermaid syntax:

![](https://oss.congdongchatgpt.com/congdongchatgpt/2023-03-13/1678701552-799332-graphdata.webp)

Và sau khi sao chép điều này vào trình soạn thảo markdown, đóng trong thẻ {mermaid}, tôi nhận được...

![](https://oss.congdongchatgpt.com/congdongchatgpt/2023-03-13/1678701589-11224-mermaid.webp)

**Bước 4: Sơ đồ trình tự**

Tiếp theo, tôi đã cố gắng đưa ra các lời nhắn giả thuyết để kiểm tra phản hồi. Mục đích đầu tiên của tôi là tạo một sơ đồ trình tự.

> Prompt: how would a Buy transaction for an asset impact the tables mentioned above, I would like to depict this as a sequence diagram. Can you help describe the diagram in markdown format for mermaid ChatGPT: Sure, a Buy transaction would have an impact on the following tables:
>
> Asset table: the current_value of the asset would be updated to reflect the current market value of the asset Portfolio table: the current_value of the portfolio would be updated to reflect the new asset and its market value, and the asset_allocation would be updated to reflect the new asset. Transaction table: a new transaction would be added with the transaction details such as the transaction type, transaction date, asset_id, and portfolio_id
>
> Here is an example of how the process could be represented in a Mermaid sequence diagram:

![](https://oss.congdongchatgpt.com/congdongchatgpt/2023-03-13/1678701641-995474-sequence-diagram.webp)

và sau đó sao chép nó vào trình soạn thảo markdown.

![](https://oss.congdongchatgpt.com/congdongchatgpt/2023-03-13/1678701673-883138-sequence.webp)

Ấn tượng phải không? Nhưng tôi chưa hoàn thành đâu.

**Bước 5: Sơ đồ chuyển trạng thái**

Hãy hỏi về một sơ đồ chuyển trạng thái.

> Prompt: Will the account have states like new, closed, active inactive etc? I would like to depict the states in a state diagram using mermaid. Can you help describe the diagram in markdown format ChatGPT: It is common for financial accounts to have different states, such as new, closed, active, and inactive, to reflect the current status of the account.
>
> new account would be one that has just been opened and is awaiting funding or verification. active account would be one that is currently open and being used for transactions. inactive account would be one that is not currently being used but has not been closed. closed account would be one that has been closed by the customer or the financial institution, and no longer able to be used for transactions. Pending state could be used to indicate that the account is under review or awaiting verification. Suspended state could be used to indicate that the account has been temporarily suspended, for example, due to suspicious activity or non-compliance with terms and conditions. Frozen state could be used to indicate that the account has been frozen, for example, due to a legal dispute or regulatory action. Expired state could be used to indicate that the account has reached its expiration date and is no longer in use.
>
> here is an example of how the states of an account could be represented in a Mermaid state diagram:

![](https://oss.congdongchatgpt.com/congdongchatgpt/2023-03-13/1678701732-654340-sequence-diagram-2.webp)

Dường như định dạng này đã lỗi thời và có thể gặp vấn đề do sự phụ thuộc lặp lại. Vì vậy, tôi đã yêu cầu ChatGPT cải thiện nó.

> Prompt: can you try giving the state diagram markdown syntax in new format using [*] ChatGPT: Sure, here is an example of how a state diagram for a wealth management system's account management component could be represented in Mermaid using the new format with [*]:

![](https://oss.congdongchatgpt.com/congdongchatgpt/2023-03-13/1678701780-36380-mermaid-representation.webp)

**Markdown Editor Representation**

![](https://oss.congdongchatgpt.com/congdongchatgpt/2023-03-13/1678701808-461554-markdown-representation.webp)

Sơ đồ này cho thấy các trạng thái khác nhau của một tài khoản và các chuyển tiếp có thể xảy ra giữa chúng.

Trạng thái ban đầu là \[*], đại diện cho trạng thái bắt đầu.

* Tài khoản có thể chuyển từ trạng thái New sang trạng thái Active bằng cách kích hoạt nó.
* Tài khoản có thể chuyển từ trạng thái New sang trạng thái Closed bằng cách đóng nó.
* Tài khoản có thể chuyển từ trạng thái Active sang trạng thái Inactive bằng cách vô hiệu hóa nó.
* Tài khoản có thể chuyển từ trạng thái Active sang trạng thái Closed bằng cách đóng nó.
* Tài khoản có thể chuyển từ trạng thái Inactive sang trạng thái Active bằng cách kích hoạt nó.
* Tài khoản có thể chuyển từ trạng thái Inactive sang trạng thái Closed bằng cách đóng nó.
* Bây giờ chúng ta đã đi đến đâu đó rồi. Hãy mở rộng điều này hơn nữa để bao gồm các trạng thái khác nữa.

> Prompt: please include expired, frozen and other relevant states as well
>
> ChatGPT: Sure, here is an example of how a state diagram for a wealth management system’s account management component could be represented in Mermaid including additional states such as Expired, Frozen, etc:
>
> Description: This diagram shows the different states of an account and the possible transitions between them.
>
> The initial state is \[*] which denotes the start state. The account can transition from New state to Active state by activating it. The account can transition from New state to Closed state by closing it. The account can transition from Active state to Inactive state by deactivating it. The account can transition from Active state to Frozen state by freezing it. The account can transition from Active state to Closed state by closing it. The account can transition from Inactive state to Active state by activating it. The account can transition from Inactive state to Frozen state by freezing it. The account can transition from Inactive state to Closed state by closing it. The account can transition from Frozen state to Active state by unfreezing it. The account can transition from Frozen state to Closed state by closing it. The account can transition from Closed state to Expired state if the account is expired.

![](https://oss.congdongchatgpt.com/congdongchatgpt/2023-03-13/1678701883-272046-extended-state-diagram.webp)

And Diagrammatic Representation

![](https://oss.congdongchatgpt.com/congdongchatgpt/2023-03-13/1678701900-653346-1-flma-die-vqldvmlo8jtgq.webp)

Điều này thật tuyệt vời. Thật ấn tượng về những gì có thể đạt được với ChatGPT và Mermaid.

Nguồn: <https://congdongchatgpt.com/d/57-su-dung-chatgpt-de-xay-dung-so-do-he-thong>