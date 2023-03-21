---
title: Docker và các kiến thức căn bản
date: 2023-03-21 23:46
description: 'Nếu bạn đã từng gặp trường hợp khi team code chung dự án với nhau
  hoặc làm bài tập nhóm trên trường mà mỗi người trong team lại dùng hệ điều
  hành khác nhau, phần của người này code xong chạy ổn nhưng sang máy người khác
  "đứt" có thể là do 2 máy có các môi trường khác nhau, do các thư viện không
  trùng phiên bản với nhau... '
---
## Lý thuyết

### Đặt vấn đề

Nếu bạn đã từng gặp trường hợp khi team code chung dự án với nhau hoặc làm bài tập nhóm trên trường mà mỗi người trong team lại dùng hệ điều hành khác nhau, phần của người này code xong chạy ổn nhưng sang máy người khác "đứt" có thể là do 2 máy có các môi trường khác nhau, do các thư viện không trùng phiên bản với nhau... những lúc như thế sẽ phải tự cài thêm thư viện hoặc chỉnh sửa môi trường sao cho có thể chạy được dự án. Vậy nên bây giờ cần sử dụng 1 công cụ mà giúp các lập trình viên trong team luôn có môi trường đồng nhất, tránh các lỗi vặt có thể xảy ra. Vậy bài viết này sẽ giúp các bạn tiếp cận với Docker

### Virtualization và Containerization

Trước khi đi vào Docker thì chúng ta hãy nói đến công nghệ Virtualization và Containerization\
\
**Virtualization:**

* Virtualization là mức ảo hóa phần cứng trong đó một phần cứng vật lý được phân chia thành nhiều phần cứng ảo để có thể chạy đa hệ điều hành và các ứng dụng khác nhau đồng thời.
* Nó bao gồm ảo hoá CPU, RAM, ổ đĩa và card mạng. Bằng cách ảo hoá các phần cứng này, nó cho phép nhiều máy ảo chạy trên cùng một máy chủ vật lý mà không ảnh hưởng đến nhau.
* Các máy ảo này hoàn toàn độc lập với nhau, giống như chúng được cài đặt trên các máy chủ riêng biệt.
* Virtualization cần sử dụng tài nguyên phần cứng khá lớn và có thể gây ra sự chậm trễ trong quá trình hoạt động.
* Ví dụ điển hình về các công cụ sử dụng Virtualization như: VMware, VirtualBox, Hyper-V, KVM...

**Containerization:**

* Containerization là mức ảo hóa hệ điều hành, trong đó mỗi container chứa một ứng dụng hoặc một nhóm ứng dụng được đóng gói cùng với các thư viện và các tài nguyên khác cần thiết để chạy ứng dụng đó
* Các container chia sẻ kernel của hệ điều hành vật lý và các thư viện chung với hệ điều hành, vì vậy Containerization tiết kiệm tài nguyên hơn so với Virtualization.
* Ví dụ điển hình về các công cụ sử dụng Containerization như: Docker, Podman, Kubernetes...

**Tóm lại:** Virtualization tạo ra các máy ảo độc lập chạy trên cùng một phần cứng vật lý, còn Containerization tạo ra các container chia sẻ kernel và các thư viện của hệ điều hành vật lý.

