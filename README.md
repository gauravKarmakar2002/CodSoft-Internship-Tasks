# CodSoft-Internship-Tasks
I am Delighted to share that I have completed all the tasks given to me by #CodSoft as a Python Programming Virtual Internship programme  which includes, To-Do List Application, Simple Calculator, Random Password Generator, Rock-Paper-Scissor Game &amp; Contact Book...
👋Hello Everyone👋,
I have just completed each and every task which was given by hashtag#CodeSoft, which includes,
1) TO-DO List Application 📝📝📝
2) Simple Calculator 🧮🧮🧮
3) Random Password Generator 🔑🔑🔑
4) Rock-Paper-Scissor Game 🪨📄✂️🎮
5) Contact Book 📖📖📖

I'm also excited to share all my Python projects which was given by hashtag#CodeSoft and as a part of this 'Python Programming' virtual internship, it was a wonderful & knowledgeable journey for me.

Key Feature for each Projects:-

 1) 📝TO-DO List Application📝:- 
* User-Friendly Interface, where the user's can use the system without any trouble.
* Some features inside the applications like, ADD, TASK DONE, DELETE, EXIT, DATE & TIME, etc.
* Language Used:- Python 
* Framework:- Python Tkinter

2) 🧮Simple Calculator🧮:- 
* User-Friendly Interface, where the user's can do any kind of arithmetic operation in the system.
* Some given features are input area given for the user to conduct any kind of operations they like.
* Language Used:- Python

3) 🔑Random Password Generator🔑:- 
* User-Friendly Interface, where the user's can give any length of characters for their password.
* The random password generated as output will have lower case, upper case as well as digit type of characters. 
* Language Used:- Python

4) 🪨📄✂️🎮Rock-Paper-Scissor Game🎮✂️📄🪨:- 
* User-Friendly Interface, where the user's can choose any choice from the given options.
* Here the User will play against with the Computer and the final match score will be shown at the end.
* Language Used:- Python

5) 📖Contact Book📖:-
* User-Friendly Interface, where the user's can store their details as much as they can.
* Some features are Add, View, Search, Update, Delete, etc.
* Language Used:- Python

At the end, it was really a great opportunity to work with hashtag#CodSoft as a 'Python Programming' virtual internship developer and had a wonderful experience on the project which was assigned to me and special Thanks to my Mentor or Guru, Mr. Divakar Kushwaha sir, who supported me and guided me the path for the completion of the projects.

😊Thank You hashtag#CodSoft...😊

hashtag#python hashtag#pythontkinter hashtag#CodSoft hashtag#pythonprogramming hashtag#virtualinternship hashtag#internship hashtag#todolist hashtag#simplecalculator hashtag#GUI hashtag#rockpaperscissorgame hashtag#randompasswordgenerator hashtag#contactbook


TASK 1:- TO-DO LIST APPLICATION

from tkinter import *
from tkinter import ttk
from time import strftime

todo = Tk()
todo.title("List of To-Do List")
todo.configure(bg="sea green")
todo.geometry("1000x1000")
todo.resizable(False, False)

def TO():
    global count, text
    if(count>=len(L)):
        count = 0
        text = ''
        l1.configure(text=text)
    else: 
        text=text+L[count]
        l1.configure(text=text)
        count += 1
    l1.after(400, TO)

L="📝TO-DO LIST📝"
count=0
text=''

l1=Label(todo, text=L, font=("times new roman", 30, "bold"), fg="goldenrod1", bg="sea green", bd=10, height=2, relief=GROOVE, width=25)
l1.place(x=200, y=0)
TO()

#----------NAME LABEL-------------

name_label=Label(todo, text="By- Gaurav Karmakar", font=("times new roman", 18, "bold"), fg="goldenrod1", bg="sea green", bd=10, relief=GROOVE, width=18)
name_label.place(x=720, y=950)

#----------EXIT BUTTON-------------

def EXT():
    todo.destroy()

ext_bt=Button(todo, text="EXIT", font=("times new roman", 22, "bold"), fg="goldenrod1", bg="sea green", bd=10, width=7 , relief=GROOVE, activebackground="peachpuff3", command=EXT)
ext_bt.place(x=855,y=0)

#----------CLOCK---------------------

def TIME_CLOCK():
    Time = strftime('%H:%M:%S %p \n%x')
    Clock.configure(text=Time)
    Clock.after(1000, TIME_CLOCK)
    
