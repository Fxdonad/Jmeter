**Báo Cáo Hiệu Suất - JMeter Load Test**

## 1. Giới Thiệu
Báo cáo này phân tích kết quả kiểm thử hiệu suất của mô-đun đăng nhập (“login”) trong hệ thống với hai kịch bản tải: 50 và 100 người dùng đồng thời.

## 2. Thông Tin Kiểm Thử
- **Công cụ kiểm thử**: Apache JMeter
- **Kịch bản**: Gửi yêu cầu đăng nhập và ghi nhận thời gian phản hồi.
- **Tiêu chí đánh giá**:
  - Thời gian đáp ứng trung bình (Average Response Time)
  - Thời gian phản hồi tối thiểu và tối đa (Min/Max Response Time)
  - Độ lệch chuẩn (Standard Deviation)
  - Tỷ lệ lỗi (Error %)
  - Lưu lượng giao dịch (“Throughput”)

## 3. Kết Quả Phân Tích
### 3.1. Kiểm thử với 50 User
- **Số lượng request**: 101
- **Thời gian phản hồi trung bình**: 612ms
- **Thời gian phản hồi tối thiểu**: 549ms
- **Thời gian phản hồi tối đa**: 1617ms
- **Độ lệch chuẩn**: 113.39ms
- **Tỷ lệ lỗi**: 0%
- **Throughput**: 1.7 requests/phút

### 3.2. Kiểm thử với 100 User
- **Số lượng request**: 101
- **Thời gian phản hồi trung bình**: 588ms
- **Thời gian phản hồi tối thiểu**: 544ms
- **Thời gian phản hồi tối đa**: 883ms
- **Độ lệch chuẩn**: 37.14ms
- **Tỷ lệ lỗi**: 0%
- **Throughput**: 19.6 requests/phút

## 4. Nhận Xét & Kết Luận
- **Hiệu suất hệ thống cải thiện khi số người dùng tăng lên**: Thời gian phản hồi trung bình giảm từ 612ms (đối với 50 user) xuống 588ms (đối với 100 user). Ngoài ra, thời gian phản hồi tối đa cũng giảm đáng kể (1617ms → 883ms).
- **Tỷ lệ lỗi là 0%** trong cả hai kịch bản, cho thấy hệ thống hoạt động ổn định.
- **Throughput tăng lên rõ rệ**: Từ 1.7 requests/phút (đối với 50 user) lên 19.6 requests/phút (đối với 100 user), cho thấy hệ thống đã xử lý request hiệu quả hơn khi số user tăng.
- **Độ lệch chuẩn giảm đi** (đối với 100 user), cho thấy hệ thống trả về thời gian phản hồi đồng định hơn khi tải cao.

## 5. Kiến Nghị
- **Hệ thống hoạt động tốt** khi số người dùng tăng lên, nhưng nên tiếp tục kiểm thử với số lượng user lớn hơn (đạt ngưỡng 500 user) để đánh giá giới hạn hệ thống.
- **Xem xét tối ưu hóa throughput** để duy trì hiệu suất tốt khi tăng số user cao hơn.
- **Tiếp tục theo dõi độ lệch chuẩn** khi tăng user để đánh giá sự ổn định.

---
**Tóm lại**: Hệ thống hoạt động tốt và tăng hiệu suất khi tăng user. Nên kiểm thử tăng user lên các ngưỡng cao hơn để đánh giá khả năng chịu đỡ tối đa.

