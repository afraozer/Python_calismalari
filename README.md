import  requests #web uzerinde isteklerimizi yönetmek icin kullaniriz
from bs4 import BeautifulSoup #bilgi kazımak Bilgi kazımak istediğimiz web sitesinden veriyi  cekerken kullaniriz
import tkinter as tk #tkinter olusturmak icin ice aktardik 

url= "https://www.doviz.com/" #verileri aldigimiz urlyi gireriz
r=requests.get(url)
soup=BeautifulSoup(r.content,"html.parser") 
data1= soup.find("span",{"data-socket-key":"gram-altin"}).text 
data2 = soup.find("span",{"data-socket-key":"USD"}).text
window= tk.Tk()
data3= soup.find("span",{"data-socket-key":"EUR"}).text
data4= soup.find("span",{"data-socket-key":"GBP"}).text
data5= soup.find("span",{"data-socket-key":"XU100"}).text
#değişkenleri web sitesinden incele kismindan data-socket-key kismini kopyalayarak elde ederiz

window.geometry("310x270")#önümüze acilacak pencerenin olculerini belirleriz
window.title("Borsa")#önümüze acilacak pencerenin adini belirleriz
window.configure(background="purple") #önümüze acilacak pencerenin arkaplan rengini belirleriz

label=tk.Label(window,text="Borsa", font="arial 15 bold", bg="purple") #tkinterın başlıgını adını,yazi fontunu ve backgroundunu belirleriz
label.pack()

gramaltin=tk.Label(window,text="Gram Altin",font="arial 12", bg="purple")#gram altin yazisinin ,yazi fontunu ve backgroundunu belirleriz
gramaltin.pack()
gramaltin.place(x=30,y=45)#gram altin yazisinin konumunu belirleriz
goldvalue= tk.Label(window,text=data1,font="arial 12",bg="purple")#gram altin degerinin ,yazi fontunu ve backgroundunu belirleriz
goldvalue.pack()
goldvalue.place(x=30,y=65)#gram altin degerinin yazisinin yerinin konumunu belirleriz

dolar=tk.Label(window,text="dolar",font="arial 12", bg="purple")
dolar.pack()
dolar.place(x=200,y=45)
dolarvalue= tk.Label(window,text=data2,font="arial 12",bg="purple")
dolarvalue.pack()
dolarvalue.place(x=200,y=65)

euro=tk.Label(window,text="Euro",font="arial 12", bg="purple")
euro.pack()
euro.place(x=20,y=115)
eurovalue= tk.Label(window,text=data3,font="arial 12", bg="purple")
eurovalue.pack()
eurovalue.place(x=30,y=135)

sterlin=tk.Label(window,text="Sterlin",font="arial 12", bg="purple")
sterlin.pack()
sterlin.place(x=200,y=115)
sterlinvalue= tk.Label(window,text=data4,font="arial 12", bg="purple")
sterlinvalue.pack() 
sterlinvalue.place(x=200,y=135)

bist=tk.Label(window,text="Bist 100",font="arial 12", bg="purple")
bist.pack()
bist.place(x=200,y=185)
bistvalue= tk.Label(window,text=data5,font="arial 12", bg="purple")
bistvalue.pack()
bistvalue.place(x=200,y=205)

window.mainloop()
