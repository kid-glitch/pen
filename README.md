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


File còn lại là mã nguồn WPS. Tiếp tục kiểm tra các port còn lại xem có gì không rồi quay lại mã nguồn này nếu tắc :v 


