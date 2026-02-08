# General

Download as zip, unzip, and run `sudo ./install.sh`.
https://github.com/ZeptByteS/dvorak-qwerty/tree/develop

Downloading ghostty:

```bash
snap install ghostty --classic
```

Downloading VS Code: https://code.visualstudio.com/download

- `.deb` Arm64

# Intel RealSense SDK 2.0

## On Linux (Ubuntu)

### 1. Install dependencies

```bash
sudo apt update
sudo apt install -y git cmake build-essential pkg-config \
libgtk-3-dev libgl1-mesa-dev libglu1-mesa-dev libusb-1.0-0-dev \
libudev-dev libssl-dev libglfw3-dev libopencv-dev ffmpeg
```

### 2. Clone the librealsense repo

```bash
cd ~
git clone [https://github.com/IntelRealSense/librealsense.git](https://github.com/IntelRealSense/librealsense.git)
cd librealsense
```

### 3. Create a build folder

```bash
mkdir build && cd build
```

### 4. Configure the build

```bash
cmake ../ -DCMAKE_BUILD_TYPE=Release -DBUILD_EXAMPLES=true
```

### 5. Compile

```bash
make -j$(nproc)
```

### 6. Install

```bash
sudo make install
sudo ldconfig
```

### 7. Test the installation

```bash
realsense-viewer
```

```bash
rs-enumerate-devices
```
