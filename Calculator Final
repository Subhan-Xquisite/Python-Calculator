print("HELLO FELLOW FRIENDS, HOPE YOU ALL ARE HAVING A GOOD DAY AT THE MOMENT. THIS IS A SHORT SUMMARY OF WHAT THIS IS ABOUT SO PLEASE PAY ATTENTION AND LET'S START")
print("SO AS YOU ALL KNOW BY NOW THAT IN THE PREVIOUSE VERSION WE HAD A LIMIT OF DOING CALCUALTION TILL SEVEN NUMBERS ONLY AND THAT THERE WERE A FEW RESONABLE BUGS")
print("IN THIS VERSION OF OUR 2NDSIMPLECALCULATORMADEBYLEGENDGAMER5208 THERE IS A GUI, UNLIMITED TYPE OF CALCULATIONS, CAN CLEAR ON SPOT, SQUARE ROOT NUMBERS")
print("HOPE YOU ALL ENJOY AND HAVE FUN DOING MENTAL MATHS MADEBYLEGENDGAMER5208 ON SIMPLECALCULATOR")
# NOW WE WILL BE INPORTING A VERY SPECIAL MODULE GUI FOR THE CALCULATOR AS IT WILL GIVE IT A SHAPE AS WELL AS MAKE IT WASIER TO NAVIGATE AROUND INPUTED CONTROLS.
from tkinter import *
import math
import tkinter.messagebox

# NOW WE FIRST WILL MAKE A LAYOUT FOR OUR GUI MODULE AND MAKE THE LAYOUT WITH THE FRAME ROOT
root = Tk()
root.title("2NDSIMPLECALCULATORMADEBYLEGENDGAMER5208")
root.configure(background = 'lawngreen')
root.resizable(width=False, height=False)
root.geometry("480x568")
calc = Frame(root)
calc.grid()

#THIS SECTION WILL NOW PYTHON CODE ALL THE SYMBOLS AND NUMBER PAD WE WILL BE NEEDING TO USE IN THE CALCULATOR
class Calc():
	def __init__(self):
		self.total=0
		self.current=''
		self.input_value=True
		self.check_sum=False
		self.op=''
		self.result=False

	def numberEnter(self, num):
		self.result=False
		firstnum=txtDisplay.get()
		secondnum=str(num)
		if self.input_value:
			self.current = secondnum
			self.input_value=False
		else:
			if secondnum == '.':
				if secondnum in firstnum:
					return
			self.current = firstnum+secondnum
		self.display(self.current)

	def sum_of_total(self):
		self.result=True
		self.current=float(self.current)
		if self.check_sum==True:
			self.valid_function()
		else:
			self.total=float(txtDisplay.get())

	def display(self, value):
		txtDisplay.delete(0, END)
		txtDisplay.insert(0, value)

	def valid_function(self):
		if self.op == "add":
			self.total += self.current
		if self.op == "sub":
			self.total -= self.current
		if self.op == "multi":
			self.total *= self.current
		if self.op == "divide":
			self.total /= self.current
		if self.op == "mod":
			self.total %= self.current
		self.input_value=True
		self.check_sum=False
		self.display(self.total)

	def operation(self, op):
		self.current = float(self.current)
		if self.check_sum:
			self.valid_function()
		elif not self.result:
			self.total=self.current
			self.input_value=True
		self.check_sum=True
		self.op=op
		self.result=False

# CLEAR THE ENTRY OF NUMBERS
	def Clear_Entry(self):
		self.result = False
		self.current = "0"
		self.display(0)
		self.input_value=True

# CLEAR ALL EVERYTHING OF ENTRY NUMBERS
	def All_Clear_Entry(self):
		self.Clear_Entry()
		self.total=0

# MATHS PRISM OF CHANGING AND CALCULATING WITH INTEGERS SYMBOL EASILY
	def mathPM(self):
		self.result = False
		self.current = -(float(txtDisplay.get()))
		self.display(self.current)

# SQUARE ROOT OF NUMBERS MAKING IT EASIER TO OPERATE LIKE A REAL MATHEMATICIAN
	def squared(self):
		self.result = False
		self.current = math.sqrt(float(txtDisplay.get()))
		self.display(self.current)

added_value = Calc()

# NOW WE WILL BE CREATING THE CODING SCRIPT FOR THE TEXT DISPLAY SCREEN AND OTHER STUFF LIKE THE NUMBER PAD WHICH CONATINS ALL THE ARITHEMATIC FUNCTIONALITIES
# THE OTHER BUTTONS THAT INCLUDE REAL TIME STUFF FOR US LIKE BUTTONS FOR ADDITION/SUBTRACTION/MULTIPLY/DIVIDE/INTEGERSNUMBER/EQUAL AND ETC
txtDisplay = Entry(calc, font=('Helvetica',20,'bold' ,'italic'),
				bg='greenyellow',fg='black',
				bd=30,width=28,justify=RIGHT)
txtDisplay.grid(row=0,column=0, columnspan=4, pady=1)
txtDisplay.insert(0,"0")

