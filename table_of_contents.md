**“Kỹ thuật truyền dòng dữ liệu video trong các ứng dụng truyền thông”**
(*Video Streaming Techniques in Communication Applications*)

---

## **A. Giới thiệu**

A.1. Lý do chọn đề tài
A.2. Tính cấp thiết và bối cảnh công nghệ
A.3. Bài toán thực tiễn trong video streaming
A.4. Mục tiêu nghiên cứu
A.5. Cách tiếp cận và phương pháp
A.6. Tài liệu chuẩn và nền tảng lý thuyết sử dụng (RFC, ITU-T, MPEG, IEEE…)

---

## **B. Tổng quan lý thuyết về truyền dòng video**

B.1. Tổng quan về nén video
 • H.264/AVC (ISO/IEC 14496-10)
 • H.265/HEVC (ISO/IEC 23008-2)
 • AV1 (AOMedia)
 • Mô hình dự đoán, biến đổi, entropy coding

B.2. Kiến trúc hệ thống streaming
 • Client–Server
 • CDN và Edge Computing
 • P2P Streaming

B.3. Mô hình dòng dữ liệu video
 • Bitrate, tốc độ mã hóa
 • GOP, cấu trúc khung I/P/B
 • Mô hình buffer: startup, playback, stall

B.4. Mạng và các yếu tố ảnh hưởng
 • Độ trễ (latency), jitter
 • Congestion, packet loss
 • Công thức ước lượng throughput

B.5. Chuẩn hóa kỹ thuật trong streaming
 • MPEG-DASH (ISO/IEC 23009-1)
 • HLS (RFC 8216)
 • CMAF (ISO/IEC 23000-19)

---

## **C. Các kỹ thuật truyền dòng dữ liệu video (phân tích sâu + toán học)**

### **C.1. Progressive Download**

C.1.1. Kiến trúc hoạt động
C.1.2. Mô hình tải tuyến tính
C.1.3. Công thức dự đoán throughput
C.1.4. Độ trễ khởi tạo (startup delay model)
C.1.5. Giới hạn và vấn đề

### **C.2. Adaptive Bitrate Streaming (ABR)**

C.2.1. Kiến trúc chung của DASH/HLS
C.2.2. Mô hình phân đoạn và manifest
C.2.3. Thuật toán chọn bitrate
 • Buffer-Based (BB)
 • Rate-Based (RB)
 • Hybrid Models
 • BOLA (Utility-based, có hàm U(b))
 • MPC (Model Predictive Control: optimization, reward function)
 • Pensieve (Deep Reinforcement Learning)
C.2.4. Mô hình buffer dynamics
C.2.5. Công thức ước lượng băng thông
C.2.6. LL-HLS & Low-Latency DASH

### **C.3. Real-time Video Streaming**

C.3.1. RTP/RTCP (RFC 3550) — Mô hình jitter, packet loss
C.3.2. WebRTC
 • Kiến trúc ICE/SRTP/DTLS
 • Congestion control GCC (mô hình toán)
 • Delay-based & loss-based control
C.3.3. RTMP: nguyên lý, hạn chế
C.3.4. Mô hình độ trễ end-to-end
$$
L_{e2e} = L_{capture} + L_{encode} + L_{network} + L_{decode} + L_{render}
$$

---

## **D. Phân tích chuyên sâu các vấn đề kỹ thuật**

D.1. Jitter và công thức tính theo RTP (RFC 3550)
D.2. Mô hình biến động buffer trong ABR
D.3. QoE Metrics
 • ITU-T P.1203 model
 • VMAF (Netflix) – công thức, pipeline
 • SSIM/PSNR – phân tích hạn chế
D.4. Congestion Control
 • TCP Cubic vs BBR
 • WebRTC GCC
D.5. Hiện tượng stall và mô hình phân tích
D.6. Trade-off: latency – quality – stability

---

## **E. Thiết kế mô phỏng & thử nghiệm**

E.1. Mô hình thử nghiệm tổng thể
 • Sơ đồ system design ASCII
E.2. Xây dựng server DASH/HLS
E.3. Mô phỏng ABR bằng Python
 • Thuật toán BOLA / MPC
 • Buffer evolution simulation
E.4. Đo QoE theo băng thông
E.5. So sánh kỹ thuật streaming
E.6. Nhận xét & đánh giá

---

## **F. Kết luận và hướng phát triển**

F.1. Kết luận chung
F.2. Đánh giá hạn chế của mô hình
F.3. Hướng mở rộng nghiên cứu tương lai

---

## **G. Tài liệu tham khảo (chuẩn IEEE)**

*RFC, IEEE Xplore, ACM DL, MPEG, ITU-T, Netflix TechBlog, Apple HLS Docs, DASH-IF Docs, Google WebRTC Docs*

---

# ✅ **Mục lục đã hoàn thành.**

Bạn muốn tôi triển khai **Phần A – Giới thiệu**, hay muốn chỉnh sửa mục lục trước?
