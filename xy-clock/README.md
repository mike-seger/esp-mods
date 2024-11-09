# XY-Clock


## Example commands
```
# Globals
#port=/dev/tty.usbserial-B001V5Z7
port=COM4

# Get Flash Size
rombytesize=$(( 1048576 * $(esptool.py --port /dev/cu.usbserial-1481130 flash_id | grep "flash size:" | sed 's/.*\([0-9+]\).*/\1/') ))
# e.g. 
rombytesize=0x200000

# Backup Flash
esptool -b 9600 -p $port read_flash 0x00000 "$rombytesize" backup-xy-clock."$rombytesize"."$(date +%Y%m%d%H%M)".bin

# Restore Flash
esptool.py --port /dev/cu.usbserial-1481130 write_flash 0x00000 firmwarebackup.bin 

```

## Links
- [clock case](https://www.thingiverse.com/thing:6361178#google_vignette)
- [EspHome-Led-Clock](https://github.com/trip5/EspHome-Led-Clock)
- [XY-Clock](https://templates.blakadder.com/XY-Clock.html)
- [303WIFILC01](https://github.com/maarten-pennings/303WIFILC01)