numberpad = "789456123"
i=0
btn = []
for j in range(2,5):
	for k in range(3):
		btn.append(Button(calc, width=6, height=2,
						bg='yellow1',fg='black',
						font=('Helvetica',20,'bold' ,'italic'),
						bd=4,text=numberpad[i]))
		btn[i].grid(row=j, column= k, pady = 1)
		btn[i]["command"]=lambda x=numberpad[i]:added_value.numberEnter(x)
		i+=1
		
btnClear = Button(calc, text=chr(67),width=6,
				height=2,bg='aqua',
				font=('Helvetica',20,'bold' ,'italic')
				,bd=4, command=added_value.Clear_Entry
				).grid(row=1, column= 0, pady = 1)

btnAllClear = Button(calc, text=chr(67)+chr(69),
					width=6, height=2,
					bg='aqua',
					font=('Helvetica',20,'bold' ,'italic'),
					bd=4,
					command=added_value.All_Clear_Entry
					).grid(row=1, column= 1, pady = 1)

btnsq = Button(calc, text="\u221A",width=6, height=2,
			bg='aqua', font=('Helvetica',
									20,'bold' ,'italic'),
			bd=4,command=added_value.squared
			).grid(row=1, column= 2, pady = 1)

btnAdd = Button(calc, text="+",width=6, height=2,
				bg='aqua',
				font=('Helvetica',20,'bold' ,'italic'),
				bd=4,command=lambda:added_value.operation("add")
				).grid(row=1, column= 3, pady = 1)

btnSub = Button(calc, text="-",width=6,
				height=2,bg='aqua',
				font=('Helvetica',20,'bold' ,'italic'),
				bd=4,command=lambda:added_value.operation("sub")
				).grid(row=2, column= 3, pady = 1)

btnMul = Button(calc, text="x",width=6,
				height=2,bg='aqua',
				font=('Helvetica',20,'bold' ,'italic'),
				bd=4,command=lambda:added_value.operation("multi")
				).grid(row=3, column= 3, pady = 1)

btnDiv = Button(calc, text="/",width=6,
				height=2,bg='aqua',
				font=('Helvetica',20,'bold' ,'italic'),
				bd=4,command=lambda:added_value.operation("divide")
				).grid(row=4, column= 3, pady = 1)

btnZero = Button(calc, text="0",width=6,
				height=2,bg='deeppink1',fg='black',
				font=('Helvetica',20,'bold' ,'italic'),
				bd=4,command=lambda:added_value.numberEnter(0)
				).grid(row=5, column= 0, pady = 1)

btnDot = Button(calc, text=".",width=6,
				height=2,bg='deeppink1',
				font=('Helvetica',20,'bold' ,'italic'),
				bd=4,command=lambda:added_value.numberEnter(".")
				).grid(row=5, column= 1, pady = 1)
btnPM = Button(calc, text=chr(177),width=6,
			height=2,bg='cornflowerblue', font=('Helvetica',20,'bold'),
			bd=4,command=added_value.mathPM
			).grid(row=5, column= 2, pady = 1)

btnEquals = Button(calc, text="=",width=6,
				height=2,bg='cornflowerblue',
				font=('Helvetica',20,'bold'),
				bd=4,command=added_value.sum_of_total
				).grid(row=5, column= 3, pady = 1)

# NOW OUR NUMBER PAD AND OTHER DISPLAYS HAVE BEEN FINALIZED SO NOW WE WILL MAKE THE EXIT MENUE AND OPTION MENU AND EDIT PANEL FOR THE GUI MODULE				

def iExit():
	iExit = tkinter.messagebox.askyesno("2NDSIMPLECALCULATORMADEBYLEGENDGAMER5208",
										"ARE YOU PLANNING ON EXITING THIS PORGRAM SINCE YOU ARE DONE DOING CALCULATIONS ?")
	if iExit>0:
		root.destroy()
		return

def Standard():
	root.resizable(width=False, height=False)
	root.geometry("480x568+0+0")

menubar = Menu(calc)

# THIS IS THE FIRST MENUBAR WHICH CONATINS WHEATHER YOU WANT TO STAY ON STANDARD FORM OF THE CALCULATOR OR WANT TO EXIT THE PROGRAM :
filemenu = Menu(menubar, tearoff = 0)
menubar.add_cascade(label = 'File', menu = filemenu)
filemenu.add_command(label = "Standard", command = Standard)
filemenu.add_separator()
filemenu.add_command(label = "Exit", command = iExit)

# THIS IS THE SEOCND MENUBAR THAT INCLUDED THE FUNCTION FOR THE USER TO EDIT LIKE CUT,COPY AND PASTE TO MAKE IT EASIER FOR THE USER :
editmenu = Menu(menubar, tearoff = 0)
menubar.add_cascade(label = 'Edit', menu = editmenu)
editmenu.add_command(label = "Cut")
editmenu.add_command(label = "Copy")
editmenu.add_separator()
editmenu.add_command(label = "Paste")

root.config(menu=menubar)

root.mainloop()
