> **KỸ THUẬT TRUYỀN DÒNG DỮ LIỆU VIDEO TRONG CÁC ỨNG DỤNG TRUYỀN THÔNG**
> (*Video Streaming Techniques in Communication Applications*)

---

## TRANG ĐẦU & PHẦN MỞ ĐẦU

* Trang bìa (Cover)
* Lời cảm ơn (Acknowledgements)
* Tóm tắt tiếng Việt (Abstract in Vietnamese)
* Abstract (English)
* Danh mục chữ viết tắt & ký hiệu (List of Acronyms and Notations)
* Danh mục hình vẽ (List of Figures)
* Danh mục bảng biểu (List of Tables)
* Mục lục (Table of Contents)

---

## CHƯƠNG 1. GIỚI THIỆU TỔNG QUAN (INTRODUCTION)

1.1. Động cơ nghiên cứu và bối cảnh ứng dụng
1.2. Bài toán chung của video streaming trong các hệ thống truyền thông hiện đại
1.3. Các kịch bản ứng dụng chính
 1.3.1. Video theo yêu cầu (VoD, SVOD, AVOD)
 1.3.2. Truyền hình trực tuyến (Live OTT, IPTV, Internet TV)
 1.3.3. Hội nghị truyền hình, họp trực tuyến (Video Conferencing)
 1.3.4. Cloud gaming và interactive streaming
 1.3.5. 360° video, VR/AR streaming

1.4. Các thách thức kỹ thuật
 1.4.1. Băng thông biến thiên và tắc nghẽn mạng
 1.4.2. Độ trễ đầu cuối (end-to-end latency)
 1.4.3. Chất lượng trải nghiệm (QoE) vs. tài nguyên mạng (QoS/QoE trade-off)
 1.4.4. Mở rộng quy mô (scalability) và phân phối toàn cầu

1.5. Mục tiêu, phạm vi và đóng góp của Project
1.6. Cấu trúc của Project/Đồ án

---

## CHƯƠNG 2. CƠ SỞ LÝ THUYẾT TÍN HIỆU VIDEO VÀ MÃ HÓA (VIDEO SIGNAL & CODING FOUNDATIONS)

2.1. Mô hình tín hiệu video số
 2.1.1. Sampling không gian, thời gian, và màu (spatio-temporal & color sampling)
 2.1.2. Chroma subsampling (4:4:4, 4:2:2, 4:2:0)
 2.1.3. GOP (Group of Pictures): I/P/B frames

2.2. Các chuẩn mã hóa video hiện đại
 2.2.1. H.264/AVC
 2.2.2. H.265/HEVC
 2.2.3. AV1, VP9 (tổng quan)
 2.2.4. SVC (Scalable Video Coding): temporal/spatial/SNR scalability

2.3. Cơ sở toán học của nén video
 2.3.1. Mô hình nguồn và loại bỏ dư thừa (redundancy removal)
 2.3.2. Biến đổi, lượng tử hoá và entropy coding (tổng quan)
 2.3.3. **Mô hình Rate–Distortion**
  a) Hàm rate–distortion ( R(D) ) và hàm distortion ( D )
  b) Công thức bitrate xấp xỉ theo độ phân giải, frame rate và mức chất lượng

2.4. Các thước đo chất lượng tín hiệu video (Objective Quality Metrics)
 2.4.1. PSNR, MSE: định nghĩa và giới hạn
 2.4.2. SSIM, MS-SSIM
 2.4.3. VMAF và các chỉ số QoE-aware
 2.4.4. Quan hệ giữa rate–distortion và QoE

2.5. Kết luận chương và liên hệ với bài toán streaming

---

## CHƯƠNG 3. KIẾN TRÚC HỆ THỐNG VIDEO STREAMING (END-TO-END ARCHITECTURE)

3.1. Chuỗi xử lý đầu cuối (End-to-end pipeline)
 3.1.1. Content ingestion & encoding
 3.1.2. Packaging và segmentation
 3.1.3. CDN, edge server, cache hierarchy
 3.1.4. Video player client và feedback

3.2. Kiến trúc client–server và overlay
 3.2.1. Mô hình client–server truyền thống
 3.2.2. HTTP-based streaming (progressive download vs. segmented streaming)
 3.2.3. Kiến trúc P2P và hybrid CDN–P2P

