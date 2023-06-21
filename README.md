from tkinter import * 
from tkinter.font import BOLD
from tkinter import messagebox
import random
window=Tk() 
frame1=Frame(window,pady=50) 
frame1.pack() 
window.title("login page") 
window.geometry('750x350') 
text = 'abcdefghijklmnopqrstuvwxyz0123456789'
captcha = StringVar() 
input = StringVar() 
def create_captcha(): 
 c = random.choices(text, k = 6) 
 captcha.set(''.join(c)) 
def check(): 
 if captcha.get() == input.get(): 
 messagebox.showinfo('Captcha Verification', 'Captcha verified 
Succesfully..') 
 else: 
 messagebox.showerror('Captcha Verification', 'Incorrect Captcha') 
 input.set('') 
 create_captcha() 
regno=Label(frame1,text="Enter Regstration No.:",font=('times new 
roman',16,BOLD),pady=10) 
regnow=StringVar() 
passwo=Label(frame1,text="Enter Password",font=('times new 
roman',16,BOLD),pady=10) 
passwow=StringVar() 
code=Label(frame1,text="Type The Code You See above:",font=('times new 
roman',16,BOLD),pady=10) 
codew=StringVar() 
captha=Label(frame1, textvariable=captcha, font=("ariel 16 bold"),pady=10) 
btn=Button(frame1, text="Check", font="ariel 15 bold", bg='gold', 
command=check) 
Eregno=Entry(frame1,textvariable=regnow) 
Ecode=Entry(frame1, textvariable=input, bg='white', font="ariel 12 bold") 
Epasswo=Entry(frame1,textvariable=passwow,show='*') 
regno.grid(row=1,column=1) 
Eregno.grid(row=1,column=2) 
passwo.grid(row=2,column=1) 
Epasswo.grid(row=2,column=2) 
code.grid(row=3,column=1) 
Ecode.grid(row=4,column=1) 
captha.grid(row=5,column=1) 
btn.grid(row=6,column=1) 
create_captcha() 
window.mainloop()
