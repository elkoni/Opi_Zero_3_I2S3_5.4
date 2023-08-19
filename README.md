# Opi_Zero_3_I2S3
Orange Pi Zero 3 ( H618 )  I2S3 digital audio output

This DT overlay activates I2S3 PCM digital audio  output on [Orange Pi Zero 3](http://www.orangepi.org/html/hardWare/computerAndMicrocontrollers/details/Orange-Pi-Zero-3.html)

Place dtbo file in /boot/dtb/sunxi/overlay .\
Add line "overlays=i2s3" to /boot/orangepiEnv.txt .\
Use alsamixer to adjust I2S3 Src  to APBIF_TXDIF2 .\
Check with aplay -l .
~~~
Z3$ aplay -l
**** List of PLAYBACK Hardware Devices ****
card 0: audiocodec [audiocodec], device 0: soc@3000000:codec_plat-5096000.codec 5096000.codec-0 []
  Subdevices: 1/1
  Subdevice #0: subdevice #0
card 2: ahubhdmi [ahubhdmi], device 0: ahub_plat-snd-soc-dummy-dai snd-soc-dummy-dai-0 []
  Subdevices: 1/1
  Subdevice #0: subdevice #0
card 3: ahubi2s3 [ahubi2s3], device 0: ahub_plat-snd-soc-dummy-dai snd-soc-dummy-dai-0 []
  Subdevices: 1/1
  Subdevice #0: subdevice #0
~~~

