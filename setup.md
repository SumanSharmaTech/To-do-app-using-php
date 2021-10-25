#DETAIL STEPS


#Step 1 : Import Modules

Before we start using Tkinter, we need to call Tkinter for use. 
so we import the module. Here * means everything. 
So we are importing everything from Tkinter then in the second line we have imported message box from Tkinter.

`from tkinter import *
from tkinter import messagebox`

#Step 2: Create & Configure Window

After importing module, we will create a window so that we can place widgets on it.

`ws = Tk()
ws.geometry('500x450+500+200')
ws.title('PythonGuides')
ws.config(bg='#223441')
ws.resizable(width=False, height=False)

....
....

ws.mainloop()`

#Step 3: Creating a frame

In this section we will understand why we have used frames as a first widget in our code.

`frame = Frame(ws)
frame.pack(pady=10)`

#Step 4: Adding Listbox

In this section, we will learn why and how we have used Listbox on the window.

`lb = Listbox(
    frame,
    width=25,
    height=8,
    font=('Times', 18),
    bd=0,
    fg='#464646',
    highlightthickness=0,
    selectbackground='#a6a6a6',
    activestyle="none",
    
)
lb.pack(side=LEFT, fill=BOTH)`

#Step 5: Adding dummy data

We have added dummy data so that the application is ready to view.
You add or delete whatever data you want.

`task_list = [
    'Eat apple',
    'drink water',
    'go gym',
    'write software',
    'write documentation',
    'take a nap',
    'Learn something',
    'paint canvas'
    ]


for item in task_list:
    lb.insert(END, item)`
    
#Step 6: Adding Scrollbars

In this section, we will understand why and how scrollbars are added to the window.

`sb = Scrollbar(frame)
sb.pack(side=RIGHT, fill=BOTH)

lb.config(yscrollcommand=sb.set)
sb.config(command=lb.yview)`


#Step 7: Adding Entry Box

`my_entry = Entry(
    ws,
    font=('times', 24)
    )

my_entry.pack(pady=20)`


#Step: 8 Adding another frame for buttons


`button_frame = Frame(ws)
button_frame.pack(pady=20)`


#Step 9: Adding Buttons


`addTask_btn = Button(
    button_frame,
    text='Add Task',
    font=('times 14'),
    bg='#c5f776',
    padx=20,
    pady=10,
    command=newTask
)
addTask_btn.pack(fill=BOTH, expand=True, side=LEFT)

delTask_btn = Button(
    button_frame,
    text='Delete Task',
    font=('times 14'),
    bg='#ff8b61',
    padx=20,
    pady=10,
    command=deleteTask
)
delTask_btn.pack(fill=BOTH, expand=True, side=LEFT)`


#Step 10: newTask() function

`def newTask():
    task = my_entry.get()
    if task != "":
        lb.insert(END, task)
        my_entry.delete(0, "end")
    else:
        messagebox.showwarning("warning", "Please enter some task.")`
        
 #Step 11: deleteTask() function
 
 `def deleteTask():
    lb.delete(ANCHOR)`
 

