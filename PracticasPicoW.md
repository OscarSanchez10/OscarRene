## 2.1 - Práctica Hola Mundo

<div style="text-align:center">
 <img src="https://scontent.ftij5-1.fna.fbcdn.net/v/t1.15752-9/370211712_702032104719134_6626550141145375390_n.jpg?_nc_cat=110&ccb=1-7&_nc_sid=8cd0a2&_nc_eui2=AeG1vCfvSbqEBYpWp4PkX1RJ7wuuBa9K8MfvC64Fr0rwx1umi5WXcMWFfu38QwJY8xCCsrg7UBoS3fAME-YQ7rWD&_nc_ohc=hPtg7o2L218AX88pAdB&_nc_ht=scontent.ftij5-1.fna&oh=03_AdRhgT6smaYEiGW6jWLOKSLNMfwXljsKxh3oSCTPtTeXRw&oe=654DAFA8" width="600" height="600" />
</div>

```
from machine import Pin, I2C
from ssd1306 import SSD1306_I2C

WIDTH = 128
HEIGHT = 64

i2c = I2C(0, scl=Pin(1), sda=Pin(0), freq=200000)
oled = SSD1306_I2C(WIDTH, HEIGHT, i2c)
oled.text("Hola Mundo!", 0, 0)
oled.show()
```


## 2.1.2 - Desplegar la hora de internet

<div style="text-align:center">
 <img src="https://scontent-sjc3-1.xx.fbcdn.net/v/t1.15752-9/370148795_3520742031518351_6059106492781991160_n.jpg?_nc_cat=103&ccb=1-7&_nc_sid=8cd0a2&_nc_eui2=AeHMKaTH2hnh_N86zF2UW0AgdimOryETpqd2KY6vIROmp2StmM44EgE4qowacI9zwhDYwTO2HB8Sql7fpdqeB8an&_nc_ohc=PqMLq_65OXkAX_MNkQk&_nc_ht=scontent-sjc3-1.xx&oh=03_AdTRJsIF-Fm-lKh8r2mrRhyB4GCu5sF3waRl5kFqx1YbJw&oe=654D9EC4"/>
</div>

```
import ntptime
import time

from machine import Pin, I2C
from ssd1306 import SSD1306_I2C

i2c=I2C(0,sda=Pin(0), scl=Pin(1), freq=400000)
oled = SSD1306_I2C(128, 64, i2c)

ntp_server = "pool.ntp.org"

try:
    ntptime.settime()
    print("Hora de internet obtenida.")
except Exception as e:
    print("Error al obtener la hora:", e)

rtc_time = time.localtime()
print("Hora actual: {}/{}/{} {}:{}:{}".format(
    rtc_time[1], rtc_time[2], rtc_time[0],
    rtc_time[3], rtc_time[4], rtc_time[5]))

oled.text("{}/{}/{} {}:{}:{}".format(
    rtc_time[1], rtc_time[2], rtc_time[0],
    rtc_time[3], rtc_time[4], rtc_time[5]),0,0)
oled.show()
```
