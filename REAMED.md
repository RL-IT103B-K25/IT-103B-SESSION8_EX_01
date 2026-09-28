
Trường hợp kiểm thử	
-Điều phối xe theo FIFO
-Tính tổng điện năng và doanh thu

Dữ liệu đầu vào	
-['29A-112.33', '30E-889.12', '51K-678.99']
-[45.2, 30.5, 62.8, 28.0]

Kết quả sai thực tế
-pop() → xe 51K-678.99 được sạc trước
-i <= length → truy cập array[4] là undefined → tổng thành NaN

Kết quả đúng mong đợi
-shift() → xe 29A-112.33 được sạc trước
-i < length → tổng 166.5 kWh, doanh thu 749250 VNĐ


Phân tích 2 lỗi
Lỗi 1: waitingQueue.pop() lấy phần tử cuối → sai FIFO.
→ Sửa thành waitingQueue.shift().
Lỗi 2: i <= completedSessionsKwh.length chạy thêm 1 lần.
Khi i = 4, completedSessionsKwh[4] là undefined, cộng vào số → NaN.
→ Sửa thành i < completedSessionsKwh.length.