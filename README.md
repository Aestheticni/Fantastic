# Fantastic
Simple GUI application which implements financial ratio calculations

import tkinter as tk
import tkinter.font as font


def clear_screen():
    for widget in window.winfo_children():
        widget.destroy()
    OPTIONS = [
        "Profitability Ratios",
        "Liquidity Ratios",
        "Leverage Ratios",
        "Operating Ratios"
    ]
    variable = tk.StringVar(window)
    variable.set(OPTIONS[0])  # default value
    frame_a = tk.Frame(window, borderwidth=5, background="#696969", relief=tk.RAISED)
    frame_a.pack()
    w = tk.OptionMenu(frame_a, variable, *OPTIONS)
    w.pack()
    frame_b = tk.Frame(window, borderwidth=5, background="#696969", relief=tk.RAISED)


window = tk.Tk()
window.config(bg="#615b5c")
window.geometry("500x500+25+25")
frame_2 = tk.Frame(window, borderwidth=5, background="#696969", relief=tk.RAISED)
frame_3 = tk.Frame(window, borderwidth=5, background="#696969", relief=tk.RAISED)
frame_1 = tk.Frame(window, borderwidth=5, background="#696969", relief=tk.RAISED)

window.columnconfigure(1, weight=1, minsize=75)
window.rowconfigure(0, weight=1, minsize=50)
frame_1.grid(row=0, column=1, padx=3, pady=5)
window.columnconfigure(1, weight=1, minsize=75)
window.rowconfigure(1, weight=1, minsize=50)

frame_2.grid(row=1, column=1, padx=3, pady=5)
window.columnconfigure(1, weight=1, minsize=75)
window.rowconfigure(2, weight=1, minsize=50)
frame_3.grid(row=2, column=1, padx=3, pady=5)

myFont = font.Font(family='Helvetica', size=20, weight='bold')

button_1 = tk.Button(master=frame_1, text="TAB-1", width=20, height=5, background="#c4bcbe", font=myFont,
                     command=clear_screen)
button_2 = tk.Button(master=frame_2, text="TAB-2", width=20, height=5, background="#c4bcbe", font=myFont)
button_3 = tk.Button(master=frame_3, text="TAB-3", width=20, height=5, background="#c4bcbe", font=myFont)

button_1.pack()
button_2.pack()
button_3.pack()

window.mainloop()

from tkinter import *
# Messagebox library
from tkinter import messagebox

# Python List
services = []


# Function to use when button is clicked displaying info from checkbox
def showInfo():
    for i in range(len(services)):
        selected = ""
        # Get services variable
        if services[i].get() >= 1:
            selected += str(i)
            # External Window
            messagebox.showinfo(message="You selected Checkbox " + selected)

        # Create new root window


window = Tk()
# Root window title
window.title("Detailed ratios")

for i in range(10):
    # Append int variables for each checkbox
    option = IntVar()
    option.set(0)
    services.append(option)

# Check widget used to display a number of toggle buttons/boxes for different options
Checkbutton(window, text="Gross Margin",
            # Pack manages our widgets in blocks before placing them onto our root window (Widget button or checkbox)
            variable=services[0]).pack()

Checkbutton(window, text="Operating Margin",
            variable=services[1]).pack()
