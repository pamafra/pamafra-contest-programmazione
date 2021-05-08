
from tkinter import *
from tkinter.messagebox import *
import math

root = Tk()
root.title('Calcolo MCD e mcm')
root.resizable(width=False, height=False)

contenitore = Frame(root)

def calcola(evento = None,):
    if (valore1.get() > 0 and valore2.get() >0) and (valore1.get() == int and valore2.get()==int):
        MCD.set(math.gcd(valore1.get() , valore2.get() ))
        mcm.set((valore1.get() * valore2.get()) // (MCD.get()))
    else:
        showerror('Errore','Devi inserire un numero intero positivo diverso da 0')
    

valore1 = IntVar()
valore2 = IntVar()
MCD = IntVar()
MCD.set('')
mcm = IntVar()
mcm.set('')


titolo = Label(root,font = ('arial',17),text=' Calcolo MCD e mcm ',bg = 'lime').grid(row=0,column=0,columnspan=3,pady=(15,25))

casella_1 = Label(root,text = '1° numero').grid(row=1,column=0,padx=(15,10))
casella_1 = Entry(root, textvariable = valore1, width = 20)
casella_1.grid (row=  1, column = 1)
casella_1.bind( '<Return>', calcola)

casella_2 = Label(root,text = '2° numero').grid(row=2,column=0,padx=(15,10))
casella_2 = Entry(root, textvariable = valore2)
casella_2.grid (row=  2, column = 1)
casella_2.bind( '<Return>', calcola)

bottone_calcola = Button(root, text='Calcola', command = calcola ,width = 8)
bottone_calcola.grid(row=1,rowspan=2,column = 2,padx=(10,15))

Label(root, text ='MCD: ').grid(row=3,column=0,columnspan=2,pady=(15,0))
Label(root, textvariable = MCD).grid(row=3,column=0,columnspan=3,pady=(15,0))

Label(root, text ='mcm: ').grid(row=4,column=0,columnspan=2,pady=(2,15))
Label(root, textvariable = mcm).grid(row=4,column=0,columnspan=3,pady=(2,15))

root.mainloop()
