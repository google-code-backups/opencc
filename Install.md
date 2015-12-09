# OpenCC #

## Windows ##

解壓後即可在命令行下使用，請確保輸入文件的編碼為UTF-8。

## Mac OS X ##

安裝[homebrew](http://mxcl.github.com/homebrew/)，並在終端下執行：

```
brew install opencc
```

## Ubuntu ##

如果你正在使用Ubuntu 10.10 (Maverick) 以上的版本，opencc已經被加入到了[官方源](https://launchpad.net/ubuntu/+source/opencc)中，使用

```
sudo apt-get install opencc
```

如果你更願意體驗最新的版本，請使用ppa：

```
sudo add-apt-repository ppa:byvoid-kcp/ppa
sudo apt-get update
sudo apt-get install opencc
```

## Debian ##

用法同ubuntu
你可以在 http://packages.debian.org/opencc 找到最新的打包。

## Fedora ##

```
yum install opencc
```


## archlinux ##

```
yaourt -S opencc
```

http://aur.archlinux.org/packages.php?ID=40433

## gentoo ##

http://packages.gentoo.org/package/app-i18n/opencc

## 編譯源碼包 ##

### POSIX ###

  1. 到 http://code.google.com/p/opencc/downloads/list 下載最新版本
  1. 解壓縮並進入目錄

```
mkdir build
cd build
cmake -DCMAKE_INSTALL_PREFIX=/usr -DCMAKE_BUILD_TYPE=Release -D ENABLE_GETTEXT:BOOL=ON ..
make
sudo make install
```

**如果不需要本地化，請設置 ENABLE\_GETTEXT:BOOL=OFF**

### Windows ###

**您需要安裝MSYS平臺和cmake，然後在命令行下執行下列命令**

```
mkdir build
cd build
cmake .. -G "MSYS Makefiles" -DCMAKE_INSTALL_PREFIX="" -DCMAKE_BUILD_TYPE=Release -DENABLE_GETTEXT:BOOL=OFF
make
```

# Node.js #

安裝前，請確保你已經安裝了Node.js 0.8.20以上的版本，並且node-gyp的版本在0.8.4以上。在命令行下運行即可安裝：

```
npm install opencc
```

# opencc-php #

  1. 到 http://code.google.com/p/opencc/downloads/list 下載最新版本
  1. 解壓縮並進入目錄
  1. 安裝php5-dev工具

```
phpize
./configure
make
sudo make install
```

# ropencc #

ropencc是opencc的ruby語言綁定，具體配置和使用方法請見

https://github.com/Psli/ropencc