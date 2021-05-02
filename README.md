from tkinter import *
from tkinter import messagebox
import tkinter

login_screen = Tk()
login_screen.title("HOLY CROSS HIGH SCHOOL SENIOR HIGH ENROLLMENT")
login_screen.geometry("600x550")
login_screen.config(bg="white")

#header
heading1 = Label(text="+By This Sign You Shall Conquer+\n\"In God's Mercy, We Serve With Joy\"\n Camp Phillips, M.F., Bukidnon", bg="midnight blue", width="300",
fg="white", height="7", font=("Georgia", 13, "bold", "italic"))
heading1.pack()

Canvas1 = Canvas(login_screen,width=800, height = 500,bg="snow",relief="raised")
Canvas1.pack()

filename = PhotoImage(file ="C:\IMAGE\Hchs Logo.png")
Canvas1.create_image(10,10, anchor= NW, image = filename)

heading= Label(login_screen,text="LOG-IN YOUR ACCOUNT",font=("Helvetica",14,"bold"),relief="raised",bg="white",fg="black")
heading.place(x=30, y=395)

#details
uname = StringVar()
pw = StringVar()
dt = StringVar()

def login():
    username = uname.get()
    password = pw.get()
    date = dt.get()

    file = open("login.txt", "a")
    file.write ("\nYour Username: " + username)
    file.write ("\nYour Password: " + password)
    file.write ("\nThe Date you logged in: " + str (date))
    file.close()

def info_g11():
    aged = age.get()
    date = bDate.get()
    gen = gender.get()
    st = strand.get()
    ea = email.get()
    num = num.get()
    ln = lastName.get()
    fn= firstName.get()
    mn= middleName.get()

    file = open("Info_G11.txt", "a")
    file.write ("\nYour Last Name: " + ln)
    file.write ("\nYour First Name: " + fn)
    file.write ("\nYour Middle Name: " + mn)
    file.write ("\nBirthday: " + str (date))
    file.write ("\nAge: " + str (aged))
    file.write ("\nGender: " + gen)
    file.write ("\nStrand: " + st)
    file.write ("\nYour Email: " + ea)
    file.write ("\nPhone Number: " + str (num))
    file.close()

def info_g12():
    aged = age.get()
    date = bDate.get()
    gen = gender.get()
    st = strand.get()
    ea = email.get()
    num = num.get()
    ln = lastName.get()
    fn= firstName.get()
    mn= middleName.get()

    file = open("Info_G12.txt", "a")
    file.write ("\nYour Last Name: " + ln)
    file.write ("\nYour First Name: " + fn)
    file.write ("\nYour Middle Name: " + mn)
    file.write ("\nBirthday: " + str (date))
    file.write ("\nAge: " + str (aged))
    file.write ("\nGender: " + gen)
    file.write ("\nStrand: " + st)
    file.write ("\nYour Email: " + ea)
    file.write ("\nPhone Number: " + str (num))
    file.close()

def login_verify():
    messagebox.showinfo("Holy Cross High School","You are Successfully Enrolled!")
    a = messagebox.askokcancel("Enrollment","Please check your Email for further instructions. \nThank you!")
    if a == 'ok':
        print("THANK YOU")
    else:
       exit
    
