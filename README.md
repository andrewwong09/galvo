# galvo
Galvo controller


# Dependencies
- [Comedi](https://www.comedi.org/index.html)

## Setting up Comedi on Ubuntu 22.04

```
git clone https://github.com/Linux-Comedi/comedi.git
sudo apt install autoconf
./autogen.sh
./configure
make
sudo make install

git clone https://github.com/Linux-Comedi/comedi-nonfree-firmware.git
sudo apt install libtool // error: possibly undefined macros AC_PROG_LIBTOOL
./autogen.sh
./configure --with-udev-hotplug=/lib --sysconfdir=/etc~
make
sudo apt install flex  // error: missing flex tool
sudo apt-get install bison -y  // errro: missing yacc tool
sudo make install
```

## Testing comedi compiling
```
cc comedi_test.c -lcomedi -LLIBDIR -lm -o comedi_test
LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/local/lib
export LD_LIBRARY_PATH
sudo chmod 777 /dev/comedi0
./comedi_test
```

# Hardware
- National Instruments PCI-6251
