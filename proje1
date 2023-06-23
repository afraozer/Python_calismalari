# Python_calismalari
import configparser
import time #ekran suresi icin time'ı ice aktardik
from selenium import webdriver 
import os
import pyautogui #ekran goruntusu almak icin pyautogui ice aktardik

driver= webdriver.Chrome() ^#web tarayıcımızı chrome uzerinden gereceklestiricez
url ='https://www.google.com/'
driver.get(url)

driver.maximize_window() #ekranı buyutmek icin 

url= 'https://www.youtube.com/'
driver.get(url)


url='https://www.youtube.com/watch?v=NzsDd4IytEk'
driver.get(url)
time.sleep(4)

ekran_goruntusu = pyautogui.screenshot()
dosya_adi = "odev_1.jpg"
dosya_yolu = os.path.join('C:\\Users\AFRANUR\Desktop', dosya_adi)#dosyayi kayit edecegimiz yeri belirledik
ekran_goruntusu.save(dosya_yolu)

driver.close()

#22. satir dosya_yolu icim girilen AFRANUR kullanici adini kendi windows kullanici adiniz ile deistiriniz.
