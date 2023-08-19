# Opi_Zero_3_I2S3
Orange Pi Zero 3 ( H618 )  I2S3 digital audio output

This DT overlay activates I2S3 PCM digital audio  output on [Orange Pi Zero 3](http://www.orangepi.org/html/hardWare/computerAndMicrocontrollers/details/Orange-Pi-Zero-3.html)

Place dtbo file in /boot/dtb/sunxi/overlay .\n
Add line "overlays=i2s3" to /boot/orangepiEnv.txt .
Use alsamixer to adjust I2S3 Src  to APBIF_TXDIF2 .
Check with aplay -l . 
