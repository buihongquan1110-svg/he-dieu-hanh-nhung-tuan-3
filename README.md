# TUẦN 3: QUY TRÌNH BUILD ROOT FILESYSTEM VỚI BUSYBOX
# Bước 1: Cài công cụ trên máy ảo
```bash
sudo apt update
sudo apt install build-essential gcc-arm-linux-gnueabihf libncurses-dev wget
```
- Kiểm tra cross complier:
```bash
arm-linux-gnueabihf-gcc -v
```
- Nếu hiện version thì đã cài đúng

# Bước 2: Tải BusyBox
```bash
wget https://busybox.net/downloads/busybox-1.36.1.tar.bz2
tar -xjf busybox-1.36.1.tar.bz2
cd busybox-1.36.1
```
# Bước 3: Cấu hình Busybox
```bash
make ARCH=arm CROSS_COMPILE=arm-linux-gnueabihf- menuconfig
```
- Vào:
```bash
Settings →
  [*] Build BusyBox as a static binary (no shared libs)
```
<img width="1920" height="1080" alt="Screenshot from 2026-03-10 22-37-50" src="https://github.com/user-attachments/assets/b46ae8f5-a3de-4403-af9e-731c0faf5657" />

- Bấm Space để chọn
- Save → Exit

# Bước 4: Complie 
```bash
make -j4 ARCH=arm CROSS_COMPILE=arm-linux-gnueabihf-
```
- Chờ complie xong
- Kiểm tra có file busybox chưa:
```bash
ls busybox
```
- Nếu thấy file busybox là đúng

# Bước 5: Tạo thư mục rootfs
```bash
cd ~
mkdir rootfs
```

# Bước 6: Install BusyBox vào rootfs
- Chạy:
```bash
make ARCH=arm CROSS_COMPILE=arm-linux-gnueabihf- CONFIG_PREFIX=~/rootfs install
```
# Bước 7: Kiểm tra kết quả 
<img width="1927" height="2560" alt="image" src="https://github.com/user-attachments/assets/4856f0e0-8e0d-4d9d-9cf6-056716bd8c87" />
<img width="2561" height="1921" alt="image" src="https://github.com/user-attachments/assets/bf372017-f984-4436-b023-2e487684e6cc" />

Link video làm trên BBB: https://drive.google.com/drive/folders/17RH8gHqSrV-o-5OysdLAjEZQAFoqVZwK


