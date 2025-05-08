https://battle.cookiearena.org/challenges/web/sql-injection-bypass-login

- Giao diện của web:

![1](./img/1.png)

1.	Thử với giá trị bình thường xem chức năng login có hoạt động không

- Ta nhập username=1 và password=1

![1](./img/2.png)
Chức năng bình thường

2.	Thử với giá trị bất bình thường xem web có validate kí tự không

- Ta nhập username=1’ và pasword = 1

![1](./img/3.png)
Web phản ứng với kí tự ‘ 

- Thử tiếp với kí tự “  

![1](./img/4.png)
Vậy ta sẽ dùng ‘ để SQL injection 

- Payload: username=guest' OR 1=1-- &password=guest  
  
![1](./img/5.png)
Lấy được Flag