from tkinter import *
import random

root = Tk()

moznosti=['rock', 'paper', 'scissors','lizard', 'spock']

class Cela_igra():
    def __init__(self, master):
        self.master=master


        self.rezultat=""


        self.igralec=0
        self.rac=0


        meni = Menu(self.master)
        self.master.config(menu=meni)

        
        mozno = Menu(meni)
        mozno.add_command(label="Nova_igra", command=self.nova_igra)
        mozno.add_command(label="Shrani igro", command=self.shrani)
        mozno.add_command(label="Naloži igro", command=self.nalozi)
        meni.add_cascade(label="Možnosti", menu=mozno)

 
        frame=Frame(root, width=600, height=690)
        frame.pack()

        self.canvas=Canvas(root, width=600,height=200)
        self.canvas.pack()

        
        gumb1=Button(frame, image=rock, command=self.ro)
        gumb1.place(x=340, y=400)

        gumb2=Button(frame, image=paper, command=self.pa)
        gumb2.place(x=415, y=170)

        gumb3=Button(frame, image=scissors, command=self.sc)
        gumb3.place(x=220, y=31)

        gumb4=Button(frame, image=lizard, command=self.li)
        gumb4.place(x=100, y=400)

        gumb5=Button(frame, image=spock, command=self.sp)
        gumb5.place(x=16, y=170)





        self.napis_rezultat = StringVar(value=str(self.rezultat))
        label_rezultat = Label(frame,font=("Purisa",26), textvariable=self.napis_rezultat)
        label_rezultat.place(x=300, y=300, anchor=CENTER)

        self.napis_tock_igralec = StringVar(value=("igralec: %s" % str(self.igralec)))
        label_igralec = Label(frame,font=("Purisa",20),textvariable=self.napis_tock_igralec)
        label_igralec.place(x=450, y=650)

        self.napis_tock_rac = StringVar(value=("računalnik:%s" %str(self.rac)))
        label_rac = Label(frame,font=("Purisa",20), textvariable=self.napis_tock_rac)
        label_rac.place(x=30, y=650)

        

    def pripravi_canvas(self):
        self.canvas.delete(ALL)



        
    def ro(self):
        self.pripravi_canvas()
        ran=random.randrange(0,5)
        kir=moznosti[ran]
        x=moznosti_slike[ran]
        self.canvas.create_image(500,75, image=rock)
        self.canvas.create_image(100,75,image=x)
        if kir=='rock': self.rezultat="PAT"
        if kir in ['lizard', 'scissors']:
            self.igralec=self.igralec+1
            self.rezultat="ZMAGA!"
        if kir in ['paper','spock']:
            self.rac=self.rac+1
            self.rezultat="IZGUBIL SI!"
        self.posodobi()
        print ('rock', kir, self.igralec, self.rac, self.rezultat)

    def pa(self):
        self.pripravi_canvas()
        ran=random.randrange(0,5)
        kir=moznosti[ran]
        x=moznosti_slike[ran]
        self.canvas.create_image(500,75, image=paper)
        self.canvas.create_image(100,75,image=x)
        if kir=='paper': self.rezultat="PAT"
        if kir in ['spock', 'rock']:
            self.igralec=self.igralec+1
            self.rezultat="ZMAGA!"
        if kir in ['scissors', 'lizard'] :
            self.rac=self.rac+1
            self.rezultat="IZGUBIL SI!"
        self.posodobi()
        print ('paper', kir, self.igralec, self.rac, self.rezultat)

    def sc(self):
        self.pripravi_canvas()
        ran=random.randrange(0,5)
        kir=moznosti[ran]
        x=moznosti_slike[ran]
        self.canvas.create_image(500,75, image=scissors)
        self.canvas.create_image(100,75,image=x)
        if kir=='scissors':self.rezultat="PAT"
        if kir in ['lizard', 'paper']:
            self.igralec=self.igralec+1
            self.rezultat="ZMAGA!"
        if kir in ['spock', 'rock']:
            self.rac=self.rac+1
            self.rezultat="IZGUBIL SI!"
        self.posodobi()
        print ('scissors', kir, self.igralec, self.rac, self.rezultat)

    def li(self):
        self.pripravi_canvas()
        ran=random.randrange(0,5)
        kir=moznosti[ran]
        x=moznosti_slike[ran]
        self.canvas.create_image(500,75, image=lizard)
        self.canvas.create_image(100,75,image=x)
        if kir=='lizard':self.rezultat="PAT"
        if kir in ['paper', 'spock']:
            self.igralec=self.igralec+1
            self.rezultat="ZMAGA!"
        if kir in ['scissors', 'rock']:
            self.rac=self.rac+1
            self.rezultat="IZGUBIL SI!"
        self.posodobi()
        print ('lizard', kir, self.igralec, self.rac, self.rezultat)

    def sp(self):
        self.pripravi_canvas()
        ran=random.randrange(0,5)
        kir=moznosti[ran]
        x=moznosti_slike[ran]
        self.canvas.create_image(100,75,image=x)
        self.canvas.create_image(500,75, image=spock)
        if kir=='spock':self.rezultat="PAT"
        if kir in ['rock', 'scissors']:
            self.igralec=self.igralec+1
            self.rezultat="ZMAGA!"
        if kir in ['lizard', 'paper']:
            self.rac=self.rac+1
            self.rezultat="IZGUBIL SI!"
        self.posodobi()
        print ('spock', kir, self.igralec, self.rac, self.rezultat)


    def nova_igra (self):
        self.rac=0
        self.igralec=0
        self.rezultat=""
        self.pripravi_canvas()
        self.posodobi()

    def shrani(self):
        with open ("lizard.txt", 'w') as a:
            print('{}\n{}'.format(self.igralec,self.rac),file=a)
            
    def nalozi (self):
        sez=[]
        with open ("lizard.txt", 'r') as b:
            for i in b:
                x=i.strip()
                sez.append(int(x))
            self.igralec=sez[0]
            self.rac=sez[1]
            self.rezultat=""
        self.posodobi()
        self.pripravi_canvas()


            

    def posodobi(self):
        self.napis_rezultat.set(str(self.rezultat))
        self.napis_tock_igralec.set("igralec: %s" %str(self.igralec))
        self.napis_tock_rac.set("računalnik:%s" % str(self.rac))
    
        


        
    

    
rock=PhotoImage(file='img/rock.gif')
paper=PhotoImage(file='img/paper.gif')
scissors=PhotoImage(file='img/scissors.gif')
lizard=PhotoImage(file='img/lizard.gif')
spock=PhotoImage(file='img/spock.gif')

moznosti_slike=[rock, paper, scissors, lizard, spock]


aplikacija=Cela_igra(root)
root.mainloop()
