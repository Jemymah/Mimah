# Mimah
from tkinter import *

def register_user():
    
    username_info = username.get()
    password_info = password.get()
    print('hi')
    
    file=open("ALAConnectsDocument.txt", "w")
    file.write(username_info+"\n")
    file.write(password_info)
    file.close()
    print('hello')
    username_entry.delete(0, END)
    password_entry.delete(0, END)
    
    Label(screen1, text = "Registration success", fg = "green", font = ("calibiri", 11)).pack() 
    
    

def register():
    global screen1
    screen1 = Toplevel(screen)
    screen1.title("Register")
    screen1.geometry("300x250")
    
    global username #(Global variable are the ones that are defined and declared outside a fuction and we need to use them inside a function)
    global password
    global username_entry
    global password_entry
    username = StringVar ()
    password = StringVar ()
    
    Label(screen1, text = "Please enter details below").pack()
    Label(screen1, text = "").pack()
    Label(screen1, text = " Username").pack()
    username_entry = Entry(screen1, textvariable = username)
    username_entry.pack()
    Label(screen1, text = "Password").pack()
    password_entry = Entry(screen1, textvariable = password)
    password_entry.pack()
    Label(screen1, text = "").pack()
    Button(screen1, text = "Register", width = 10, height = 1, command = register_user).pack()
    
    


def login():
    print("login session started")
    


def main_screen():
    global screen
    screen = Tk()
    screen.geometry("300x250")
    screen.title("Notes 1.0")
    Label(text = "Notes 1.0", bg = "grey", width = "300", height = "2", font = ("arial", 13)).pack()
    Label(text = "").pack()
    Button(text = "Login", height = "2", width = "30", command = login ).pack()
    Label(text = "").pack()
    Button(text = "Register", height = "2", width = "30", command = register ).pack()
    
    screen.mainloop()

main_screen()

    
          