![containers-vs-virtual-machines.jpeg](https://images.viblo.asia/75406a2c-cb78-4c25-8a33-8c4296f65430.jpeg)

Hình 1: Mô tả sự khác nhau giữa Virtualization và Containerization



### Docker

#### Khái niệm

Docker là một công cụ đóng gói phần mềm và triển khai ứng dụng trong các container. Các ứng dụng chạy trong các container được gọi là các container Docker. Docker giúp các lập trình viên chỉ cần chạy các container lên mà không cần phải lo về việc cài các thư viện hoặc môi trường, điều này giúp các lập trình viên phát triển ứng dụng 1 cách nhanh chóng, đảm bảo tính nhất quán giữa môi trường phát triển và môi trường triển khai.\
\
**Ví dụ:** Có 2 lập trình viên đang làm việc trên một dự án sử dụng framework NestJS và yêu cầu sử dụng NodeJS. Bình thường thì cả 2 lập trình viên cần phải cài cắm các thư viện cần thiết như Nodejs, npm... . Nhưng nếu bạn sử dụng MacOS và cài phiên bản Node 14.x, còn người kia dùng Windows và cài phiên bản Node 12.x, thì trường hợp này sẽ khá dễ phát sinh xung đột vì môi trường phát triển không đồng nhất. Trong trường hợp này, để tránh xung đột giữa các lập trình viên thì Docker cung cấp 1 môi trường đồng nhất giữa cả 2 bằng cách sử dụng image node:14.x, image này đã cung cấp đủ các công cụ và thư viện cần thiết để phát triển xây dựng và triển khai ứng dụng Node.js ( nó giống như bạn cài Node trên máy tính cá nhân của bạn ). Chính vì thế mà khi 1 người khác muốn vào phát triển ứng dụng cùng, thì họ chỉ cần chạy container lên mà không cần phải nghĩ về việc cài môi trường và các thư viện đi kèm.

#### Các thành phần cơ bản

* Docker daemon: Là một tiến trình nền chạy trên một máy tính Docker host ( máy cài Docker ), và quản lý các hoạt động Docker như tạo và quản lý các container, images, networks và volumes.
* Docker client: Là một ứng dụng dòng lệnh hoặc giao diện người dùng đồ họa (GUI) để tương tác với Docker daemon và thực hiện các hoạt động Docker. Docker client sử dụng Docker API để giao tiếp với Docker daemon.
* Docker images: Là một gói đóng gói của một ứng dụng và các tài nguyên cần thiết để chạy ứng dụng đó trong một container. Một image có thể được tạo từ một Dockerfile hoặc tải từ một kho chứa image trên internet như Docker Hub.
* Docker container: Là một môi trường đóng gói độc lập, chứa tất cả các thành phần cần thiết để chạy một ứng dụng trong một môi trường cô lập, container được tạo ra từ image sau khi đã đóng gói
* Docker network: cho phép các container tương tác với nhau và với các dịch vụ khác. Một Docker network được tạo ra để tạo một mạng ảo cho các container chạy trên cùng một máy Docker host
* Docker volume: Cho phép các container lưu trữ và truy cập dữ liệu được sử dụng bởi các ứng dụng. Volume giúp dữ liệu được bảo vệ và giữ cho đồng bộ giữa các container.

![image.png](https://images.viblo.asia/41182e80-c34b-4db2-b3c0-a8f82101809e.png)

Hình 2: Kiến trúc của Docker



**Bên cạnh đó:**

* Docker registry: Là một kho chứa image để lưu trữ các image được tạo bởi người dùng Docker hoặc bởi các nhà cung cấp phần mềm. Docker Hub là một ví dụ về Docker registry công cộng, trong khi các tổ chức cũng có thể triển khai một Docker registry riêng tư. Đây là nơi mà chúng ta tải lên các image sau khi đã build ( khá giống việc lưu trữ code trên Github )
* Dockerfile: Là một tệp cấu hình định nghĩa các bước để xây dựng một image Docker. Dockerfile chứa các chỉ thị để tải các phần mềm, công cụ cần thiết, cài đặt các gói phụ thuộc, cấu hình ứng dụng ...
* Docker compose: Là công cụ được sử dụng để quản lý, triển khai và tự động hóa việc chạy nhiều container cùng một lúc

## Thực hành

### Cài đặt

Các bạn có thể tải Docker [ở đây](https://www.docker.com/products/docker-desktop/) và sau đó cài đặt theo hướng dẫn ở đây:

* MacOs: <https://docs.docker.com/desktop/install/mac-install/>
* Windows: <https://docs.docker.com/desktop/install/windows-install/>

Còn với họ Unix, các bạn có thể download [tại đây](https://docs.docker.com/desktop/install/linux-install/) và sau đó làm theo hướng dẫn:

* Arch: <https://docs.docker.com/desktop/install/archlinux/>
* Debian: <https://docs.docker.com/desktop/install/debian/>
* Fedora: <https://docs.docker.com/desktop/install/fedora/>
* Ubuntu: <https://docs.docker.com/desktop/install/ubuntu/>

Hoặc sử dụng command line:

* Ubuntu 20.04: <https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-20-04>
* Debian 10: <https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-debian-10>

### Các lệnh cơ bản

Đây là 1 số câu lệnh phổ biến và hay sử dụng trong quá trình sử dụng Docker:

* `docker run`: Lệnh để chạy một container từ một image.
* `docker pull`: Lệnh để tải một image từ Docker Registry về máy tính.
* `docker push`: Lệnh để đẩy một image lên Docker Registry.
* `docker build`: Lệnh để tạo một image từ Dockerfile.
* `docker images`: Lệnh để hiển thị danh sách các image có sẵn trong Docker.
* `docker ps`: Lệnh để hiển thị danh sách các container đang chạy.
* `docker stop`: Lệnh để dừng một container đang chạy.
* `docker rm`: Lệnh để xóa một container đã dừng hoặc bị lỗi.
* `docker rmi`: Lệnh để xóa một image.
* `docker exec`: Lệnh để thực thi một lệnh trong một container đang chạy.

### Chạy ứng dụng Docker đầu tiên

Lý thuyết bên trên là đủ rồi, chúng ta bắt tay vào thực hành chạy lên ứng dụng Docker đầu tiên của chúng ta thôi\
\
Mục đích của bài thực hành này là:

* Chạy thành công 1 container ( sử dụng container mà mình đã push lên Docker Hub, và bên trong chứa code backend sử dụng NestJS )
* Call đến API `/user` để lấy ra thông tin của các users
* Đi vào bên trong container để xem trong đó có gì

Chúng ta hãy mở terminal ( command line ) và paste câu lệnh này vào:

```none
docker run --name nestjs-basic -p 3000:3000 -d tuanops/nestjs-basic:latest

```

Các tham số ở đây:

* **\--name**: đặt tên cho container là **nestjs-basic**
* **\-p:** bên trong container chạy trên cổng 3000, vì vậy cần map cổng này ra cổng 3000 của host bằng tham số -p.
* **\-d:** cho container chạy ngầm (detach mode) và trả về ID của container.
* **tuanops/nestjs-basic:latest:** tên image để chạy container ( Nếu ở máy host đã có image này thì docker sẽ chạy luôn image đó để tạo thành container, còn nếu không thì docker sẽ lên Docker Hub để tìm image tương ứng )

Sau khi khởi tạo thành công thì chúng ta dùng lệnh `docker ps` để kiểm tra các container đang chạy\
![image.png](https://images.viblo.asia/fb5a823a-95a3-4415-b61d-84377fc7381d.png)

Hình 3: Chạy container đầu tiên



Vậy là chúng ta đã khởi tạo thành công container với tên `nestjs-basic`, giờ chúng ta sẽ thử call đến API `/user` bằng lệnh:

```none
curl http://localhost:3000/user

```

Và đây là kết quả:![image.png](https://images.viblo.asia/c7dc104d-c3be-40ed-988c-7fe20511e274.png)

Hình 4: Kết quả của API user



Vây là chúng ta đã call thành công api `/user` từ bên ngoài vào bên trong container rồi\
Tiếp theo thì chúng ta sẽ đi vào bên trong container xem bên trong có gì nào, chúng ta dùng lệnh:

```none
docker exec -it 22d801b5bf39 /bin/sh

```

Ở đây:

* `docker exec` là lệnh để thực thi một command trong container đang chạy.
* `-it` được sử dụng để tạo một interactive terminal shell sau khi truy cập vào container.
* `22d801b5bf39` là container ID của container cần truy cập.
* `/bin/sh` là command cần thực thi trong container đó. Ở đây, chúng ta sử dụng shell (/bin/sh) để thực thi các lệnh trong container.

![image.png](https://images.viblo.asia/bc276718-b277-4ed1-a775-ce82e324a6be.png)

Hình 5: Đi vào container đã khởi tạo



Trong thư mục `nest` này chứa source code mà chúng ta đã build image `tuanops/nestjs-basic`

### Build ứng dụng Docker đầu tiên

Image trên mình đã build ra và push lên Dockerhub, giờ chúng ta sẽ tạo ra container đó. Đây là [source code](https://github.com/tuantranquang20/nestjs-basic), nếu các bạn muốn build image giống bên trên thì clone code về rồi làm tiếp nha. Sau khi clone về thì thư mục của source code sẽ như sau:\
\
![image.png](https://images.viblo.asia/a30f6727-fece-43c6-b799-338a53e5cc53.png)

Hình 6: Thư mục dự án



Tiếp theo mở file `user.service.ts` thì sẽ thấy API `/user` mình đã gọi hàm `fetchAll` để trả về kết quả như phần thực hành trên\
\
![image.png](https://images.viblo.asia/9fba86a7-0067-44ac-a714-2b1e1b7c00d6.png)

Hình 7: Hàm trả về kết quả của API user



Các bạn có thể mở `Dockerfile` và thấy nội dụng của nó:

```none
FROM node:14-alpine

WORKDIR /nest

COPY package*.json ./
RUN npm install
COPY . .

EXPOSE 3000
CMD ["npm", "run", "start:dev"]

```

Ở đây:

* `FROM node:14-alpine`: Chúng ta sử dụng image này là image cơ sở, nghĩa là ứng dụng của chúng ta chạy trong môi trường Node version 14
* `WORKDIR /nest`: Thiết lập thư mục làm việc cho Docker image là /nest
* `COPY package*.json ./`: Đây là câu lệnh sao chép các tệp package.json và package-lock.json từ máy host vào thư mục làm việc của Docker image (/nest).
* `RUN npm install`: Cài đặt các thư viện phụ thuộc cho ứng dụng
* `COPY . .`: Đây là câu lệnh sao chép tất cả các tệp của ứng dụng từ máy host vào thư mục làm việc của Docker image (/nest).
* `EXPOSE 3000`: Đây là câu lệnh mở cổng 3000 để cho phép ứng dụng được truy cập từ bên ngoài Docker container.
* `CMD ["npm", "run", "start:dev"]`: Đây là câu lệnh chỉ định lệnh sẽ được thực thi khi Docker container bắt đầu chạy. Trong trường hợp này, nó chạy lệnh npm run start:dev, để chạy trong chế độ phát triển.

Trước khi build thì ta sẽ xoá container hiện tại và image mà các bạn đã chạy ở bước trên. Trước tiên dùng lệnh `docker stop` để stop container đang chạy rồi dùng lệnh `docker rm` để xoá container và `docker rmi` để xoá image:\
\
![image.png](https://images.viblo.asia/4383662d-483a-4d1a-93ca-94c2a2c23680.png)\
![image.png](https://images.viblo.asia/71dc259a-789c-4569-9c81-6992fc0de284.png)

Hình 8: Xoá image cũ



Tiếp theo ở thư mục gốc của source code, giờ chúng ta bắt đầu build image đầu tiên bằng lệnh:\
`docker build -t tuanops/nestjs-basic .`\
\
Ở đây tham số:

* **docker build:** lệnh để build image
* **\-t tuanops/nestjs-basic:** đặt tên cho image là `tuanops/nestjs-basic` ( các bạn có thể đặt tên tuỳ theo ý các bạn )
* **.** : là đường dẫn tới Dockerfile, ở đây là đường dẫn hiện tại.

Sau khi đã build xong, dùng lệnh `docker images` để kiểm tra các image đã sinh ra:\
\
![image.png](https://images.viblo.asia/304c5bdb-864e-418f-8884-a9513612a7f5.png)

Hình 9: Kiểm tra image đã build



Sau đó thì các bạn quay lại bài thực hành trên để có thể tạo container bằng image các bạn đã build ra

### Push image Docker đầu tiên lên Docker Hub

Trước tiên nếu các bạn chưa có account thì vào trang chủ của [Docker Hub](https://hub.docker.com/) để tạo tài khoản Trước khi muốn push image của chúng ta lên Docker Hub thì chúng ta phải đăng nhập Docker trên máy host của chúng ta. Chúng ta vào phần [Security](https://hub.docker.com/settings/security) rồi sau đó chọn `New access token`, sau khi đặt tên cho Token thì sẽ hiển thị lệnh và password để login:

![Screen Shot 2023-03-20 at 17.45.10.png](https://images.viblo.asia/4172bf2d-2958-42a0-9211-6c024c6311d6.png)

Hình 10: Generate token để đăng nhập Docker trên máy host



Các bạn chỉ cần copy đoạn `docker login -u` và password vào terminal để đăng nhập trên máy host là đăng nhập thành công rồi!\
\
![image.png](https://images.viblo.asia/df2310a4-7f67-4e34-b46d-c3b485cd9a21.png)

Hình 11: Đăng nhập Docker trên máy host



Sau khi login thành công thì việc còn lại rất đơn giản, chỉ cần chạy lệnh: `docker push` là được:\
\
![image.png](https://images.viblo.asia/2f065dd3-4839-41ad-904d-9fd636f98f40.png)

Hình 12: Push image lên Docker Hub



Sau đó chúng ta lên Docker Hub để kiểm tra image của chúng ta\
\
![image.png](https://images.viblo.asia/0c743438-9f86-41c6-957c-e73f4c28b80d.png)

Hình 13: Image đã push thành công lên Docker Hub



Vậy là chúng ta đã push image lên DockerHub thành công rồi, giờ thì nếu ai đó muốn sử dụng image của bạn thì họ chỉ cần pull về và chạy là xong.

### Code ứng dụng và chạy trực tiếp bằng Docker

Với những kiến thức bên trên, thì bạn chỉ có thể chạy container đó lên, và kể cả khi bạn có sửa code ở bên ngoài máy host, khi save lại thì bên trong container vẫn không thay đổi gì. Để có thể "hot reload", thì Docker hỗ trợ việc ánh xạ thư mục vào container. Ở đây mình sẽ ánh xạ thư mục code của mình vào bên trong container, điều này có nghĩa là bạn dùng luôn môi trường container mà bên ngoài máy host bạn không cần phải cài cắm gì\
Trước khi thực hành thì các bạn nhớ xoá container đi nhé.\
Đứng ở thư mục gốc của source code, các bạn chạy lệnh:

```none
docker run --name nestjs-basic -p 3000:3000 -v $(pwd):/nest tuanops/nestjs-basic

```

\
Tham số:

* **\-v**: ánh xạ thư mục vào trong container, cụ thể ánh xạ thư mục gốc đang đứng ( `$(pwd)`) vào thư mục `nest` bên trong container ( thư mục đó được định nghĩa trong Dockerfile khi định nghĩa WORKDIR )
* **tuanops/nestjs-basic**: là image mình đã build ra
* **\--name**: đặt tên cho container là **nestjs-basic**
* **\-p:** ánh xạ cổng 3000

![image.png](https://images.viblo.asia/9e318275-25de-4a7f-a517-ad07ab22e5d7.png)

Hình 14: Ánh xạ thư mục code hiện tại vào trong container



Vậy là đã ánh xạ thành công thư mục code hiện tại vào trong container, để kiểm tra các bạn có thể sửa hàm `fetchAll`, thêm 1 kết quả nữa rồi save lại. Sau đó thử `curl http://localhost:3000` thì sẽ thấy trả về kết quả sau khi sửa code:

![image.png](https://images.viblo.asia/19f53b1b-4d27-4e63-a7f1-49063a4bf348.png)

Hình 15: Kết quả trả về của API mới



Trường hợp các bạn lỡ tắt hoặc stop conatiner, thì chỉ cần chạy lại bằng lệnh:

`docker start -a 17b77d31bb12`

Ở đây:

* `-a`: Vì khi container được khởi động lại bằng lệnh docker start, nó sẽ chạy ở nền và không hiển thị log trực tiếp trên terminal của bạn. chúng ta dùng tham số trên để dễ dàng trong việc phát triển, debug ứng dụng
* `17b77d31bb12`: là container đã vô tình bị tắt trước đó ( các bạn có thể dùng lệnh `docker ps -a` để hiển thị toàn bộ container )

Từ cách này chúng ta có thể code luôn "bên trong" container mà không cần phải phụ thuộc vào môi trường máy host bên ngoài, điều này tránh tối đa được xung đột giữa các môi trường trên các máy khác nhau.

## Kết luận

Qua bài viết này, chúng ta đã thấy được tác dụng khi áp dụng Docker vào phát triển phần mềm, Docker giúp các lập trình viên build và chạy ứng dụng 1 cách nhanh chóng, tránh các xung đột như thư viện không trùng phiên bản, môi trường thiếu... và chúng ta đã đi qua các ví dụ về các khái niệm cơ bản, các câu lệnh hay sử dụng và đã chạy và push docker image của riêng mình lên Docker Hub để mọi người có thể sử dụng.\
Chúng ta đã hoàn thành bài viết đầu tiên mà mình chia sẻ về Docker, bài tiếp theo thì mình sẽ cùng với các bạn tìm hiểu tiếp về Docker Compose nhé