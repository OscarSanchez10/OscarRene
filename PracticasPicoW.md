## 2.1 - Práctica Hola Mundo

 <img src="[https://scontent.ftij5-1.fna.fbcdn.net/v/t1.15752-9/370279235_626775489620257_7755814948557268879_n.jpg?_nc_cat=103&ccb=1-7&_nc_sid=8cd0a2&_nc_eui2=AeFmtTfd020UQ-sSeHph_KKoi1iAV_jHDuuLWIBX-McO66cLcjB_Eq0Yvp3e-KsTvd13MyRspo4AbCy9jp4GUWsa&_nc_ohc=LLaCCJsfPdAAX8IVEwG&_nc_ht=scontent.ftij5-1.fna&oh=03_AdRcVGCZGaCsX8_oaPS_IxFgKH0TDXXiaqd0JD8cgOUyng&oe=654DB1C5](https://scontent.ftij5-1.fna.fbcdn.net/v/t1.15752-9/370211712_702032104719134_6626550141145375390_n.jpg?_nc_cat=110&ccb=1-7&_nc_sid=8cd0a2&_nc_eui2=AeG1vCfvSbqEBYpWp4PkX1RJ7wuuBa9K8MfvC64Fr0rwx1umi5WXcMWFfu38QwJY8xCCsrg7UBoS3fAME-YQ7rWD&_nc_ohc=hPtg7o2L218AX88pAdB&_nc_ht=scontent.ftij5-1.fna&oh=03_AdRhgT6smaYEiGW6jWLOKSLNMfwXljsKxh3oSCTPtTeXRw&oe=654DAFA8)https://scontent.ftij5-1.fna.fbcdn.net/v/t1.15752-9/370211712_702032104719134_6626550141145375390_n.jpg?_nc_cat=110&ccb=1-7&_nc_sid=8cd0a2&_nc_eui2=AeG1vCfvSbqEBYpWp4PkX1RJ7wuuBa9K8MfvC64Fr0rwx1umi5WXcMWFfu38QwJY8xCCsrg7UBoS3fAME-YQ7rWD&_nc_ohc=hPtg7o2L218AX88pAdB&_nc_ht=scontent.ftij5-1.fna&oh=03_AdRhgT6smaYEiGW6jWLOKSLNMfwXljsKxh3oSCTPtTeXRw&oe=654DAFA8">
    
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


