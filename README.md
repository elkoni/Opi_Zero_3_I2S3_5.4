# Opi_Zero_3_I2S3
Orange Pi Zero 3 ( H618 )  I2S3 digital audio output

This DT overlay activates I2S3 PCM digital audio  output on [Orange Pi Zero 3](http://www.orangepi.org/html/hardWare/computerAndMicrocontrollers/details/Orange-Pi-Zero-3.html)

Place dtbo file in /boot/dtb/sunxi/overlay .\
Add line "overlays=i2s3" to /boot/orangepiEnv.txt .\
Use alsamixer to adjust I2S3 Src  to APBIF_TXDIF2 ( see JPG ) .\
Check with aplay -l:
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
Connect external digital to analog converter board with I2S format input.\
Use following pins : \
Pin 25 - GND --> signal GND of DAC board\
Pin 23 - PH6 --> I2S BCK \
Pin 21 - PH8 --> I2S DATA \
Pin 19 - PH7 --> I2S LRCK \
Pin 2  - 5V  --> to +5V power of DAC board\  
Pin 6  - GND --> to GND power of DAC board\

The signal levels are 3.3V .

Test with sox :
~~~
 AUDIODEV=hw:3,0 play -V -r 48000 -n -b 16 -c 2 synth sin 440 vol -12dB
~~~