Clock=Label(todo, font=("TIMES NEW ROMAN", 18, "bold"), relief=GROOVE, bd=10, width=10, fg="goldenrod1", bg="sea green")
Clock.place(x=1, y=0)
TIME_CLOCK()

#-----------FRAME-------------------

f1=Frame(todo, bg="yellow green", relief=SOLID, bd=7)
f1.place(x=235, y=400, height=533, width=550)

f2=Frame(todo, bg="yellow green", relief=SOLID, bd=7)
f2.place(x=235, y=170, height=225, width=550)

#---------LISTBOX AREA-----------

def task():
    tt = E2.get()
    listbox.insert(END, tt)
    E2.delete(0, END)
    
def remove():
    marked = listbox.curselection()
    if marked:
        index = marked[0]
        listbox.delete(index)

def select():
    marked = listbox.curselection()
    if marked:
        index = marked[0]
        tt = listbox.get(index)
        if tt.endswith("☑️"):
            listbox.delete(index)
            listbox.insert(index, tt[1:])
        else:
            listbox.delete(index)
            listbox.insert(index, "✅" + tt)
        

#def clr():
 #   listbox.delete(0, END)
#-----------FRAME DETAILS----------
L2=Label(f2, text="List The Task", font=("times new roman", 28, "bold"), fg="goldenrod1", bg="sea green", bd=5, relief=GROOVE, width=15)
L2.pack()

E2=Entry(f2, font=("TIMES NEW ROMAN", 30, "bold"), bg="sea green", fg="goldenrod1", width=26, relief=SUNKEN)
E2.place(x=6, y=65)

listbox = Listbox(f1,font=("times new roman", 26, "bold"), bg="yellow green", relief=SOLID)
listbox.insert(END, "📝Tasks📝:-")
listbox.place(x=-1, y=-1, width=537, height=520)


bt1=Button(f2, text="ADD", font=("TIMES NEW ROMAN", 26, "bold"), bd=7, width=7, relief=GROOVE, bg="sea green", fg="goldenrod1", activebackground="peachpuff3", command=task)
bt1.place(x=5, y=122)

bt2=Button(f2, text="DONE", font=("TIMES NEW ROMAN", 26, "bold"), bd=7, width=7, relief=GROOVE, bg="sea green", fg="goldenrod1", activebackground="peachpuff3", command=select)
bt2.place(x=185, y=122)

bt3=Button(f2, text="DELETE", font=("TIMES NEW ROMAN", 26, "bold"), bd=7, width=7, relief=GROOVE, bg="sea green", fg="goldenrod1", activebackground="peachpuff3", command=remove)
bt3.place(x=365, y=122)

todo.mainloop()


TASK 2:- SIMPLE CALCULATOR 

NUM1=eval(input("ENTER THE FIRST VALUE = "))
NUM2=eval(input("ENTER THE SECOND VALUE = "))
ARITH_OPERATION=str(input("SELECT THE OPERATION(+, -, *, /) = "))
if(ARITH_OPERATION=='+'):
    print("ADDITION= ", NUM1+NUM2)
elif(ARITH_OPERATION=='-'):
    print("SUBTRACTION= ", NUM1-NUM2)
elif(ARITH_OPERATION=='*'):
    print("MULTIPLICATION= ", NUM1*NUM2)
elif(ARITH_OPERATION=='/'):
    print("DIVISION= ", NUM1/NUM2)
else:
    print("NOTHING")


TASK 3:- RANDOM PASSWORD GENERATOR

import random
import string

# DEFINING THE LENGTH OF PASSWORD FROM THE USER.....

length = int(input("Enter The Lenght Of Password = "))

# DEFINING THE TYPES OF CHARACTERS USED IN THE PASSWORD....

lower = string.ascii_lowercase
upper = string.ascii_uppercase
number = string.digits

# COMBINING EVERYTHING INTO ONE.....

Every = lower + upper + number 

# DEFINING THE FINAL RANDOM PASSWORD FROM THE USER.....

rdm = random.sample(Every, length)
password = "".join(rdm)
print("Password = ",password)



TASK 4:- ROCK-PAPER-SCISSOR GAME


