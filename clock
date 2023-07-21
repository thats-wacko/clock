
import machine
from lcd_lib import LCD_1inch3
from machine import Pin,SPI,PWM
import framebuf
import utime

def colour(R,G,B):
    return (((G&0b00011100)<<3) +((B&0b11111000)>>3)<<8) + (R&0b11111000)+((G&0b11100000)>>5)

LCD = LCD_1inch3()
LCD.fill(LCD.black)

LCD.show()

c=colour(0,0,200)



#minute = 32
#hour = 23                                         #uncomment these to change the time!!!
#second = 53

#LCD.write_text("20/07/2023",44,70,2,LCD.white)    #change this according to the date

LCD.write_text(":",83,105,3,LCD.white)
LCD.write_text(":",142,105,3,LCD.white)
LCD.fill_rect(160,101,55,29, LCD.black)
LCD.fill_rect(95,101,55,29, LCD.black)
LCD.fill_rect(35,101,55,29, LCD.black)
LCD.write_text(str(minute),100,105,3,LCD.white)
LCD.write_text(str(hour),40,105,3,LCD.white)

LCD.show()

for i in range(24):
    for i in range(60):
        for i in range (60):
            c=colour(0,0,200)
            LCD.fill_rect(154,101,55,29, LCD.black)
            if second < 10:
                LCD.write_text("0"+str(second),160,105,3,LCD.white)
                LCD.show()
            if second > 9:
                LCD.write_text(str(second),160,105,3,LCD.white)
                LCD.show()
            #print(hour)
            print(minute)
            utime.sleep(0.9738)
            second = second + 1
            #print(second)
            if  second > 59:
                minute = minute + 1
                second = second - 60
                LCD.fill_rect(95,101,55,29, LCD.black)
                if minute < 10:
                    LCD.write_text("0"+str(minute),100,105,3,LCD.white)
                    LCD.show()
                if minute > 9:
                    LCD.write_text(str(minute),100,105,3,LCD.white)
                    LCD.show()
                print("minute")
                LCD.show()
                if  minute > 59:
                    minute = minute - 60
                    LCD.fill_rect(95,101,55,29, LCD.black)   
                    LCD.write_text("0"+str(minute),100,105,3,LCD.white)
                    hour = hour + 1
                    LCD.fill_rect(35,101,55,29, LCD.black)
                    if hour < 10:
                        LCD.write_text("0"+str(hour),40,105,3,LCD.white)
                        LCD.show()
                    if hour > 9:
                        LCD.write_text(str(hour),40,105,3,LCD.white)
                        LCD.show()
                    print("hour")
                    LCD.show()
                    if hour > 23:
                        hour = 0
                        LCD.fill_rect(35,101,55,29, LCD.black)
                        LCD.show()
                        LCD.write_text("0"+str(hour),40,105,3,LCD.white)
                        LCD.show()
                        print("day")
                    
