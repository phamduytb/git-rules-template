# git-rules-template:

# Quy tắc đặt tên nhánh khi thi công chức năng:

  feature/[Mô tả ngắn gọn về chức năng]
  
Ví dụ: Thực hiện thi công: Yêu cầu nhập mã captcha khi đăng nhập không thành công nhiều lần.

Tên nhánh sẽ là: feature/login-captcha

# Quy tắc đặt tên nhánh khi fix bug:

  bugfix/[Mô tả ngắng gọn về bug]
 
Ví dụ: Thực hiện fix bug: Lỗi không biển thị đủ thông tin trên file báo cáo thuế.

Tên nhánh sẽ là: bugfix/miss-data-report-tax

# Quy tắc đặt tên nhánh release:
  release/[Mã phiên bản]
Tham khảo cách đặt mã phiên bản: Semantic Versioning

Ví dụ: Thực hiện phát hành bản R1.2.

Tên nhánh sẽ là: release/r1.2

# Quy tắc đánh tag:

Sử dụng [Mã phiên bản] để đánh tag.

Ví dụ: r1.2

# Quy tắc đặt tên nhánh khi hotfix:
hotfix/[Mã phiên bản hotfix]
Ví dụ: Thực hiện hot fix cho bản r1.2 với mã hotfix: r1.2.1.

Tên nhánh sẽ là: hotfix/r1.2.1

#Quy tắc viết comment khi commit:
  type: subject (Bắt buộc)
  body (Tùy chọn)
  
1. Type:

* feat - Một tính năng mới (feature)
*  fix - Fix một bug
*  docs - Thay đổi tài liệu
*  style - Mọi thứ liên quan tới style
*  refactor - Refactor code
*  test - Mọi thứ liên quan tới test
*  chore - Cập nhật các cấu hình build, cấu hình ứng dụng,...

2. Subject:

*  Không được dài quá 50 ký tự, bắt đầu bằng chữ hoa và không được kết thúc bằng dấu chấm.
*  Sử dụng câu mệnh lệnh để mô tả những gì commit thực hiện thay vì những gì nó đã làm. Ví dụ: sử dụng "thay đổi" thay vì "đã thay đổi"

3. Body:

*  Sử dụng khi commit cần giải thích thêm. Sử dụng để giải thích những gì (What), tại sao (Why) của commit này, không sử dụng làm thế nào (How).
*  Cần một dòng trống giữa type: subject, mỗi dòng không quá 72 ký tự.

Ví dụ

  feat: Hiển thị captcha khi người dùng đăng nhập nhiều lần
  Captcha sẽ được thị sau khi người dùng đăng nhập sai n lần. Ngăn không cho phép người dùng      viết các công cụ tự động dò mật khẩu.
  Số lần đăng nhập sai được cấu hình tại file confile với khóa là: MaxLoginFail.
  
  # Chú ý trong quá trình thi công của Dev:
  
 * Dev chủ động tạo nhánh feature, bugfix trên repo remote theo các work items được gán.
*  Tất cả các nhánh đều được tách ra từ nhánh origin/develop
*  Khi dùng câu lệnh merge thì code sẽ được merge từ nhánh đích vào nhánh mình đang checkout. *  Ví dụ: Checkout ở nhánh feature/pbi-001 merge với nhánh develop => tất cả các code của       nhánh develop sẽ được merge về nhánh đang checkout.
*  Có thói quen merge code với nhánh origin/develop thường xuyên và áp dụng quy tắc: Chỉ thêm code của mình vào, không bỏ code của nhánh origin/develop trong lúc merge.
*  Nên thực hiện merge code với nhánh origin/develop => Xử lý conflict trước các bước: Build, test, push.
*  Khi tạo pull request mà hệ thống báo conflict => merge lại code với nhánh origin/develop => xử lý conflict => Bulid => test => push lại => Hệ thống tự động đưa commit đó vào pull request hiện tại.
