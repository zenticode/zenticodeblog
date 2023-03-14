---
title: Everything in Ruby is an object?
date: 2023-03-14 22:54
tags:
  - Ruby
description: '"Everything in Ruby is an object" là một lời tuyên bố mà hầu như
  Rubiers nào cũng đã từng nghe qua. Cơ mà thuyết tương đối của Einstein bảo
  rằng: Chẳng có gì là tuyệt đối!'
---
"Everything in Ruby is an object" là một lời tuyên bố mà hầu như Rubiers nào cũng đã từng nghe qua. Cơ mà thuyết tương đối của Einstein bảo rằng: Chẳng có gì là tuyệt đối!

Hmmm, vậy thì chúng ta sẽ xem thử, liệu có gì trong Ruby không phải là object không nhé?

## 1. Block

`Block` là một khối các câu lệnh được thực hiện tuần tự được đặt trong `{}` hoặc `do end`. Block không phải một object, và vì thế, nó không hề có tên gọi. Nó cũng không thể gán cho bất cứ variables nào. Block không thể tái sử dụng và cũng không thể lưu trữ. `Block` được truyền vào một method và được thực thi tại từ khoá `yeild`

```none
   def say_something_to_xuantai
       yield "Xuan Tai"
   end
   
   say_something_to_xuantai { |welcome| "Welcome to Ruby, #{welcome}" }

```

## 2. Conditional

Conditional giúp chúng ta có thể thực hiện các câu lệnh theo điều kiện mong muốn. Trong Ruby thì có 2 conditional thường dùng đó là `If - else` và `case - when`. Vậy 2 mục này có gì khác nhau? Khi nào thì nên dùng `if - else`, khi nào nên dùng `case - when`?

### a. if - else

If - else là kiểu conditional được xét theo tuần từ tự trên xuống dưới, và nó chỉ thực các câu lệnh nằm trong nhánh điều kiện thoả mãn. Với `if - else`, chúng ta có thể xét nhiều điều kiện khác nhau hoặc nhiều tổ hợp điều kiện, và các điều kiện nằm phía trước sẽ được ưu tiên đánh giá trước.

```none
def say_the_number(a)
    if a > 2
      puts "greater than 2"
    elsif a < 5
     puts "less than 5"
    elsif a == 4
     puts "4"
    else
     puts "It's a number"
    end
end

say_the_number(1) # less than 5
say_the_number(3) # greater than 2
say_the_number(4) # greater than 2

```

Theo ví dụ trên, rõ ràng khi truyền 3 và 4 vào, nó đều thoả mãn điều kiện `< 5`. Tuy nhiên trước đó nó đã thoả mãn điều kiện `> 2` rồi nên nó sẽ không xét tiếp các conditions bên dưới.

### b. case - when

`case - when` cũng là một conditional statement. Tuy nhiên, statement này chỉ có thể so sánh với 1 variable và mỗi biểu thức là một giá trị duy nhất. Các giá trị được so sánh trong biểu thức có thể là 1 number, một string, một symbol hoặc thậm chí là một array

```none
ex1:

    case a
    when 0
      puts "It's a number"
    when "x"
     puts "It's a string"
    else
     puts "It's nothing"
    end

ex2:

    case a
    when *(1..10)
      puts "Less than 11"
    when *(11..20)
     puts "Less than 21"
    else
     puts "It's nothing"
    end

```

### c. Khi nào thì dùng `If - else`, khi nào thì dùng `when - case`?

`if - else` có thể sử dụng cho mọi trường hợp. Tuy nhiên, khi biểu thức điều kiện là các biểu thức đơn và có các giá trị độc lập, không chồng chéo lên nhau thì chúng ta nên sử dụng `when - case` sẽ giúp cho việc viết code trở nên gọn gàng và dễ hiểu hơn.

### 3. Methods

Các methods có thể hiểu đơn giản là các hành động của một object, và vì thế nên nó không phải là object rồi 😄.

### 4. Operators

Operators là tập hợp các toán tử được dùng để thực hiện với các object. Trên thực tế, các toán tử này chính là method. Và khi thực hiện phép toán `a + b` thì thực tế `+` chính là method của `a`, và `b` chính là argument. Và vì là method nên chúng ta hoàn toàn có thể override lại các toán tử này.

```none
    a = "Xin chao"
    class << a
      def +(string)
        return "#{self} Xuan Tai #{string}"
      end
    end
=> a + "dep trai" # Xin chao Xuan Tai dep trai

```

Như ví dụ trên, em đã override lại toán tử `+` của riêng object a(class String). Và giờ kết quả của phép `a + ...` sẽ luôn kèm theo chuỗi `Xuan Tai` 😄

## Tổng kết:

Qua đây, chúng ta đã có thể biết rằng, trong Ruby không phải tất cả đều là object. Mà chính xác hơn là: Trong Ruby, hầu như mọi thứ đều là object 😄

Cảm ơn các độc giả, nếu bài viết của em có điểm nào chưa đúng thì các bác cứ nhiệt tình mắng vốn nhé. Em sẽ luôn hạ mình lắng nghe để có cơ hội trau dồi thêm kiến thức. Em xin cảm ơn 😄

N﻿guồn: [Viblo](https://viblo.asia/p/everything-in-ruby-is-an-object-W13VMgr8JY7)