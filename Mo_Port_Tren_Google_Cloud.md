# Mở port trên Google Cloud cho VPS
Thao tác theo các bước dưới đây

Mở giao diện FireWall rules
------------
 - Nhấn vào Menu Google Cloud Platform góc trên bên phải.
 - Chọn VPC Network.
 - Chọn FireWall rules

Tạo Rule
------------
Nhấn vào CREATE FIREWALL RULE để tạo rule mới.
- Name: Đặt tên Rule
- Target: Chuyển sang All instance in the network
- Source IP Range: 0.0.0.0/0
- Protocols and ports: Chọn all để mở toàn bộ các port (không nên), hoặc tích vào ô TCP và mở một port được chỉ định.
Nhấn CREATE để hoàn thành tạo rule mới.

