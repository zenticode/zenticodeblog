---
title: Blockchain layers là gì và các giải pháp mở rộng?
date: 2023-03-17 21:36
tags:
  - Blockchain
description: >+
  Với những ai chưa biết thì các bài viết của mình sẽ xoay quanh chủ đề liên
  quan đến các lĩnh vực Backend, Blockchain cũng như DevOps, hi vọng thông qua
  việc chia sẻ kiến thức đến cộng đồng mình cũng sẽ nhận về các ý kiến đóng góp
  để cải thiện kỹ năng và nâng cao trình độ trong lĩnh vực chuyên môn, cũng như
  là các bài viết tâm sự chuyện nghề chuyện đời dưới góc nhìn cá nhân.
---
Chào mọi người đã lâu không gặp, lần trước mình đã hứa lên bài về Blockchain tuy nhiên đến hôm nay mình mới có dịp ngồi lại và viết cho mọi người bài viết này nhằm giúp mọi người có cái nhìn cốt lõi về các nền tảng Blockchain hiện tại cũng như các giải pháp scaling. Với những ai chưa biết thì các bài viết của mình sẽ xoay quanh chủ đề liên quan đến các lĩnh vực **Backend, Blockchain** cũng như **DevOps**, hi vọng thông qua việc chia sẻ kiến thức đến cộng đồng mình cũng sẽ nhận về các ý kiến đóng góp để cải thiện kỹ năng và nâng cao trình độ trong lĩnh vực chuyên môn, cũng như là các bài viết tâm sự chuyện nghề chuyện đời dưới góc nhìn cá nhân.

## Web3.0 và giới hạn

Thời gian qua, mọi người sẽ nghe nhiều về khái niệm Web3.0, được cho là cuộc cách mạng tiếp theo trong tiến trình phát triển của Internet. Web3.0 dựa trên nền tảng công nghệ Blockchain và các hệ thống phân tán giúp người dùng có toàn quyền với các dữ liệu cá nhân như danh tính và tài sản, cũng như là giảm sự tập trung hoá quyền lực vào các trung tâm dữ liệu một cách an toàn và minh bạch.

Tuy nhiên, việc triển khai Web 3.0 hiện nay đang gặp nhiều thách thức, nhiều vấn đề khả năng mở rộng, hiệu suất cũng như trải nghiệm người dùng tương đối phức tạp gây khó khăn cho đa số người dùng thông thường. Vì thế để Web3.0 có thể triển khai và áp dụng rộng rãi còn là một quá trình dài cải thiện các vấn đề ở các cơ sở hạ tầng mạng Blockchain hiện tại khó có thể đáp ứng.

## Bộ ba bất khả thi trong Blockchain

Thời gian qua, các nền tảng Blockchain khác nhau mọc lên như nấm sau mưa từ Layer0 đến Layer2 nhằm giải quyết các vấn đề khác nhau. Tuy nhiên, theo mình nhìn vào bản chất mọi nền tảng Blockchain hiện nay đều tồn tại 3 khía cạnh của **"Bộ ba đỉnh tam giác bất khả thi"** mà ở đó tuỳ vào tiêu chí đặc thù mà phải có sự lựa chọn và đánh đổi phù hợp giữa 2 trong 3 yếu tố: **Tính phân tán - Tính bảo mật - Tính mở rộng**.

