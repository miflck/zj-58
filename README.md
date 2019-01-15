zj-58
=====

CUPS filter for thermal printer Zjiang ZJ-58

The linux driver provided on Zjiang site unfortunately doesn't work.
First, it is 32-bit binary (and so, on x64 system need some x86 libs to be installed).
Second, it's PPD is not correct - it just doesn't show any advanced settings because of it.
Finally, raster filter just crashes on any try to run it!
But even if you run it, you'll see that it's working with printer is not optimal: for example, if it sees a blank line, it will send the blank raster to print (instead of just use 'feeding' command, which is definitely faster!)

This is the solution:
PPD is fixed and works.
Filter is provided as src (you can found a list of packages need to be installed in order to build it in the header of source).
Also, printing of blank lines is optimized.


## Osx install:
http://scruss.com/blog/2015/07/12/thermal-printer-driver-for-cups-linux-and-raspberry-pi-zj-58/

### compile:
cd zj-58/
make

### install
sudo ./install

### Add printer:
go to http://localhost:631/printers
type in terminal: cupsctl WebInterface=yes
add printer from webinterface and select ppd from
/etc/cups/ppd
