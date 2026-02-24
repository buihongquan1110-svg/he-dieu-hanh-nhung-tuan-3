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