3.3. Mô hình hệ thống và ký hiệu toán học
 3.3.1. Mô hình mạng: băng thông, độ trễ, jitter, packet loss
 3.3.2. Mô hình buffer tại client: dung lượng, mức nước (buffer occupancy)
 3.3.3. Mô hình traffic video: arrival process, service process (mô hình hàng đợi đơn giản)

3.4. Phân loại các chế độ streaming
 3.4.1. VoD vs. Live streaming
 3.4.2. HTTP adaptive streaming vs. real-time streaming
 3.4.3. Low-latency, ultra-low-latency streaming

3.5. Gợi ý các sơ đồ minh hoạ ASCII cho kiến trúc hệ thống

---

## CHƯƠNG 4. GIAO THỨC TRUYỀN TẢI VÀ TẦNG MẠNG (TRANSPORT & NETWORKING PROTOCOLS)

4.1. Tổng quan về tầng vận chuyển trong video streaming
 4.1.1. So sánh TCP, UDP, SCTP trong bối cảnh media
 4.1.2. Khái niệm congestion control và reliability

4.2. RTP/RTCP và RTSP cho real-time streaming
 4.2.1. Cấu trúc gói RTP, timestamp, sequence number
 4.2.2. RTCP reports và feedback về chất lượng
 4.2.3. RTSP: thiết lập, điều khiển phiên (session control)

4.3. HTTP/1.1, HTTP/2, HTTP/3/QUIC trong adaptive streaming
 4.3.1. Cơ chế connection, multiplexing và head-of-line blocking
 4.3.2. QUIC và ưu điểm cho video streaming (0-RTT, connection migration)

4.4. Multicast và các cơ chế phân phối nhóm
 4.4.1. IP multicast, SSM, ASM (tổng quan)
 4.4.2. Application-layer multicast và overlay multicast

4.5. Cơ chế đáng tin cậy và chống lỗi
 4.5.1. ARQ, selective retransmission trong real-time
 4.5.2. FEC (Forward Error Correction) và trade-off bitrate

4.6. Phân tích chi phí giao thức và overhead trên bitrate hiệu dụng

---

## CHƯƠNG 5. KỸ THUẬT HTTP ADAPTIVE STREAMING (HLS, MPEG-DASH, CMAF…)

5.1. Khái quát HTTP adaptive streaming
 5.1.1. Ý tưởng segment-based streaming
 5.1.2. Lợi ích: CDN-friendly, firewall-friendly, cacheable

5.2. Chuẩn HLS (HTTP Live Streaming)
 5.2.1. Playlist (M3U8), variant playlist và media playlist
 5.2.2. Cấu trúc segment, keyframe alignment
 5.2.3. Low-Latency HLS (LL-HLS): chunked transfer và partial segments

5.3. Chuẩn MPEG-DASH
 5.3.1. Cấu trúc MPD (Media Presentation Description)
 5.3.2. Representation, adaptation set, periods
 5.3.3. DASH profiles, live vs. on-demand
 5.3.4. CMAF (Common Media Application Format) và chunked HTTP

5.4. Mô hình toán học của phân đoạn và bitrate
 5.4.1. Tính toán bitrate hiệu dụng trên từng segment
 5.4.2. Trade-off độ dài segment vs. độ trễ vs. ổn định chất lượng
 5.4.3. Mô hình hóa startup delay, rebuffering, bitrate switching

5.5. So sánh HLS, DASH, Smooth Streaming, HDS
 5.5.1. Khía cạnh chuẩn hoá, tương thích thiết bị
 5.5.2. Chi phí triển khai và tối ưu CDN

---

## CHƯƠNG 6. THUẬT TOÁN ADAPTIVE BITRATE (ABR) VÀ MÔ HÌNH TOÁN HỌC

6.1. Bài toán lựa chọn bitrate thích nghi
 6.1.1. Mô hình hóa quyết định chọn representation cho từng segment
 6.1.2. Ràng buộc về buffer, throughput, QoE

6.2. Phân loại thuật toán ABR
 6.2.1. Rate-based (qua ước lượng throughput)
 6.2.2. Buffer-based (qua mức buffer)
 6.2.3. Hybrid rate–buffer-based
 6.2.4. Model-based, control-theoretic ABR
 6.2.5. ABR sử dụng học tăng cường (RL-based ABR)

