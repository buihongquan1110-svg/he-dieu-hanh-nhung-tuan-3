# TUẦN 3: QUY TRÌNH BUILD ROOT FILESYSTEM VỚI BUSYBOX
# Bước 1: Cài công cụ trên máy ảo

`"sudo apt update"`

`"sudo apt install build-essential gcc-arm-linux-gnueabihf libncurses-dev wget"`

- Kiểm tra cross complier:

`"arm-linux-gnueabihf-gcc -v"`

- Nếu hiện version thì đã cài đúng

# Bước 2: Tải BusyBox

`"wget https://busybox.net/downloads/busybox-1.36.1.tar.bz2"`

`"tar -xjf busybox-1.36.1.tar.bz2"`

`"cd busybox-1.36.1"`

# Bước 3: Cấu hình Busybox
`"make ARCH=arm CROSS_COMPILE=arm-linux-gnueabihf- menuconfig"`

- Vào:
Settings →


  [*] Build BusyBox as a static binary (no shared libs)

- Bấm Space để chọn
- Save → Exit

# Bước 4: Complie 
`"make -j4 ARCH=arm CROSS_COMPILE=arm-linux-gnueabihf-"`

- Chờ complie xong
- Kiểm tra có file busybox chưa:
`"ls busybox"`
- Nếu thấy file busybox là đúng

# Bước 5: Tạo thư mục rootfs
`"cd ~"`
`"mkdir rootfs"`

# Bước 6: Install BusyBox vào rootfs
- Chạy:
`"make ARCH=arm CROSS_COMPILE=arm-linux-gnueabihf- CONFIG_PREFIX=~/rootfs install"`
# Bước 7: Kiểm tra kết quả 
<img width="1927" height="2560" alt="image" src="https://github.com/user-attachments/assets/4856f0e0-8e0d-4d9d-9cf6-056716bd8c87" />
<img width="2561" height="1921" alt="image" src="https://github.com/user-attachments/assets/bf372017-f984-4436-b023-2e487684e6cc" />

Link video làm trên BBB: https://drive.google.com/drive/folders/17RH8gHqSrV-o-5OysdLAjEZQAFoqVZwK


