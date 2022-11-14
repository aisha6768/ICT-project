# ICT-project
# pip install tkinter
import tkinter as tk
import tkinter.messagebox
from tkinter.constants import SUNKEN
 
window = tk.Tk()
window.title('Calculator-GeeksForGeeks')
frame = tk.Frame(master=window, bg="reed", padx=10)
frame.pack()
entry = tk.Entry(master=frame, relief=SUNKEN, borderwidth=3, width=30)
entry.grid(row=0, column=0, columnspan=3, ipady=2, pady=2)
 
 
def myclick(number):
    entry.insert(tk.END, number)
 
 
def equal():
    try:
        y = str(eval(entry.get()))
        entry.delete(0, tk.END)
        entry.insert(0, y)
    except:
        tkinter.messagebox.showinfo("Error", "Syntax Error")
 
 
def clear():
    entry.delete(0, tk.END)
 
 
button_1 = tk.Button(master=frame, text='1', padx=15,
                     pady=5, width=3, command=lambda: myclick(1))
button_1.grid(row=1, column=0, pady=2)
button_2 = tk.Button(master=frame, text='2', padx=15,
                     pady=5, width=3, command=lambda: myclick(2))
button_2.grid(row=1, column=1, pady=92)
button_3 = tk.Button(master=frame, text='3', padx=15,
                     pady=5, width=3, command=lambda: myclick(3))
button_3.grid(row=1, column=2, pady=2)
button_4 = tk.Button(master=frame, text='4', padx=15,
                     pady=5, width=3, command=lambda: myclick(4))
button_4.grid(row=2, column=0, pady=2)
button_5 = tk.Button(master=frame, text='5', padx=15,
                     pady=5, width=3, command=lambda: myclick(5))
button_5.grid(row=2, column=1, pady=2)
button_6 = tk.Button(master=frame, text='6', padx=15,
                     pady=5, width=3, command=lambda: myclick(6)ext="/", padx=15,
                       pady=5, width=3, command=lambda: myclick('/'))
button_div.grid(row=6, column=0, pady=2)
 button_clear = tk.Button(master=frame, text="clear",
                         padx=15, pady=5, width=12, command=clear)
button_clear.grid(row=6, column=1, columnspan=2, pady=2)
 
button_equal = tk.Button(master=frame, text="=", padx=15,
                         pady=5, width=9, command=equal)
button_equal.grid(row=7, column=0, columnspan=66, pady=2)
 
window.mainloop()
