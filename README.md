# Hệ Thống Xử Lý Hàng Đổi Trả Sàn TMĐT (Shopee Return Management Hub)

Ứng dụng web toàn diện quản lý vòng đời hàng đổi trả trên sàn Thương mại điện tử (Shopee) kết nối trực tiếp với **Supabase PostgreSQL (Schema: `san_hoan`)**, thư viện lưu trữ đa phương tiện **Google Drive**, và bot thông báo phê duyệt **Lark Suite**.

🔗 **Trang Live Web App:** [https://nguyensonphong.github.io/shopee-return-app/](https://nguyensonphong.github.io/shopee-return-app/)  
📁 **Thư mục Media Google Drive:** [ShopeeReturnMedia](https://drive.google.com/drive/folders/1vYBVcoYobK2JGyEWggmD25ajREitwkBB?usp=sharing)

---

## 🎯 Quy Trình Nghiệp Vụ Chuẩn 5 Kho

Hệ thống được thiết kế bám sát 100% quy trình vận hành và kiểm soát rủi ro:

1. **Kho 1 - Kho Sàn Trả (Tiếp Nhận Ban Đầu):**
   - Hàng ngày nhận danh sách hàng sẽ hoàn, đơn vị vận chuyển (SPX, J&T, Ninja Van, Viettel Post, GHTK), ngày dự kiến nhập.
   - Thủ kho tra cứu vận đơn, lập biên bản nhận hàng, đính kèm link camera quay video kiểm tra ngoại quan kiện hàng + mở hộp xem thực tế bên trong.
2. **Kho 2 - Kho Bán Bình Thường (Xuất Bán Hàng):**
   - Hàng sau khi bộ phận Kỹ thuật / Bảo hành giám định đạt chuẩn, nguyên vẹn sẽ được điều chuyển về đây và đóng ticket.
3. **Kho 3 - Kho Chờ Xử Lý Sàn:**
   - Dành cho sản phẩm xác định có vấn đề (hư hỏng, vỡ nát, mất linh kiện).
   - Bộ phận Kỹ thuật xác định mức độ hư hỏng, đưa ra mức đòi bồi hoàn (100%, 70%, 50%).
   - CS-Ecom / Trợ lý AI tự động soạn văn bản khiếu nại gửi Shopee.
   - Chu kỳ Shopee phản hồi: 2 - 3 ngày làm việc; CS phải phản hồi lại trong 24 giờ.
   - Quy tắc 5 lần: Sau 5 lần claim không đạt thỏa thuận, tự động chuyển cờ **Escalation** cho người phụ trách thủ công để đàm phán lại với Shopee hoặc trình BGĐ duyệt mức bồi hoàn.
4. **Kho 4 - Kho Hoàn Shopee:**
   - Khi Shopee chấp thuận bồi hoàn 100% giá trị, chuyển vào kho này và đóng ticket.
5. **Kho 5 - Kho Hàng Thanh Lý:**
   - Nếu không được bồi hoàn 100% hoặc sau quá trình đàm phán chốt mức bồi hoàn một phần, điều chuyển về kho thanh lý và xuất bán thu hồi vốn.

---

## 🛠️ Công Nghệ & Tích Hợp

- **Frontend:** Single Page Application (HTML5, Tailwind CSS, Chart.js, Font Awesome, Responsive Mobile/Desktop).
- **Cơ sở dữ liệu:** Supabase PostgreSQL (Schema riêng: `san_hoan`).
- **Lưu trữ Bằng chứng:** Google Drive cá nhân (Thư mục mở quyền Viewer công khai).
- **Tương tác Thông báo:** Lark Suite Bot & Lark Interactive Cards (Phê duyệt/Từ chối trực tiếp trong tin nhắn chat).
- **Triển khai Live:** GitHub Pages tự động.
