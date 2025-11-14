# Đề tài: KỸ THUẬT TRUYỀN DÒNG DỮ LIỆU VIDEO TRONG CÁC ỨNG DỤNG TRUYỀN THÔNG
## (Video Streaming Techniques in Communication Applications)

---

## A. GIỚI THIỆU

- A.1. Lý do chọn đề tài  
- A.2. Tính cấp thiết và bối cảnh công nghệ  
- A.3. Bài toán thực tiễn trong video streaming  
  - A.3.1. Latency  
  - A.3.2. Packet loss, jitter  
  - A.3.3. Bitrate adaptation và QoE  
- A.4. Mục tiêu nghiên cứu  
- A.5. Cách tiếp cận và phương pháp nghiên cứu  
  - A.5.1. Nghiên cứu lý thuyết (RFC, MPEG, ITU-T, IEEE, ACM…)  
  - A.5.2. Phân tích mô hình toán và thuật toán  
  - A.5.3. Thiết kế mô phỏng và đánh giá thực nghiệm  
- A.6. Tài liệu chuẩn và nền tảng lý thuyết sử dụng  

---

## B. TỔNG QUAN LÝ THUYẾT VỀ TRUYỀN DÒNG VIDEO

- B.1. Nén video và các chuẩn mã hóa  
  - B.1.1. H.264/AVC (ISO/IEC 14496-10)  
  - B.1.2. H.265/HEVC (ISO/IEC 23008-2)  
  - B.1.3. AV1 (AOMedia Video 1)  
  - B.1.4. Các khái niệm: frame, macroblock, prediction, transform, entropy coding  
- B.2. Cấu trúc video và dòng dữ liệu  
  - B.2.1. GOP, frame I/P/B  
  - B.2.2. Bitrate, framerate, resolution  
  - B.2.3. Mô hình buffer phát video  
- B.3. Kiến trúc hệ thống streaming  
  - B.3.1. Mô hình Client–Server truyền thống  
  - B.3.2. CDN và Edge Caching  
  - B.3.3. P2P Streaming  
- B.4. Mạng và các yếu tố ảnh hưởng đến streaming  
  - B.4.1. Độ trễ (latency)  
  - B.4.2. Jitter  
  - B.4.3. Packet loss  
  - B.4.4. Ước lượng throughput và băng thông hiệu dụng  
- B.5. Các chuẩn hóa kỹ thuật trong streaming  
  - B.5.1. MPEG-DASH (ISO/IEC 23009-1)  
  - B.5.2. HTTP Live Streaming (HLS – RFC 8216)  
  - B.5.3. CMAF (ISO/IEC 23000-19)  
  - B.5.4. Các khuyến nghị DASH-IF và Apple HLS Guidelines  

---

## C. CÁC KỸ THUẬT TRUYỀN DÒNG DỮ LIỆU VIDEO

### C.1. Progressive Download

- C.1.1. Kiến trúc và nguyên lý hoạt động  
- C.1.2. Mô hình tải tuyến tính  
- C.1.3. Ước lượng throughput và tốc độ tải  
- C.1.4. Mô hình độ trễ khởi tạo (startup delay)  
- C.1.5. Ưu điểm, nhược điểm và giới hạn của Progressive Download  

### C.2. Adaptive Bitrate Streaming (ABR)

- C.2.1. Kiến trúc chung của ABR trên HTTP  
  - C.2.1.1. Khái niệm segment, representation, profile  
  - C.2.1.2. Manifest: MPD (DASH), playlist M3U8 (HLS)  
- C.2.2. MPEG-DASH  
  - C.2.2.1. Cấu trúc MPD  
  - C.2.2.2. Adaptation set, representation, segment template  
- C.2.3. HLS và Low-Latency HLS  
  - C.2.3.1. Playlist M3U8 và segment TS/fMP4  
  - C.2.3.2. LL-HLS: partial segments, preload hints  
- C.2.4. CMAF và Low-Latency Streaming  
- C.2.5. Mô hình toán học cho ABR  
  - C.2.5.1. Mô hình buffer dynamics  
  - C.2.5.2. Ước lượng băng thông (throughput estimation)  
- C.2.6. Thuật toán chọn bitrate trong ABR  
  - C.2.6.1. Thuật toán Rate-Based (RB)  
  - C.2.6.2. Thuật toán Buffer-Based (BB)  
  - C.2.6.3. Thuật toán Hybrid (kết hợp rate + buffer)  
  - C.2.6.4. Thuật toán BOLA (Buffer Occupancy based Lyapunov Algorithm)  
  - C.2.6.5. Thuật toán MPC (Model Predictive Control)  
  - C.2.6.6. Pensieve – ABR dựa trên Deep Reinforcement Learning  

### C.3. Real-time Video Streaming