6.3. Mô hình ước lượng throughput
 6.3.1. Ước lượng dựa trên lịch sử download segments (average, EWMA, harmonic mean)
 6.3.2. Throughput prediction với time-series / ML
 6.3.3. Phân tích sai số ước lượng và ảnh hưởng tới QoE

6.4. Mô hình buffer và điều khiển feedback
 6.4.1. Phương trình động buffer (buffer level dynamics)
 6.4.2. Mô hình điều khiển: PID, MPC, control-theoretic ABR
 6.4.3. Phân tích ổn định (stability) và dao động bitrate

6.5. Hàm utility và mô hình tối ưu hoá QoE
 6.5.1. Định nghĩa hàm utility theo bitrate và chất lượng thị giác
 6.5.2. Penalty cho rebuffering, bitrate switching và latency
 6.5.3. Bài toán tối ưu đa mục tiêu (multi-objective optimization): QoE vs. fairness vs. cost

6.6. ABR như một bài toán MDP/RL
 6.6.1. Định nghĩa state, action, reward trong RL-ABR
 6.6.2. Các thuật toán RL điển hình (DQN, Actor-Critic cho ABR – mô tả khái quát)
 6.6.3. Mô hình hóa training environment: trace mạng, QoE model

6.7. So sánh các thuật toán ABR tiêu biểu và phân tích ưu/nhược điểm

---

## CHƯƠNG 7. KIỂM SOÁT TẮC NGHẼN VÀ QoS/QoE TRONG VIDEO STREAMING

7.1. Mối quan hệ giữa congestion control và QoE
7.2. Các thuật toán congestion control cổ điển (TCP Reno, Cubic – tổng quan)
7.3. Congestion control hiện đại cho ứng dụng video
 7.3.1. TCP BBR và ảnh hưởng tới video streaming
 7.3.2. Congestion control trong QUIC với video

7.4. Congestion control chuyên biệt cho real-time video
 7.4.1. GCC (Google Congestion Control) trong WebRTC
 7.4.2. NADA, SCReAM và các scheme khác
 7.4.3. Jitter buffer và điều khiển tốc độ gửi

7.5. QoS mechanisms
 7.5.1. DiffServ, traffic shaping, policing
 7.5.2. Network-assisted streaming (SAND, server–network assisted DASH)

7.6. Mô hình toán học QoS/QoE
 7.6.1. Mô hình hàng đợi và delay cho video flows
 7.6.2. Mối quan hệ giữa loss, delay, jitter và QoE người dùng cuối

---

## CHƯƠNG 8. REAL-TIME & INTERACTIVE STREAMING: WEBRTC VÀ ỨNG DỤNG TƯƠNG TÁC

8.1. Yêu cầu đặc thù của real-time & interactive streaming
 8.1.1. Latency < 500 ms và yêu cầu đồng bộ âm thanh–hình ảnh
 8.1.2. Bidirectional media và dữ liệu điều khiển

8.2. Kiến trúc WebRTC
 8.2.1. Signaling, ICE, STUN/TURN
 8.2.2. Media path, SRTP, SRTCP
 8.2.3. Data channels và các use case bổ trợ

8.3. Codec, packetization và FEC trong WebRTC
8.4. Mô hình control loop trong WebRTC: congestion, bandwidth estimation
8.5. Ứng dụng: hội nghị truyền hình, cloud gaming, remote desktop, collaborative apps

---

## CHƯƠNG 9. CÁC KỸ THUẬT NÂNG CAO: SCALABILITY, EDGE, MULTI-PATH & DRM

9.1. Scalable Video Coding (SVC) và layered streaming
 9.1.1. Temporal, spatial và quality scalability
 9.1.2. Ứng dụng SVC trong multicast, SFU/MCU conferencing

9.2. Multi-CDN, multi-path và path diversity
 9.2.1. Mô hình hóa phân luồng qua nhiều đường (MPTCP, QUIC multipath – khái quát)
 9.2.2. Thuật toán phân chia bitrate trên nhiều path

9.3. Edge computing trong video streaming
 9.3.1. Edge transcoding, edge caching
 9.3.2. Tối ưu delay và giảm tải core network

9.4. Caching & content placement
 9.4.1. Các chiến lược cache (LRU, LFU, LFU-DA…)
 9.4.2. Mô hình toán học cho hit ratio và impact lên QoE

