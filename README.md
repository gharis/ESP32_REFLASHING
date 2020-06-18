Reflsahing is required when esp32 device is malfunctioning
eg- continuous rebooting


# ESP32_REFLASHING on Windows 10

### Iinstall python27

### Goto C:\Python27\Scripts folder run pip install esptool 
C:\Python27\Scripts>pip install esptool 


C:\Python27\Scripts>esptool.py 

usage: esptool [-h] [--chip {auto,esp8266,esp32}] [--port PORT] [--baud BAUD] 

               [--before {default_reset,no_reset,no_reset_no_sync}] 

               [--after {hard_reset,soft_reset,no_reset}] [--no-stub] 

               [--trace] [--override-vddsdio [{1.8V,1.9V,OFF}]] 

               {load_ram,dump_mem,read_mem,write_mem,write_flash,run,image_info,make_image,elf2image,read_mac,chip_id,flash_id,read_flash_status,write_flash_status,read_flash,verify_flash,erase_flash,erase_region,version} 
 
esptool: error: too few arguments 


 
### Hold boot button on esp32
### Goto C:\Python27\Scripts folder run esptool.py --chip esp32 erase_flash 
 
 
C:\Python27\Scripts>esptool.py --chip esp32 erase_flash 

esptool.py v2.8 

Found 1 serial ports 

Serial port COM3 

Connecting..... 

Chip is ESP32D0WDQ5 (revision 1) 

Features: WiFi, BT, Dual Core, 240MHz, VRef calibration in efuse, Coding Scheme None 

Crystal is 40MHz 

MAC: 4c:11:ae:b9:90:54 

Uploading stub... 

Running stub... 

Stub running... 

Erasing flash (this may take a while)... 

Chip erase completed successfully in 9.4s 

Hard resetting via RTS pin... 





## Download micropython flashing bin files from https://micropython.org/download/esp32/ 
### Select a stable version download (in my case esp32-idf3-20191220-v1.12.bin)
### Copy the file into C:\Python27\Scripts
### Hold boot button on esp32
### Goto C:\Python27\Scripts folder run esptool.py --chip esp32 --port COM3 write_flash -z 0x1000 esp32-idf3-20191220-v1.12.bin 
 
 
C:\Python27\Scripts>esptool.py --chip esp32 --port COM3 write_flash -z 0x1000 esp32-idf3-20191220-v1.12.bin 

esptool.py v2.8 

Serial port COM3 

Connecting.... 

Chip is ESP32D0WDQ5 (revision 1) 

Features: WiFi, BT, Dual Core, 240MHz, VRef calibration in efuse, Coding Scheme None 

Crystal is 40MHz 

MAC: 4c:11:ae:b9:90:54 

Uploading stub... 

Running stub... 

Stub running... 

Configuring flash size... 

Auto-detected Flash size: 4MB 

Compressed 1247280 bytes to 787794... 

Wrote 1247280 bytes (787794 compressed) at 0x00001000 in 69.9 seconds (effective 142.8 kbit/s)... 

Hash of data verified. 

  

Leaving... 

Hard resetting via RTS pin... 

now esp32 is reflashed 
  
