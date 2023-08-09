import datetime
from time import sleep
from tkinter import *
from tkinter.ttk import *
from tkinter import messagebox
import winsound 


def my_alarm():
    required = f"{required_hours.get()}:{required_minutes.get()}:{required_seconds.get()}"
    while True:
        sleep(1)
        times = datetime.datetime.now().strftime("%H:%M:%S")
        if times == required:
            
            awake = Label(window,text="WAKE UP NOW!",font=('Arial 18 bold'),background="blue",foreground="white")
            awake.place(x=220,y=230)

            frequency = 500
            duration = 1600
            winsound.Beep(frequency,duration)

            break    

window = Tk(className='Alarm clock')
#window size
window.geometry("500x300")
window.configure(bg="lightskyblue")
label_a = Label(window,text="when do you want to wake up",foreground="blue",background="lightskyblue",font="Arial").place(x=120,y=20)
#when you want to wake up
required_hours = StringVar()
required_minutes = StringVar()
required_seconds = StringVar()
#import the image
img = PhotoImage(file= r"c:\Users\H&M\Downloads\icons8-clock-64.png")
image = Label(window,image= img,background= "lightskyblue").place(x= 40, y= 80)
#import the combobox 
hours = Label(window,text="Hours",background="blue",foreground="white",font=('Arial 12 bold')).place(x=150,y=85)
date_hours = Entry(window,textvariable= required_hours ,background="white",foreground="blue",width=8).place(x=150,y=120)

minutes = Label(window,text="Minutes",background="blue",foreground="white",font=('Arial 12 bold')).place(x=220,y=85)
date_minutes = Entry(window,textvariable= required_minutes ,background="white",foreground="blue",width=9).place(x=220,y=120)

seconds = Label(window,text="Seconds",background="blue",foreground="white",font=('Arial 12 bold')).place(x=290,y=85)
date_seconds = Entry(window,textvariable= required_seconds ,background="white",foreground="blue",width=9).place(x=290,y=120)
#the button to set the alarm
set_button = Button(window, text="Set my alarm",command=my_alarm).place(x= 230,y= 180)


window.mainloop() 