import random
L1=["ROCK", "PAPER", "SCISSOR"]
while True:
    User_Count=0
    Comp_Count=0
    User_Select=int(input('''
Game Start...
1) YES
2) NO | EXIT
    '''))
    if User_Select==1:
        for i in range(1,6):
            User_Input=int(input('''
1) ROCK
2) PAPER
3) SCISSOR
            '''))
            if User_Input==1:
                User_Choice="ROCK"
            elif User_Input==2:
                User_Choice="PAPER"
            elif User_Input==3:
                User_Choice="SCISSOR"
            Comp_Choice=random.choice(L1)
            if Comp_Choice == User_Choice:
                print("COMPUTER VALUE:- ", Comp_Choice)
                print("USER VALUE:- ", User_Choice)
                print("GAME DRAW...")
                User_Count = User_Count + 1
                Comp_Count = Comp_Count + 1
            elif(User_Choice=="ROCK" and Comp_Choice=="PAPER") or (User_Choice=="PAPER" and Comp_Choice=="SCISSOR") or (User_Choice=="SCISSOR" and Comp_Choice=="ROCK"):
                print("COMPUTER VALUE:- ", Comp_Choice)
                print("USER VALUE:- ", User_Choice)
                print("YOU WON THE GAME...")
                User_Count = User_Count + 1
            else:
                print("COMPUTER VALUE:- ", Comp_Choice)
                print("USER VALUE:- ", User_Choice)
                print("COMPUTER WON THE GAME...")
                Comp_Count = Comp_Count + 1
        if User_Count==Comp_Count:
            print("FINAL GAME DRAW...")
            print("USER SCORE:- ", User_Count)
            print("COMPUTER SCORE:- ", Comp_Count)
        elif User_Count>Comp_Count:
            print("YOU WON THE GAME...")
            print("USER SCORE:- ", User_Count)
            print("COMPUTER SCORE:- ", Comp_Count)
        else:
            print("COMPUTER WON THE GAME...")
            print("USER SCORE:- ", User_Count)
            print("COMPUTER SCORE:- ", Comp_Count)
    else:
        break



   TASK 5:- CONTACT BOOK



   contacts = []


def add_contact():
    store_name = input("Enter Store Name: ")
    phone_number = input("Enter Phone Number: ")
    email = input("Enter Email: ")
    address = input("Enter Address: ")

    contact = {
        'store_name': store_name,
        'phone_number': phone_number,
        'email': email,
        'address': address
    }
    contacts.append(contact)
    print("Contact added successfully!")


def view_contacts():
    if not contacts:
        print("No contacts available.")
    else:
        for index, contact in enumerate(contacts):
            print(f"{index + 1}. {contact['store_name']} - {contact['phone_number']}")


def search_contact():
    search_term = input("Enter Store Name or Phone Number to search: ")
    found = False
    for contact in contacts:
        if search_term in contact['store_name'] or search_term in contact['phone_number']:
            print(f"Found: {contact['store_name']} - {contact['phone_number']} - {contact['email']} - {contact['address']}")
            found = True
    if not found:
        print("No matching contact found.")


def update_contact():
    view_contacts()  
    try:
        contact_index = int(input("Enter the number of the contact to update: ")) - 1
        if contact_index < 0 or contact_index >= len(contacts):
            print("Invalid contact number.")
            return

        
        store_name = input("Enter new Store Name (leave blank to keep current): ")
        phone_number = input("Enter new Phone Number (leave blank to keep current): ")
        email = input("Enter new Email (leave blank to keep current): ")
        address = input("Enter new Address (leave blank to keep current): ")

        if store_name:
            contacts[contact_index]['store_name'] = store_name
        if phone_number:
            contacts[contact_index]['phone_number'] = phone_number
        if email:
            contacts[contact_index]['email'] = email
        if address:
            contacts[contact_index]['address'] = address

        print("Contact updated successfully!")
    except ValueError:
        print("Invalid input.")


def delete_contact():
    view_contacts()  
    try:
        contact_index = int(input("Enter the number of the contact to delete: ")) - 1
        if contact_index < 0 or contact_index >= len(contacts):
            print("Invalid contact number.")
            return

        contacts.pop(contact_index)
        print("Contact deleted successfully!")
    except ValueError:
        print("Invalid input.")


while True:
    print("\nContact Management System")
    print("1. Add Contact")
    print("2. View Contact List")
    print("3. Search Contact")
    print("4. Update Contact")
    print("5. Delete Contact")
    print("6. Exit")

    choice = input("Enter your choice (1-6): ")

    if choice == '1':
        add_contact()
    elif choice == '2':
        view_contacts()
    elif choice == '3':
        search_contact()
    elif choice == '4':
        update_contact()
    elif choice == '5':
        delete_contact()
    elif choice == '6':
        print("Exiting the program.")
        break
    else:
        print("Invalid choice. Please enter a number between 1 and 6.")


