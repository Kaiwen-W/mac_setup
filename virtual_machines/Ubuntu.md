# General

Download as zip, unzip, and run `sudo ./install.sh`.
https://github.com/ZeptByteS/dvorak-qwerty/tree/develop

Downloading ghostty:

```bash
snap install ghostty --classic
```

Downloading VS Code: https://code.visualstudio.com/download

- `.deb` Arm64

## Using a Shared Directory

Configure UTM (Host) Settings:

1. Right-click your Ubuntu VM in the UTM main window and select Edit.

2. Navigate to the Sharing tab in the sidebar.

3. Under Directory Share Mode, select VirtFS.

4. Click Browse... at the bottom and select the folder on your macOS host that you want to share.

5. Click Save.

Mount the Directory in Ubuntu (Guest):

1. Create a directory to serve as the mount point (e.g. `Shared` in the home folder):

```bash
mkdir ~/Shared
```

2. Mount the shared folder using the `virtfs` filesystem type

```bash
sudo mount -t 9p -o trans=virtio,version=9p2000.L share /home/$USER/Shared
```

3. Allow to read to shared folder by changing ownership inside the VM

```bash
sudo chown -R "$USER:$USER" /home/kwang/Shared
```

4. Allow Ubuntu to auto-mount the UTM shared folder at boot

   ```bash
   sudo nano /etc/fstab
   ```

   Then paste the following into it:

   ```txt
   share /home/$USER/Shared 9p trans=virtio,version=9p2000.L,rw,_netdev,nofail 0 0
   ```

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