def selection():
    selection_screen = Tk()
    selection_screen.title("ENROLLMENT")
    selection_screen.geometry("500x300")
    selection_screen.config(bg="midnight blue")
    Label(selection_screen, text="HOLY CROSS HIGH SCHOOL \nSENIOR HIGH \nCURRICULLUM",font=("Helvetica",14,"bold","italic"),relief="raised").place(x=100,y=100)
    
    def exit_select():
        selection_screen.destroy()
        
    def Grade11_verify():
        global Grade11_screen
        frame = Tk()
        frame.title("REGISTER GRADE 11")
        frame.geometry("650x450")
        frame.config(bg="midnight blue")

        global name
        global age
        global birthday
        global strand
        global name_entry
        global age_entry
        global birthday_entry
        global strand
        age = StringVar()
        bDate = StringVar()
        gender = StringVar()
        strand = StringVar()
        email = StringVar()
        num = StringVar()
    
        ageField = Spinbox(frame, from_=0,to=100, textvar=age,width=5,font=("Helvetica",10,"bold"),relief="raised").place(x=130, y=150)
        bdateField = Entry(frame, textvar=bDate,width=15,font=("Helvetica",10,"bold"),relief="raised").place(x=320, y=150)
        genderField = Entry(frame, textvar=gender,width=5,font=("Helvetica",10,"bold"),relief="raised").place(x=130, y=200)
        strandField = Entry(frame, textvar=strand,width=15,font=("Helvetica",10,"bold"),relief="raised").place(x=320, y=200)
        emailField = Entry(frame, textvar=email,width=30,font=("Helvetica",10,"bold"),relief="raised").place(x=150, y=250)
        numField = Entry(frame, textvar=num,width=30,font=("Helvetica",10,"bold"),relief="raised").place(x=150, y=290)
 
        studentInfoLabel = tkinter.Label(frame, text="Student Information",font=("arial", 16, "bold"),relief="raised").place(x=15,y=15)
        nameLabel = tkinter.Label(frame, fg='Black', text="Name:", font=("Helvetica",10,"bold"),relief="raised").place(x=50, y=60)
        lastNameLabel = tkinter.Label(frame, fg='Black', text="Last Name", font=("Helvetica",10,"bold"),relief="raised").place(x=150, y=90)
        firstNameLabel = tkinter.Label(frame, fg='Black', text="First Name", font=("Helvetica",10,"bold"),relief="raised").place(x=300, y=90)
        middleNameLabel = tkinter.Label(frame, fg='Black', text="Middle Name", font=("Helvetica",10,"bold"),relief="raised").place(x=450, y=90)

        ageLabel = tkinter.Label(frame, fg='Black', text="Age:", font=("Helvetica",10,"bold"),relief="raised").place(x=50, y=150)
        bdayLabel = tkinter.Label(frame, fg='Black', text="Birthday:", font=("Helvetica",10,"bold"),relief="raised").place(x=220, y=150)
        genderLabel = tkinter.Label(frame, fg='Black', text="Gender:", font=("Helvetica",10,"bold"),relief="raised").place(x=50, y=200)
        strandLabel = tkinter.Label(frame, fg='Black', text="Strand:", font=("Helvetica",10,"bold"),relief="raised").place(x=220, y=200)
        emailLabel = tkinter.Label(frame, fg='Black', text="Email:", font=("Helvetica",10,"bold"),relief="raised").place(x=50, y=250)
        numLabel = tkinter.Label(frame, fg='Black', text="Phone #:", font=("Helvetica",10,"bold"),relief="raised").place(x=50, y=290)

        lastName = StringVar()
        firstName = StringVar()
        middleName = StringVar()
        lastNameField = Entry(frame, textvar=lastName).place(x=130, y=65)
        fistNameField = Entry(frame, textvar=firstName).place(x=280, y=65)
        middleNameField = Entry(frame, textvar=middleName).place(x=432, y=65)

        Button(frame, text="Register", width=14, height=1, command = login_verify ,relief="raised",font=("Helvetica",10,"bold")).place(x=350,y=350)
        Button(frame, text="Cancel", width=14, height=1, command = exit,font=("Helvetica",10,"bold"),relief="raised").place(x=500,y=350)

    def Grade12_verify():
        global Grade12_screen
        frame = Tk()
        frame.title("REGISTER GRADE 12")
        frame.geometry("650x450")
        frame.config(bg="midnight blue")

        global name
        global age
        global birthday
        global strand
        global name_entry
        global age_entry
        global birthday_entry
        global strand
        age = StringVar()
        bDate = StringVar()
        gender = StringVar()
        strand = StringVar()
        email = StringVar()
        num = StringVar()
        
        ageField = Spinbox(frame, from_=0,to=100, textvar=age,width=5,font=("Helvetica",10,"bold"),relief="raised").place(x=130, y=150)
        bdateField = Entry(frame, textvar=bDate,width=15,font=("Helvetica",10,"bold"),relief="raised").place(x=320, y=150)
        genderField = Entry(frame, textvar=gender,width=5,font=("Helvetica",10,"bold"),relief="raised").place(x=130, y=200)
        strandField = Entry(frame, textvar=strand,width=15,font=("Helvetica",10,"bold"),relief="raised").place(x=320, y=200)
        emailField = Entry(frame, textvar=email,width=30,font=("Helvetica",10,"bold"),relief="raised").place(x=150, y=250)
        numField = Entry(frame, textvar=num,width=30,font=("Helvetica",10,"bold"),relief="raised").place(x=150, y=290)

 
        studentInfoLabel = tkinter.Label(frame, text="Student Information",font=("arial", 16, "bold"),relief="raised").place(x=15,y=15)
        nameLabel = tkinter.Label(frame, fg='Black', text="Name:", font=("Helvetica",10,"bold"),relief="raised").place(x=50, y=60)
        lastNameLabel = tkinter.Label(frame, fg='Black', text="Last Name", font=("Helvetica",10,"bold"),relief="raised").place(x=150, y=90)
        firstNameLabel = tkinter.Label(frame, fg='Black', text="First Name", font=("Helvetica",10,"bold"),relief="raised").place(x=300, y=90)
        middleNameLabel = tkinter.Label(frame, fg='Black', text="Middle Name", font=("Helvetica",10,"bold"),relief="raised").place(x=450, y=90)

        ageLabel = tkinter.Label(frame, fg='Black', text="Age:", font=("Helvetica",10,"bold"),relief="raised").place(x=50, y=150)
        bdayLabel = tkinter.Label(frame, fg='Black', text="Birthday:", font=("Helvetica",10,"bold"),relief="raised").place(x=220, y=150)
        genderLabel = tkinter.Label(frame, fg='Black', text="Gender:", font=("Helvetica",10,"bold"),relief="raised").place(x=50, y=200)
        strandLabel = tkinter.Label(frame, fg='Black', text="Strand:", font=("Helvetica",10,"bold"),relief="raised").place(x=220, y=200)
        emailLabel = tkinter.Label(frame, fg='Black', text="Email:", font=("Helvetica",10,"bold"),relief="raised").place(x=50, y=250)
        numLabel = tkinter.Label(frame, fg='Black', text="Phone #:", font=("Helvetica",10,"bold"),relief="raised").place(x=50, y=290)

        
        lastName = StringVar()
        firstName = StringVar()
        middleName = StringVar()
        lastNameField = Entry(frame, textvar=lastName).place(x=130, y=65)
        fistNameField = Entry(frame, textvar=firstName).place(x=280, y=65)
        middleNameField = Entry(frame, textvar=middleName).place(x=432, y=65)

        Button(frame, text="Register", width=14, height=1, command = login_verify, relief="raised",font=("Helvetica",10,"bold")).place(x=350,y=350)
        Button(frame, text="Cancel", width=14, height=1, command = exit,font=("Helvetica",10,"bold"),relief="raised").place(x=500,y=350)
        
    main =Menubutton(selection_screen,text = "Grade 11",activebackground="pink")
    main1 =Menubutton(selection_screen,text ="Grade 12",activebackground="pink")
    main2 =Menubutton(selection_screen,text ="EXIT",activebackground="pink")
    main.place(x=1,y=1)
    main1.place(x=59,y=1)
    main2.place(x=117,y=1)
    main.menu = Menu(main, tearoff=0)
    main["menu"] = main.menu
    main1.menu = Menu(main1, tearoff=0)
    main1["menu"] = main1.menu
    main2.menu = Menu(main2, tearoff=0)
    main2["menu"] = main2.menu

    reg_11 = IntVar()
    main.menu.add_checkbutton(label="Register", variable=reg_11,command=Grade11_verify)
    reg_12 = IntVar()
    main1.menu.add_checkbutton(label="Register", variable=reg_12,command=Grade12_verify)
    exit1 = IntVar()
    main2.menu.add_checkbutton(label="Exit", variable=exit1,command=exit_select)
    
def exit_verify():
    login_screen.destroy()


username_login_entry = Entry(login_screen,textvariable=uname,width="20", font=("Helvetica",10,"bold"),relief="raised").place(x=200, y= 435)
password_login_entry = Entry(login_screen,textvariable=pw,width="20", show= '*',font=("Helvetica",10,"bold"),relief="raised").place(x=200,y=460)
datetoday_login_entry = Entry(login_screen,textvariable=dt, width="20",font=("Helvetica",10,"bold"),relief="raised").place(x=200,y=485)

Label(login_screen, text="Username: ",font=("Helvetica",10,"bold"),relief="raised").place(x=80, y=435)
Label(login_screen, text="Password: ",font=("Helvetica",10,"bold"),relief="raised").place(x=80, y=460)
Label(login_screen, text="Date today: ",font=("Helvetica",10,"bold"),relief="raised").place(x=80,y=485)


#buttons
Button(login_screen, text="Login", width=10, height=1, command = lambda:[login(),selection()]).place(x=380,y=515)
Button(login_screen, text="Exit", width=10, height=1, command = exit_verify).place(x=475, y=515)

login_screen.mainloop()
input()
