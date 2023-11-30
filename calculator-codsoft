import tkinter as tk

class Calculator:
    def __init__(self, master):
        self.master = master
        master.title("Calculator")

        # Create Entry widget to display calculations
        self.display = tk.Entry(master, width=25, font=('Arial', 16))
        self.display.grid(row=0, column=0, columnspan=4, pady=5)

        # Create buttons for numbers 0-9
        for i in range(10):
            tk.Button(master, text=str(i), width=5, height=2, font=('Arial', 16),
                      command=lambda num=i: self.add_to_display(num)).grid(row=(i//3)+1, column=i%3)

        # Create buttons for operators
        tk.Button(master, text='+', width=5, height=2, font=('Arial', 16),
                  command=lambda: self.add_to_display('+')).grid(row=1, column=3)
        tk.Button(master, text='-', width=5, height=2, font=('Arial', 16),
                  command=lambda: self.add_to_display('-')).grid(row=2, column=3)
        tk.Button(master, text='*', width=5, height=2, font=('Arial', 16),
                  command=lambda: self.add_to_display('*')).grid(row=3, column=3)
        tk.Button(master, text='/', width=5, height=2, font=('Arial', 16),
                  command=lambda: self.add_to_display('/')).grid(row=4, column=3)

        # Create buttons for decimal point and clear
        tk.Button(master, text='.', width=5, height=2, font=('Arial', 16),
                  command=lambda: self.add_to_display('.')).grid(row=4, column=0)
        tk.Button(master, text='C', width=5, height=2, font=('Arial', 16),
                  command=self.clear_display).grid(row=4, column=1)

        # Create button for equals sign
        tk.Button(master, text='=', width=5, height=2, font=('Arial', 16),
                  command=self.calculate).grid(row=4, column=2)

    def add_to_display(self, char):
        self.display.insert(tk.END, str(char))

    def clear_display(self):
        self.display.delete(0, tk.END)

    def calculate(self):
        try:
            result = eval(self.display.get())
            self.display.delete(0, tk.END)
            self.display.insert(0, str(result))
        except:
            self.display.delete(0, tk.END)
            self.display.insert(0, "Error")

root = tk.Tk()
calculator = Calculator(root)
root.mainloop()