9.5. Bảo mật và DRM (Digital Rights Management)
 9.5.1. Encryption ở mức transport vs. mức segment (ClearKey, AES-128)
 9.5.2. Ảnh hưởng của bảo mật đến latency và bitrate

---

## CHƯƠNG 10. ĐO LƯỜNG, MÔ PHỎNG VÀ ĐÁNH GIÁ HỆ THỐNG VIDEO STREAMING

10.1. Mô hình đánh giá QoE tổng thể
 10.1.1. Các chỉ số QoE: startup delay, average bitrate, rebuffering ratio, quality switches
 10.1.2. MOS (Mean Opinion Score) và subjective tests

10.2. Thiết kế kịch bản thí nghiệm
 10.2.1. Môi trường đánh giá: testbed, emulation, real deployment
 10.2.2. Sử dụng network emulator (tc/netem, dummynet…)
 10.2.3. Bộ trace mạng thực tế (cellular, Wi-Fi, broadband)

10.3. Thu thập và xử lý log từ video player
 10.3.1. Logging bitrate, buffer level, stall events
 10.3.2. Phân tích thống kê và vẽ đồ thị

10.4. So sánh các thuật toán ABR / giao thức / kiến trúc
 10.4.1. Thiết lập baseline và đối chứng
 10.4.2. Phân tích định lượng và định tính

10.5. Hướng dẫn sinh viên xây dựng mô hình mô phỏng / prototype
 10.5.1. Lựa chọn nền tảng (Dash.js, Shaka Player, WebRTC libs…)
 10.5.2. Các bước triển khai và kiểm thử

---

## CHƯƠNG 11. CASE STUDIES TIÊU BIỂU TỪ THỰC TẾ CÔNG NGHIỆP

11.1. Kiến trúc streaming của một dịch vụ OTT lớn (Netflix-like architecture – mô tả học thuật)
11.2. Case study: HLS/LL-HLS trong hệ sinh thái thiết bị Apple
11.3. Case study: MPEG-DASH và CMAF trong một nền tảng web đa trình duyệt
11.4. Case study: WebRTC trong hội nghị truyền hình đa điểm
11.5. Bài học rút ra và xu hướng phát triển (per-title encoding, content-aware encoding, AI-assisted streaming)

---

## CHƯƠNG 12. ĐỊNH HƯỚNG NGHIÊN CỨU / THIẾT KẾ CHO PROJECT CỦA SINH VIÊN

12.1. Mô tả bài toán nghiên cứu cụ thể
 12.1.1. Ví dụ 1: Thiết kế và đánh giá một thuật toán ABR mới
 12.1.2. Ví dụ 2: So sánh congestion control cho video trên QUIC vs. TCP
 12.1.3. Ví dụ 3: Tối ưu QoE cho live low-latency streaming

12.2. Yêu cầu về mô hình toán học và phân tích lý thuyết
12.3. Yêu cầu về triển khai prototype / mô phỏng
12.4. Yêu cầu về thực nghiệm, số liệu, biểu đồ, phân tích sai số
12.5. Tiêu chí đánh giá đồ án (kỹ thuật, học thuật, trình bày)

---

## CHƯƠNG 13. KẾT LUẬN VÀ HƯỚNG PHÁT TRIỂN

13.1. Tóm tắt đóng góp chính
13.2. Đánh giá hạn chế của nghiên cứu
13.3. Hướng phát triển: AI-driven streaming, 6G & holographic media, metaverse streaming

---

## TÀI LIỆU THAM KHẢO (REFERENCES)

* Trình bày theo **chuẩn IEEE**, chỉ bao gồm:

  * Bài báo IEEE, ACM, Elsevier, Springer,…
  * RFC chính thức (RTP/RTCP, HLS, QUIC, …)
  * Tài liệu chuẩn MPEG/ISO/IEC, DASH-IF, ITU-T
  * Netflix TechBlog, Apple/Google official docs,… (khi là nguồn chính thống)

---

## PHỤ LỤC (APPENDICES)

Phụ lục A. Ký hiệu toán học và tóm tắt công thức
Phụ lục B. Mô tả tập dữ liệu và trace mạng sử dụng
Phụ lục C. Pseudocode các thuật toán ABR và congestion control đã triển khai
Phụ lục D. Cấu hình hệ thống thí nghiệm (server, client, network emulator, CDN mock)
