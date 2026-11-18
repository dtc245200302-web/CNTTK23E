# Bài thực hành: PingSignalR — Giao tiếp thời gian thực với ASP.NET Core SignalR

## 1. Mục tiêu
- Xây dựng máy chủ SignalR (`Ping.Api`) và ứng dụng khách Console (`Ping.Client`).
- Thực hành các cơ chế gửi tin nhắn: Gọi trực tiếp (`Echo`), Gửi nhóm (`JoinGroup`, `SendToGroup`), và Gửi toàn bộ (`Broadcast`).
- Kiểm thử vòng đời kết nối (`OnConnectedAsync`, `OnDisconnectedAsync`) và cơ chế tự động kết nối lại (`WithAutomaticReconnect`).

## 2. Cấu trúc thư mục
- `src/Ping.Api/`: Dịch vụ SignalR Hub tại endpoint `/hubs/ping` (cổng `5200`).
- `src/Ping.Client/`: Ứng dụng Console kết nối tới Hub và thực thi các kịch bản gửi/nhận.

## 3. Hướng dẫn chạy kiểm thử
1. Khởi chạy Server:
   ```bash
   dotnet run --project src/Ping.Api