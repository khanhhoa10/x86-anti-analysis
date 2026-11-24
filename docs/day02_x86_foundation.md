# Ngày 02 – Nền tảng x86

## Mục tiêu
Hiểu các khái niệm x86 cần thiết để đọc ví dụ Assembly, phân tích mã máy và debug chương trình Win32/x86.

## 1. Kiến trúc và thanh ghi
- x86 32-bit sử dụng các thanh ghi tổng quát như EAX, EBX, ECX, EDX, ESI, EDI, EBP, ESP.
- EIP lưu địa chỉ lệnh tiếp theo trong cách mô tả kiến trúc x86.
- EFLAGS lưu các cờ trạng thái, ví dụ ZF và CF.

## 2. Bộ nhớ
- Bộ nhớ được truy cập thông qua địa chỉ.
- Dạng [EBX] biểu thị dữ liệu tại địa chỉ đang nằm trong EBX.
- Dạng [EBX+4] biểu thị dữ liệu tại địa chỉ EBX cộng 4 byte.

## 3. Các lệnh cần nhận diện
- MOV: chép dữ liệu.
- LEA: tính địa chỉ hiệu dụng.
- ADD, SUB, XOR: phép toán số học/logic.
- CMP: so sánh bằng cách cập nhật cờ trạng thái.
- JMP, JE/JZ, JNE/JNZ: chuyển điều khiển.
- PUSH, POP: thao tác với ngăn xếp.
- CALL, RET: gọi hàm và quay về.

## 4. Cờ trạng thái
- ZF (Zero Flag): thường được đặt khi kết quả phép toán bằng 0.
- CF (Carry Flag): thể hiện carry/borrow trong phép toán số học không dấu.
- CMP cập nhật cờ để lệnh nhảy có điều kiện sử dụng.

## 5. Ngăn xếp
- Ngăn xếp thường dùng để lưu dữ liệu tạm, tham số và địa chỉ quay về.
- PUSH đưa dữ liệu lên ngăn xếp; POP lấy dữ liệu ra.
- CALL gọi hàm; RET quay về địa chỉ đã lưu.

## 6. Liên hệ với đề tài
- Anti-disassembly: cần hiểu cách công cụ đọc các byte thành lệnh và cách luồng điều khiển ảnh hưởng đến việc phân tích.
- Anti-debugging: cần hiểu thanh ghi, cờ trạng thái, lời gọi hàm và cách chương trình kiểm tra môi trường chạy.

## 7. Bài tập tự kiểm tra
1. Sau mov eax, 7 rồi mov ebx, 2 rồi sub eax, ebx, EAX bằng bao nhiêu?
EAX bằng 5. 
7 - 2 = 5; lệnh SUB lưu kết quả vào toán hạng đích là EAX.
2. mov eax, ebx và mov eax, [ebx] khác nhau thế nào?
mov eax, ebx chép giá trị trong EBX vào EAX. mov eax, [ebx] dùng EBX làm địa chỉ bộ nhớ, rồi đọc dữ liệu tại địa chỉ đó vào EAX.
3. cmp eax, 0 có làm EAX trở thành 0 không?
Không. CMP thực hiện phép so sánh để cập nhật cờ trạng thái; nó không ghi kết quả phép trừ vào EAX.
4. JE dựa vào cờ nào?
ZF (Zero Flag). JE nhảy khi ZF = 1, tức điều kiện bằng nhau đúng theo phép so sánh trước đó.
5. ESP thường liên quan đến vùng nhớ nào?
Ngăn xếp (stack). ESP thường trỏ đến đỉnh ngăn xếp trong chương trình x86 32-bit.
6. CALL và RET có vai trò gì?
CALL gọi hàm và lưu địa chỉ quay về lên ngăn xếp; RET lấy địa chỉ quay về và tiếp tục thực thi tại đó.
7. Vì sao khi đọc disassembly, cần chú ý lệnh nhảy và địa chỉ đích?
Vì lệnh nhảy có thể làm chương trình không chạy tuần tự từng lệnh. Khi phân tích, cần theo dõi lệnh nhảy và địa chỉ đích để hiểu luồng điều khiển và tránh đọc sai logic chương trình.