https://battle.cookiearena.org/challenges/web/simple-sqli

1.	Overview code:

![1](./img/37.png)

- Tạo một bảng database có tên users gồm 3 cột userid, userpassword, userlevel
Thực hiện tạo giá trị guest và admin 

![1](./img/38.png)

- Thực hiện truy vấn: SELECT * FROM users WHERE userlevel='userlevel'

2. Thực hiện lấy Flag:
-	Chuỗi truy vấn sẽ được chèn vào giá trị userlevel

![1](./img/39.png)

-	Thử với giá trị 0:

![1](./img/40.png)

-	Thử với giá trị bất thường: 0'

![1](./img/42.png)
Web đã validate giá trị nên ta có thể tiêm sql 

-	Payload: ' UNION SELECT 'admin', 'password', 0--

![1](./img/41.png)