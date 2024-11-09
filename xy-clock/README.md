# XY-Clock


## Example commands
```
#port=/dev/tty.usbserial-B001V5Z7
port=COM4
esptool -b 9600 -p $port read_flash 0x00000 "$rombytesize" backup-xy-clock."$rombytesize"."$(date +%Y%m%d%H%M)".bin
```

