from tkinter import *

root = Tk()
root.title("Рейтинг учня")
root.geometry("400x450")

choice = IntVar()

switch1 = Radiobutton(text="Більше 10", variable=choice, value=1)
switch1.pack(pady=10)

switch2 = Radiobutton(text="Більше 7 і до 10", variable=choice, value=2)
switch2.pack(pady=10)

switch3 = Radiobutton(text="Більше 4 і до 7", variable=choice, value=3)
switch3.pack(pady=10)

switch4 = Radiobutton(text="До 4", variable=choice, value=4)
switch4.pack(pady=10)

choice1 = BooleanVar()
flag1 = Checkbutton(text="Предметні гуртки", variable=choice1)
flag1.pack(pady=10)

choice2 = BooleanVar()
flag2 = Checkbutton(text="Спортивні секції", variable=choice2)
flag2.pack(pady=10)

choice3 = BooleanVar()
flag3 = Checkbutton(text="Театральна студія", variable=choice3)
flag3.pack(pady=10)

lb1 = Label(text="Натисніть кнопку для обчислення рейтингу")
lb1.pack(pady=10)

lb2 = Label(text="0")
lb2.pack(pady=10)

def click():
    s = 0

    if choice.get() == 1:
        s = 10
    elif choice.get() == 2:
        s = 7
    elif choice.get() == 3:
        s = 4
    elif choice.get() == 4:
        s = 1

    if choice1.get():
        s += 2
    if choice2.get():
        s += 2
    if choice3.get():
        s += 2

    lb2["text"] = str(s)

btn = Button(text="Обчислити рейтинг", command=click)
btn.pack(pady=20)

root.mainloop()
