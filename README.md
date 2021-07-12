LINK BÀI LAB: https://www.vulnhub.com/entry/photographer-1,519/

Tiến hành SCAN:

![image](https://user-images.githubusercontent.com/72652376/125227463-288f1100-e2fd-11eb-8916-3fbee1ea81e9.png)


![image](https://user-images.githubusercontent.com/72652376/125227973-106bc180-e2fe-11eb-9303-b83f253a1ccf.png)


2 cổng 139, 445 sử dụng dịch vụ SMB, ta sẽ sử dụng enum4linux xem có thu thập thêm được gì không.

![image](https://user-images.githubusercontent.com/72652376/125228356-d2bb6880-e2fe-11eb-818b-16d3b19480cd.png)

Thu được 1 thư mục được share, truy cập và get về máy

![image](https://user-images.githubusercontent.com/72652376/125228598-40679480-e2ff-11eb-9c8a-248f8e4f679a.png)

File mailsent.txt:

![image](https://user-images.githubusercontent.com/72652376/125228694-7442ba00-e2ff-11eb-946a-2fb35d174fc0.png)

Có một số mail và hint mật khẩu

File còn lại là mã nguồn WPS. Tiếp tục kiểm tra các port còn lại xem có gì không rồi quay lại mã nguồn này nếu tắc :v 

Port 8000 sử dụng dịch vụ HTTP cho nên ta scan dir bằng dirbuster thu được:

![image](https://user-images.githubusercontent.com/72652376/125229628-62621680-e301-11eb-860e-ee36df421501.png)

/app: Không có quyền truy cập

/categories/ : Không có quyền truy cập

/admin : có 1 trang login 

Login với user và pass thì thành công vào được dashboard của web:

![image](https://user-images.githubusercontent.com/72652376/125230783-b5d56400-e303-11eb-84cc-358d9253866c.png)

Web trên sử dụng Koken CMS nên có thể thử upshell dựa trên hướng dẫn tại https://www.exploit-db.com/exploits/48706

![image](https://user-images.githubusercontent.com/72652376/125231214-85da9080-e304-11eb-8541-78f52574c0ad.png)


Xóa đuôi jpg tại burp

![image](https://user-images.githubusercontent.com/72652376/125243642-8da43000-e318-11eb-9ebb-c1c0e94d8b28.png)

![image](https://user-images.githubusercontent.com/72652376/125243664-94cb3e00-e318-11eb-9053-57492e0e9b0e.png)

![image](https://user-images.githubusercontent.com/72652376/125243795-c17f5580-e318-11eb-8ec7-677d300b0630.png)

Tại kali tiến hành lắng nghe tại port 1234, và thực hiện up shell thành công

Kiểm tra trên 2 thư mục /home tìm kiếm 1 cờ user.txt

![image](https://user-images.githubusercontent.com/72652376/125244252-4cf8e680-e319-11eb-95b9-7a73406c4de2.png)


DONE :V

Tìm cách leo thang lên root nữa để kiếm cờ cuối cùng

![image](https://user-images.githubusercontent.com/72652376/125245826-39e71600-e31b-11eb-8188-57ec4ae9f6e8.png)

Có thể thấy dịch vụ php7.2 có SUID, tìm kiếm trên gtfobins thu được https://gtfobins.github.io/gtfobins/php/#sudo

![image](https://user-images.githubusercontent.com/72652376/125246630-399b4a80-e31c-11eb-8718-1507074fc2ae.png)

OKE....!!!

Leo thang đặc quyền thành công

![image](https://user-images.githubusercontent.com/72652376/125246405-f214be80-e31b-11eb-8ed0-cec917cc021c.png)

![image](https://user-images.githubusercontent.com/72652376/125246431-fb059000-e31b-11eb-9308-d5674cf8d492.png)

DONE...

#kid-glitch
