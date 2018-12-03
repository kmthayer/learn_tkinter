# learn_tkinter
# my workspace on learning tkinter
# Dynamic label content
# 2018-12-02 KMT
#

import tkinter as tk
# note the web site has the Python2 version of import
# import Tkinter as tk #OLD

counter = 0
def counter_label(label):
    counter = 0
    def count():
        global counter
        counter += 1
        label.config(text=str(counter))
        label.after(1000,count)
    count()

# make the root window as an instance of a toolkit
root = tk.Tk()
# make a title for the window
root.title("Counting Seconds")
# make an instance of a label in the root window
label=tk.Label(root, fg="dark green")
# put the label into the root window
label.pack()

# run the counter function on the label
counter_label(label)

# now we create a button to stop it (otherwise we have inf loop)
button=tk.Button(root, text='Stop',bg='red',fg='brown',width=25,command=root.destroy)
# put the button into the root window
button.pack()

# continually run until Stop or x out
root.mainloop()