- C.3.1. RTP/RTCP (RFC 3550)  
  - C.3.1.1. Cấu trúc gói RTP  
  - C.3.1.2. RTCP report, thống kê jitter và loss  
- C.3.2. WebRTC  
  - C.3.2.1. Kiến trúc ICE / STUN / TURN  
  - C.3.2.2. SRTP, DTLS-SRTP cho bảo mật  
  - C.3.2.3. Congestion Control GCC (Google Congestion Control)  
- C.3.3. RTMP  
  - C.3.3.1. Nguyên lý hoạt động  
  - C.3.3.2. Hạn chế so với các giải pháp mới  
- C.3.4. Mô hình độ trễ end-to-end trong real-time streaming  

### C.4. So sánh, ưu – nhược điểm và trade-off

- C.4.1. Progressive Download vs ABR vs Real-time Streaming  
- C.4.2. Trade-off giữa:  
  - C.4.2.1. Latency  
  - C.4.2.2. Video quality  
  - C.4.2.3. Stability (rebuffering, bitrate switching)  
- C.4.3. Các kiến trúc triển khai điển hình (biểu đồ ASCII)  

---

## D. PHÂN TÍCH SÂU CÁC VẤN ĐỀ KỸ THUẬT

- D.1. Jitter trong RTP (theo RFC 3550)  
  - D.1.1. Công thức tính jitter  
  - D.1.2. Ảnh hưởng của jitter đến QoE  
- D.2. Mô hình buffer occupancy trong ABR  
  - D.2.1. Phương trình diễn tiến buffer  
  - D.2.2. Ổn định buffer và tránh stall  
- D.3. Mô hình QoE trong video streaming  
  - D.3.1. ITU-T P.1203 – mô hình đánh giá QoE end-to-end  
  - D.3.2. Netflix VMAF – Video Multi-Method Assessment Fusion  
  - D.3.3. So sánh PSNR, SSIM, VMAF  
- D.4. Congestion Control  
  - D.4.1. Congestion control ở tầng TCP (Cubic, BBR)  
  - D.4.2. Congestion control trong WebRTC (GCC)  
- D.5. Hiện tượng stall (rebuffering)  
  - D.5.1. Mô hình hóa thời gian stall  
  - D.5.2. Tác động của stall lên QoE người dùng  
- D.6. Phân tích trade-off latency – quality – stability  

---

## E. THIẾT KẾ MÔ PHỎNG VÀ THỬ NGHIỆM

- E.1. Mô hình thực nghiệm tổng thể  
  - E.1.1. Sơ đồ kiến trúc hệ thống (ASCII)  
  - E.1.2. Môi trường mạng (network emulation)  
- E.2. Xây dựng server DASH/HLS  
  - E.2.1. Chuẩn bị nội dung và encode multi-bitrate  
  - E.2.2. Tạo MPD/M3U8 và cấu hình web server  
- E.3. Mô phỏng ABR bằng Python  
  - E.3.1. Mô hình hóa mạng (throughput trace)  
  - E.3.2. Cài đặt thuật toán BOLA / MPC / Pensieve (pseudo-code)  
  - E.3.3. Mô phỏng diễn tiến buffer và bitrate selection  
- E.4. Đo lường chất lượng trải nghiệm (QoE)  
  - E.4.1. Các metric: stall time, quality level, switching  
  - E.4.2. Tính VMAF/SSIM/PSNR theo từng kịch bản  
- E.5. So sánh các kỹ thuật streaming  
  - E.5.1. So sánh progressive vs ABR  
  - E.5.2. So sánh các thuật toán ABR với nhau  
- E.6. Thảo luận và đánh giá kết quả  

---

## F. KẾT LUẬN VÀ HƯỚNG PHÁT TRIỂN

- F.1. Kết luận chung về các kỹ thuật truyền dòng video  
- F.2. Đánh giá ưu – nhược điểm của các mô hình và thuật toán đã nghiên cứu  
- F.3. Hạn chế của project  
- F.4. Hướng nghiên cứu và phát triển trong tương lai  
  - F.4.1. ABR dựa trên học sâu và QoE-aware  
  - F.4.2. Streaming UHD/8K, VR/360°  
  - F.4.3. Tối ưu cho mạng di động 5G/6G  

---

## G. TÀI LIỆU THAM KHẢO (ĐỊNH DẠNG IEEE)

- G.1. RFC (RFC 3550, RFC 8216, …)  
- G.2. Chuẩn MPEG/ISO/IEC (MPEG-DASH, CMAF, H.264, H.265, …)  
- G.3. Khuyến nghị ITU-T (P.1203, …)  
- G.4. Bài báo IEEE/ACM liên quan đến ABR, QoE, VMAF, WebRTC GCC  
- G.5. Tài liệu kỹ thuật từ các hãng: Netflix TechBlog, Apple HLS Docs, DASH-IF, Google WebRTC Docs  

