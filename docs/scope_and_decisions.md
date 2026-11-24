# Phạm vi và quyết định dự án

## 1. Đề tài
Kỹ thuật chống phân tích trong mã x86: Nhận diện Anti-Disassembly và Anti-Debugging cơ bản.

## 2. Mục tiêu
Xây dựng các chương trình minh họa do nhóm tự viết, phân tích bằng công cụ phù hợp, kiểm thử và ghi nhận kết quả để phục vụ báo cáo và thuyết trình.

## 3. Phạm vi
- Nền tảng thực nghiệm chính: Windows, Win32/x86 32-bit.
- Hai demo Anti-Disassembly và hai demo Anti-Debugging.
- Chỉ thử nghiệm chương trình do nhóm tự viết trong môi trường học tập.
- Không thử nghiệm trên phần mềm bên thứ ba hoặc mẫu tải từ Internet.
- Kỹ thuật mở rộng chỉ thực hiện sau khi demo lõi hoàn thành.

## 4. Demo dự kiến
- AD-01: Overlapping instructions.
- AD-02: Control-flow.
- AG-01: IsDebuggerPresent.
- AG-02: PEB BeingDebugged.

## 5. Công cụ dự kiến
- Visual Studio Community: viết và build C/C++.
- Ghidra: phân tích tĩnh.
- x32dbg: debug chương trình 32-bit.
- MASM: lựa chọn Assembly ưu tiên, cần kiểm tra build thực tế trước khi chốt.

## 6. Sản phẩm
- Báo cáo.
- Slide.
- Mã nguồn và file project cần thiết để build lại.
- Ảnh/log và bảng kiểm thử làm bằng chứng.

## 7. Trạng thái
Đây là phương hướng nhóm thống nhất để triển khai. Công cụ, cấu hình build và kết quả demo sẽ được cập nhật sau khi kiểm tra thực tế.
