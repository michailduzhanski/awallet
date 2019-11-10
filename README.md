ArnakWallet is a z-Addr first, Sapling compatible wallet and full node for arnakd that runs on Linux, Windows and macOS.

![Screenshot](docs/screenshot-main.png?raw=true)
![Screenshots](docs/screenshot-sub.png?raw=true)
# Installation

Head over to the releases page and grab the latest installers or binary. https://github.com/michailduzhanski/awallet/releases

### Linux

If you are on Debian/Ubuntu, please download the `.deb` package and install it.
```
sudo dpkg -i linux-deb-arnakwallet-v0.7.6.deb
sudo apt install -f
```

Or you can download and run the binaries directly.
```
tar -xvf arnakwallet-v0.7.6.tar.gz
./arnakwallet-v0.7.6/arnakwallet
```

### Windows
Download and run the `.msi` installer and follow the prompts. Alternately, you can download the release binary, unzip it and double click on `arnakwallet.exe` to start.

### macOS
Double-click on the `.dmg` file to open it, and drag `arnakwallet` on to the Applications link to install.

## arnakd
ArnakWallet needs a Arnak node running arnakd. If you already have a arnakd node running, ArnakWallet will connect to it. 

If you don't have one, ArnakWallet will start its embedded arnakd node. 

Additionally, if this is the first time you're running ArnakWallet or a arnakd daemon, ArnakWallet will download the arnak params (~1.7 GB) and configure `arnak.conf` for you. 

Pass `--no-embedded` to disable the embedded arnakd and force ArnakWallet to connect to an external node.

## Compiling from source
ArnakWallet is written in C++ 14, and can be compiled with g++/clang++/visual c++. It also depends on Qt5, which you can get from [here](https://www.qt.io/download). Note that if you are compiling from source, you won't get the embedded arnakd by default. You can either run an external arnakd, or compile arnakd as well. 

See detailed build instructions [on the wiki](https://github.com/michailduzhanski/awallet/wiki/Compiling-from-source-code)

### Building on Linux

```
git clone https://github.com/michailduzhanski/awallet.git
cd arnakwallet
/path/to/qt5/bin/qmake zec-qt-wallet.pro CONFIG+=debug
make -j$(nproc)

./arnakwallet
```

### Building on Windows
You need Visual Studio 2017 (The free C++ Community Edition works just fine). 

From the VS Tools command prompt
```
git clone  https://github.com/michailduzhanski/awallet.git
cd arnakwallet
c:\Qt5\bin\qmake.exe zec-qt-wallet.pro -spec win32-msvc CONFIG+=debug
nmake

debug\arnakwallet.exe
```

To create the Visual Studio project files so you can compile and run from Visual Studio:
```
c:\Qt5\bin\qmake.exe zec-qt-wallet.pro -tp vc CONFIG+=debug
```

### Building on macOS
You need to install the Xcode app or the Xcode command line tools first, and then install Qt. 

```
git clone https://github.com/michailduzhanski/awallet.git
cd arnakwallet
/path/to/qt5/bin/qmake zec-qt-wallet.pro CONFIG+=debug
make

./arnakwallet.app/Contents/MacOS/arnakwallet
```

### [Troubleshooting Guide & FAQ](https://github.com/michailduzhanski/awallet/wiki/Troubleshooting-&-FAQ)
Please read the [troubleshooting guide](https://arnak.com) for common problems and solutions.
For support or other questions, tweet at [@arnakwallet](https://twitter.com/arnak) or [file an issue](https://github.com/michailduzhanski/awallet/issues).

_PS: ArnakWallet is NOT an official wallet, and is not affiliated with the Electric Coin Company in any way._
