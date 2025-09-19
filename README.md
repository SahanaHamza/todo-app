# todo-app
To-do list application with Python (Tkinter)
import tkinter as tk

# Add a new task
def add_task():
    task = task_entry.get()
    if task != "":
        listbox.insert(tk.END, task)
        task_entry.delete(0, tk.END)

# Delete the selected task
def delete_task():
    selected_task = listbox.curselection()
    if selected_task:
        listbox.delete(selected_task)

# Create the main window
root = tk.Tk()
root.title("To-Do List")
root.geometry("300x400")

# Entry field to add tasks
task_entry = tk.Entry(root, width=25)
task_entry.pack(pady=10)

# Add Task button
add_button = tk.Button(root, text="Add Task", command=add_task)
add_button.pack(pady=5)

# Task list display
listbox = tk.Listbox(root, width=35, height=15)
listbox.pack(pady=10)

# Delete Task button
delete_button = tk.Button(root, text="Delete Task", command=delete_task)
delete_button.pack(pady=5)

# Run the app
root.mainloop()

