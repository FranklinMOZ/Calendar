# Simple Tkinter Calendar

import tkinter as ui
import calendar

window = ui.Tk()
window.title("Python Calendar") # Title of the window
window.geometry("300x260")
window.resizable(0,0)

def show():
    a = int(spin1.get())
    b = int(spin2.get())
    calendar.setfirstweekday(calendar.SUNDAY)

    cal = calendar.month(b,a)
    
    txt.delete(0.0, ui.END)
    txt.insert(ui.INSERT,cal)

lbl1 = ui.Label(window, text="Month", font="Calibri 9 bold").place(x=40,y=2)
lbl2 = ui.Label(window, text="Year", font="Calibri 9 bold").place(x=180,y=2)

spin1 = ui.Spinbox(window, values=(1,2,3,4,5,6,7,8,9,10,11,12),width=4)
spin1.place(x=90,y=2)

spin2 = ui.Spinbox(window, from_=1990,to_=2100,width=4)
spin2.place(x=210,y=2)

btn = ui.Button(window,text="Show",font="Calibri 9 bold",command=show).place(x=140,y=30)

txt = ui.Text(window, width=31,height=12)
txt.place(x=20,y=57)

window.mainloop()
