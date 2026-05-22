![Cabana screenshot](assets/screenshot.png)

# Cabana

**Cabana is a CAN / CAN FD bus analysis and visualization tool.** Helps decode signals, reverse‑engineer unknown messages, plot time‑series data, and replay recorded drives with synchronized video.

It ships with a built‑in [OpenDBC](https://github.com/commaai/opendbc) database with 50+ vehicle definitions. Works with ASC, candump, TRC logs, SocketCAN, [Panda](https://github.com/commaai/panda), and [openpilot](https://github.com/commaai/openpilot) routes. MIT licensed.

Originally developed as the CAN analysis tool for **[openpilot](https://github.com/commaai/openpilot)**, Cabana is now maintained independently as a standalone general-purpose analyzer.

## Installation

### Arch Linux (AUR)

```bash
paru -S openpilot-cabana
```

Or manually:

```bash
git clone https://aur.archlinux.org/openpilot-cabana.git
cd openpilot-cabana
makepkg -s
pacman -U openpilot-cabana-*.pkg.tar.zst
```

### Other Linux

Download a precompiled binary from the [Releases](https://github.com/deanlee/openpilot-cabana/releases) page:

```bash
chmod +x cabana-linux-x86_64
./cabana-linux-x86_64 --demo
```

### Build from Source

See [Prerequisites](#prerequisites) and [Clone, Compile](#clone-compile) below.

### Prerequisites

Before running or compiling **openpilot-cabana**, install these dependencies.

### Arch Linux (AUR)

If you are on Arch Linux, you can install Cabana directly from the AUR:

```bash
yay -S openpilot-cabana
```

### Ubuntu / Debian

```bash
sudo apt update
sudo apt install -y g++ clang capnproto libcurl4-openssl-dev libzmq3-dev libssl-dev libbz2-dev libavcodec-dev libavformat-dev libavutil-dev libswscale-dev libavdevice-dev libavfilter-dev libffi-dev libgles2-mesa-dev libglfw3-dev libglib2.0-0 libjpeg-dev libncurses5-dev libusb-1.0-0-dev libzstd-dev libcapnp-dev libx11-dev libxcb1-dev libxcb-xinerama0-dev libxcb-cursor-dev opencl-headers ocl-icd-libopencl1 ocl-icd-opencl-dev qt6-base-dev qt6-tools-dev qt6-tools-dev-tools libqt6charts6-dev libqt6svg6-dev libqt6serialbus6-dev libqt6opengl6-dev

```

## Clone, Compile

### Ubuntu / Debian

```bash
sudo apt update
sudo apt install -y g++ clang capnproto libcurl4-openssl-dev libzmq3-dev libssl-dev libbz2-dev libavcodec-dev libavformat-dev libavutil-dev libswscale-dev libavdevice-dev libavfilter-dev libffi-dev libgles2-mesa-dev libglfw3-dev libglib2.0-0 libjpeg-dev libncurses5-dev libusb-1.0-0-dev libzstd-dev libcapnp-dev libx11-dev libxcb1-dev libxcb-xinerama0-dev libxcb-cursor-dev opencl-headers ocl-icd-libopencl1 ocl-icd-opencl-dev qt6-base-dev qt6-tools-dev qt6-tools-dev-tools libqt6charts6-dev libqt6svg6-dev libqt6serialbus6-dev libqt6opengl6-dev
```

### Build

```bash
git clone https://github.com/deanlee/openpilot-cabana.git
cd openpilot-cabana
git submodule update --init --recursive
python3 -m pip install --upgrade pip
python -m pip install --no-cache-dir scons numpy "cython>=3.0" setuptools pycapnp
scons
```

## Usage

```bash
./cabana                              # Interactive stream selector
./cabana --demo                       # Built-in demo route
./cabana "route-id"                   # Load a specific route
./cabana --zmq <ip>                   # Stream from comma device
./cabana --panda                      # Read from connected Panda
./cabana file.log                     # Open a candump/ASC/TRC log file
```

Find your routes at [connect.comma.ai](https://connect.comma.ai).

## Contributors

<a href="https://github.com/deanlee/openpilot-cabana/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=deanlee/openpilot-cabana" />
</a>
