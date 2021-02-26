#generator losowego hasła
from tkinter import *
import pyperclip
import random, string


#inicjacja okna
genWindow = Tk()
genWindow.resizable(0,0)
genWindow.geometry("400x200")
genWindow.title("Generator losowego hasła")
Label(genWindow, text = 'GENETATOR HASŁA' , font ='arial 20 bold').pack()
Label(genWindow, text ='WOLNI KASZUBI', font ='arial 20 bold').pack(side = BOTTOM)
lengthLabel = Label(genWindow, text = 'DŁUGOŚĆ HASŁA', font = 'arial 15 bold').pack()
passwordLength = IntVar()
length = Spinbox(genWindow, from_ = 10, to_ = 30 , textvariable = passwordLength , width = 20).pack()
passwordToString = StringVar()


#generacja losowego hasla
def Generator():
    password = ''
    #pierwsza pętla wymusza obecność wielkiej oraz małej litery, znaku interpunkcyjnego oraz specjalnego
    for x in range (0,4):
        password = random.choice(string.ascii_uppercase) + random.choice(string.punctuation) + random.choice(string.digits) + random.choice(string.ascii_lowercase)
    #druga pętla uzupełnia pozostałe wartości hasła, nie wymuszając wystąpienia po jednym z każdego rodzaju znaku
    for y in range(passwordLength.get()- 4):
        password = password + random.choice(string.ascii_uppercase + string.ascii_lowercase + string.digits + string.punctuation)
    passwordToString.set(password)

Button(genWindow, text="WYGENERUJ HASŁO", command=Generator).pack(pady=5)
Entry(genWindow, textvariable=passwordToString, width = 40).pack()


#funkcja umożliwia skopiowanie wygenerowanego hasła do schowka
def PasswordToClipboard():
    pyperclip.copy(passwordToString.get())
    Button(genWindow, text='SKOPIUJ HASŁO DO SCHOWKA', command=PasswordToClipboard).pack(pady=5)

genWindow.mainloop()
