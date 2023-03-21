---
title: Sử dụng useEffect đúng cách
date: 2023-03-21 16:50
tags:
  - ReactJs
description: Khi sử dụng thư viện ReactJS với Function component, các bạn đã quá
  quen với việc sử dụng useEffect để gọi API, lấy dữ liệu và sau đó hiển thị dữ
  liệu đó trên DOM. Vậy cách hoạt động chính xác của hook useEffect là gì? Cùng
  tìm hiểm với mình nhé!👌👌👌
---
Khi sử dụng thư viện ReactJS với Function component, các bạn đã quá quen với việc sử dụng useEffect để gọi API, lấy dữ liệu và sau đó hiển thị dữ liệu đó trên DOM. Vậy cách hoạt động chính xác của [hook useEffect](https://vi.reactjs.org/docs/hooks-overview.html#:~:text=Hooks%20l%C3%A0%20c%C3%A1c%20h%C3%A0m%20m%C3%A0,d%E1%BB%A5ng%20React%20kh%C3%B4ng%20c%E1%BA%A7n%20classes.) là gì? Cùng tìm hiểm với mình nhé!👌👌👌

## 1. [Hook](https://legacy.reactjs.org/docs/hooks-reference.html#gatsby-focus-wrapper) là gì? Tại sao phải cần hook?

Hooks mới được thêm ở phiên bản React 16.8. Cho phép bạn sử dụng state và các chức năng khác của React mà không cần tạo class. Đối với **Class component,** bạn có các hàm tương tác với state được kế thừa ***(extend***) từ Reac nhưng khi sử dụng **Functional component** bạn không có các hàm này để tương tác với state của component. Không có state thì không thể cập nhật view của bạn.

```none
// Class component
class Car extends React.Component {

 constructor() {

   super();

   this.state = {color: "red"};// tương tác với state

 }

 render() {

   return <h2>I am a Car!</h2>;

 }

}

//Functional component
import React, { useState } from 'react';

function Example() {
 // Khai báo 1 biến số đếm, gọi là "count"
 const [count, setCount] = useState(0); //Hook useState
  useEffect(()=>{
  //gọi API tại đây
  
  
  },[])
  
  
 return (
   <div>
     <p>Bạn đã bấm {count} lần</p>
     <button onClick={() => setCount(count + 1)}>
       Bấm vào tôi
     </button>
   </div>
 );
}

```

## 2. Tương ứng hook [useEffect](https://legacy.reactjs.org/docs/hooks-effect.html) và các hàm trong lifecycle của component

Khi lập trình với Class compoent, các bạn đã quen với các hàm trong lifecycle của component:

* componentDidMount()
* componentDidUpdate()
* componentWillUnmount() ![react lifecycle](https://images.viblo.asia/225c78f7-594c-4b6c-884e-fa3da2bd9b25.png)

Tương ứng với các hàm này hook useEffect sẽ được viết như sau:

1. ComponentDidMount()

```none
useEffect(() => {
    // Bạn viết code xử lý logic tại đây
}, []);

```

2. ComponentDidUpdate()

```none
useEffect(() => {
    // Bạn viết code xử lý logic tại đây
});

```

3. ComponentWillUnMount()

```none
useEffect(() => {  
    // hàm được trả về sẽ được gọi khi component unmount 
    return () => {
      // Bạn viết code xử lý logic tại đây khi component unmount.
    }
}, [])

```

## 3. Clean up trong hook useEffect

Tại sao bạn cần Clean up và Clean up là gì? Như tên của nó, Clean up giúp bạn dọn dẹp code, tránh làm lãng phí tài nguyên như RAM trong ứng dụng của bạn. Giống kiểu bạn xóa vùng nhớ của biến trong C++ khi không sử dụng đó. Ví dụ trường hợp sau: Bạn dùng 1 hàm setInterval trong hook useEffect như sau: hàm sẽ log giá trị secondsPassed mỗi 1s

```none
useEffect(()=>{
    let secondsPassed=1;
    setInterval(()=>{
    console.log(secondsPassed++)
    },1000)
},[])

```

Code này gặp 1 vấn đề: khi component của bạn bị unmounts thì hàm setInterval() vẫn được tiếp tục chạy. Nghĩa là trình duyệt vẫn log giá trị đó. Hook useEffect cho bạn 1 phương án để khắc phục vấn đề này. Sử dụng **hàm return()** trong hook useEffect như sau:

```none
useEffect(()=>{
    let secondsPassed=1;
   const id= setInterval(()=>{
    console.log(secondsPassed++)
    },1000);
    return()=> clearInterval(id)
    
},[])

```

Hàm return() sẽ chạy trước khi component bị unmount, vì thế Interval sẽ bị clear sau đó compoent mới bị unmount. Đây là 1 ví dụ điển hình của clean up trong hook useEffect. Nó còn sử dụng nhiều trường hợp khác nữa như khi api trong useEffect đang chạy thì component bị unmount.

## 4. Kết luận

Hãy tìm hiểu thật kỹ trước khi sử dụng bất cứ chức năng gì bạn nhé👏👏 **Đọc kỹ hướng dẫn sử dụng trước khi dùng**