![](https://images.viblo.asia/905fa6ec-2f34-4dc3-b800-904627377b51.png)

Nói một cách dễ hiểu thì mọi người hãy thử hình dung trong một tổ chức quản trị cụ thể như một công ty, một đất nước khi tính phân tán cao trong việc có nhiều ý kiến trong ban lãnh đạo thì đồng thời sẽ làm giảm tốc độ ra quyết định của tổ chức đó, đổi lại tính an toàn và minh bạch sẽ cao hơn. Việc một đất nước như Mỹ cần ra một quyết sách sẽ cần có sự thảo luận và thống nhất lâu hơn việc Trung Quốc ra một chính sách cũng bởi tính tập trung quyền lực này.

Trong bài viết này mình sẽ đi sâu vào phân tích **tính mở rộng** theo mình là thứ lớn nhất đang ngăn cản Blockchain trở nên rộng rãi và dễ dàng tiếp cận đến mọi người và cách mà các hệ sinh thái Blockchain hiện tại đang giải quyết.

## Tính mở rộng trên các layer Blockchain

Khi nói về tính mở rộng chúng ta sẽ thường tiếp cận theo hai hướng: mở rộng theo chiều dọc và mở rộng theo chiều ngang. Các nền tảng Blockchain cũng vậy, việc mở rộng có thể được apply ở tất cả các tầng khác nhau tuỳ thuộc vào hệ sinh thái từ đó sản sinh ra các Blockchain layer0 cho đến Blockchain layer2.

`Chúng ta sẽ đi tìm hiểu vậy layer là gì và cơ sở nào để phân biệt một nền tảng Blockchain thuộc một lớp nào đó?`

**\- Layer 0: Hardware, network and data structure**

Với các nền tảng Blokchain build trên lớp layer0, nhà phát triển sẽ tập trung vào các phần cốt lõi như tinh chỉnh phần cứng, giao thức truyền tải mạng cũng như cấu trúc lại dữ liệu của một mạng Blockchain. Các đại diện thường thấy sẽ bao gồm: Cardano, Cosmos, Polkadot,..

**\- Layer 1: Consensus**

Với các hệ sinh thái Blockchain được build ở tầng này, nhà phát triển sẽ tập trung đánh đổi tính mở rộng dựa vào giao thức đồng thuận luật phân tán. Các đại diện đã quá nổi tiếng như: Bitcoin (Proof of Work), Ethereum (Proof of Stake) hay Solana (Proof of History)..

**\- Layer 2: Scaling based on L1**

Thời gian gần đây, các giải pháp Layer2 nổi lên rầm rộ như một cách tiếp cận giúp mở rộng giao dịch và giảm chi phí. Đặc điểm của các hệ sinh thái này được build dựa trên Layer1, với các cách tiếp cận khác nhau: State channels, Off-chain, Side-chain, Rollups, Optimistic... đã quá nổi với các cái tên như: Polygon, Optimistic, ZKSync,...

**\- Layer 3: D-App**

Và còn một tầng nữa mà mọi người thường hay bỏ qua tuy nhiên vẫn là nơi có thể apply các biện pháp mở rộng một cách hữu hiệu đó là D-Apps. Nơi ta có thể tinh gọn hoặc gom nhóm các transaction, các serivces chạy và xử lý nhằm đáp ứng tính mở rộng của ứng dụng cũng như cải thiện trải nghiệm người dùng được mượt mà hơn.

## Các giải pháp giải quyết tính mở rộng

Sau khi đã phân biệt được các layer blockchain và phân chia các hệ sinh thái tương ứng chúng ta sẽ bắt đầu đi sâu vào phân tích cách mà các mạng Blockchain hiện nay triển khai để giải quyết bài toán mở rộng.

### Layer0

Điểm chung của các hệ sinh thái ở tầng này đều dựa vào phương pháp **"chia để trị"** nhằm giải quyết bài toán. Khi đó các transaction sẽ được xử lý song song nhằm tăng thông lượng TPS (transaction per second).

#### **Cardano**

Quả công nghệ phát triển lâu nhất lịch sử ngành Blockchain. Cardano tiếp cận theo hướng chia để trị bằng cách xây dựng mạng Ouroboros (PoS) trong đó chia ra nhiều epoch và slot sharding. Tuy nhiên đến thời điểm hiện tại dường như vẫn chưa có nhiều kết quả rõ rệt.

![image.png](https://images.viblo.asia/4f0c28d4-855f-4b55-9c79-50390b8df76d.png)

#### **Cosmos**

Đối với hệ sinh thái Cosmos, cốt lõi giải pháp bao gồm việc tách biệt giữa DApp (Cosmos SDK) và luật đồng thuận (Tendermint Core BFT) cũng như hạ tầng mạng network được liên kết thông qua cầu nối gọi là **ABIC** dựa trên giao thức Inter Blockchain Communication (IBC).

Nói một cách dễ hiểu chúng ta sẽ có:

`Application (Any languages) <-- ABCI (Application Blockchain Interface)--> Networking + Consensus (PoS)`

Ngoài ra hệ sinh thái Cosmos còn cung cấp các giải pháp xuyên chuỗi như:

Child-chain: Zones

Bridge: Hub - Peg Hub (Bitcoint, Ethereum)

![image.png](https://images.viblo.asia/33b50d8e-ec11-4a11-af50-495d06cdedad.png)

#### **Polkadot**

Đến với Polkadot, giải pháp này tiếp cận theo hướng xây dựng 2 loại chuỗi một để quản trị và một để chạy ứng dụng:

* Relay chain: Minimize feature -> Governance
* Para chains (stake DOT) + Parathread: DApp

![image.png](https://images.viblo.asia/42b92c31-6dc9-4491-96dc-05b357705f1f.png)

### Layer1

#### **Ethereum**

Ở Layer1, chúng ta sẽ đi sâu phân tích anh cả Ethereum và các giải pháp scaling on-chain hiện nay nhằm tiến tới Ethereum 2.0. Nói một cách dễ hiểu thì Ethereum 2.0 cũng sẽ tiếp cận theo phương pháp "chia để trị". Khi đó Ethereum sẽ nâng lên Ethereum 2.0, chuyển dần luật đồng thuận PoW sang PoS đồng thời tiến hành Sharding dựa vào Zero Knowledge Proofs.

![image.png](https://images.viblo.asia/3b02738d-15fa-45c1-8c2b-5e21f676959c.png)

Tiến trình hiện tại Ethereum đã hiện thực thành công **The Merge** trong việc merge chain Ethereum mainnet và Beacoin chain nhằm từng bước chuyển sang luật đồng thuận PoS. Các phiên bản upgrade tiếp theo là các bước chuẩn bị nhằm chuẩn bị cho quá trình Sharding trong tương lai.

Ngoài ra, các hệ sinh thái khác ở lớp Layer1 cũng cần phải chú ý bao gồm Solana và Near. Chúng ta cũng sẽ mổ xẻ 2 nền tảng này liệu đã thực sự là một Blockchain tuyệt vời để giải quyết bài toán mở rộng?

#### **Solana**

Với Solana, nền tảng này đưa ra khái niệm gọi là "luật đồng thuận" PoH (bằng chứng lịch sử). Theo mình PoH đã bị centralized thắt nút tại một điểm và bản chất vẫn cần sự kết hợp PoS. Nói một cách dễ hiểu Solana đã giải quyết bài toán timestamp tồn tại trên Ethereum:

ETH: Timestamp của Block sẽ được lấy dựa theo unix time của mỗi Miner, sau đó broadcast lên toàn mạng.

Leader: Solana giải quyết timestamp bằng 1 điểm duy nhất tập trung sau đó auto gắn dấu thời gian này vào cho các block. Từ đó giảm thiểu độ trễ nhưng hay xảy ra tình trạng tắc nghẽn dừng hoạt động.

Ở đây Solana đã đánh đổi tính Decentralize để lấy Performance do đó dường như vẫn không thể phá bỏ bộ ba tam giác bất khả thi mà mình đã đề cập bên trên.

![image.png](https://images.viblo.asia/99475ad9-7e57-423f-9383-88b0022ae39f.png)

Mặt khác, chúng ta cũng có thế quan tâm đến số lượng Validator hiện tại của Solana là 1800 cùng với con số TPS đạt ngưỡng 4000. Và một cách suy luận logic chúng ta có thể dễ dàng thấy được sẽ luôn có một tỉ lệ nghịch giữa số lượng Validator >< TPS khi mà việc đẩy cao TPS đồng thời sẽ phải giảm đi số lượng Validators (dữ liệu lấy từ thời điểm tháng 8 - 2022).

#### **Near**

Với hệ sinh thái Near được build trên ngôn ngữ lập trình RUST và giải pháp tiến hành theo hướng scale dọc kết hợp sharding (night shard) nhằm đạt target 100K TPS. Tuy nhiên, ta sẽ dễ dàng nhìn thấy khi việc giảm kích thước khi scale dọc sẽ dễ dàng gây ra tình trạng tấn công 51%.

Ngoài ra Near còn cung cấp theo các cầu nối Rainbow Bridge và một giải pháp Aurora Layer2 (EVM).

![](https://images.viblo.asia/65d854ff-7f32-4261-9dce-6f77ff9b3abe.png)

#### **APTOS/SUI**:

Các giải pháp Layer1 khác được phát triển từ đội ngũ Google trong thời gian gần đây như Aptos hay SUI hiện thực tính mở rộng dựa trên các nguyên lý cốt lõi sau:

* Block-STM Technology: Sharding + Parallel
* Move Programming Language
* BFT Consensus Protocol

### Layer2

Thời gian gần đây, các giải pháp Blockchain Layer2 dường như bùng nổ với các cách tiếp cận khác nhau có thể kể đến như:

* Rollups
* State channels
* Sidechains
* Plasma
* Validium

Trong khuôn khổ bài viết này mình không thể phân tích sâu thêm nên xin phép hẹn lại mọi người trong một bài viết khác không xa.

## Lời kết

Tóm lại thì theo mình dường như không có một nền tảng Blockchain nào là hoàn hảo để có thể giải quyết hoàn toàn đồng thời 3 yếu tố trong tam giác bất khả thi. Mỗi nền tảng sẽ có cách giải quyết khác nhau và chúng ta tiếp cận dựa theo nhu cầu thực sự phụ hợp với yêu cầu tại từng thời điểm. Việc cách mạng hoá nền Internet hay Web3.0 theo mình là một hướng đi đúng đắn tuy nhiên sẽ còn tốn quãng đường phát triển khá dài và xa hơn nữa để hoàn thiện về mặt hạ tầng và kĩ thuật trong tương lai.

Về tương lai gần mình tin là các giải pháp khả thi nhất sẽ là Layer2 và tương lai xa vẫn sẽ là Ethereum 2.0 trong bối cảnh dường như các giải pháp Layer0 hay Layer1 khó có thể đạt được các thành quả rõ rệt mong muốn.

Mặt khác, mình xin nhắc lại các kiến thức nhỏ nhoi mình tổng hợp và tích luỹ trong thời gian dài làm việc sẽ không thể tránh khỏi sai sót cũng như các nhận định chủ quan một chiều. Mọi người có thể góp ý và đưa ra các nhận định cá nhân mang tính xây dựng trong phần bình luận nhằm giúp chúng ta bổ sung và nâng cao kiến thức hơn nữa. Nếu cảm thấy bài viết hữu ích xin để lại một upvote để ủng hộ tinh thần cho mình ra thêm các bài viết mới. Happy Coding!

N﻿guồn: [Viblo](https://viblo.asia/p/blockchain-layers-la-gi-va-cac-giai-phap-mo-rong-W13VMgydJY7)