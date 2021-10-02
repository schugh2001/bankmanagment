# bankmanagment
print('''										-------WELCOME TO THE BANK-------																							''')
# print('press Enter')
import time
import re
regex = '^[a-z0-9]+[\._]?[a-z0-9]+[@]\w+[.]\w{2,3}$'
class bank:
	j={}
	def __init__(self,name,address,contact,email,password):
		self.name=name.lower()
		self.address=address
		self.contact=contact
		self.email=email
		self.password=password
	def initial(self):
		print('press 1 for login')
		print('press 2 for Transactions')
		print('press 3 for Becoming a new member')
		choice=int(input())
		if choice==1:
			self.login()
		elif choice==2:
			self.Transactions()
		elif choice==3:
			self.new()
		else:
			print("you have entered something wrong \n")
			self.initial()

	def login(self):
		print('ENTER YOUR NAME')
		sid=input()
		print('ENTER PASSWORD')
		pas=input()
		if self.name==sid and self.password==pas:
			print('-------you have succesfully login----')
			print('\n')
			print('press U for updating information')
			print('press T for Transactions')
			print('press H for going back to home')
			print('press C for checking details \n')
			sukhi=input().lower()
			if sukhi=='t':
				self.Transactions()
			if sukhi=='h':
				self.initial()
			if sukhi=='u':
				self.update()
			if sukhi=='c':
				self.details()
		else:
			print('Try Again')
			self.login()
	
	def transactions(self):
		pass

	def update(self):
		print('Enter what you want to update or you want to exit \n')
		up=input().lower()
		if up=='name':
			print('ENTER NEW NAME')
			name=input().lower()
			self.name=name
			self.update()

		if up=='address':
			print('ENTER NEW address')
			address=input().lower()
			self.address=address
			self.update()
		if up=='email':
			print('ENTER NEW mailid')
			self.email=email
			self.update()

		if up=='password':
			print('ENTER YOUR OLD PASSWORD')
			t=input()
			if t==self.password:
				print("ENTER NEW PASSWORD")
				password=input()
				self.password=password
				self.update()
			else:
				self.update()
		if up=="exit":
			self.initial()

	def new(self):
		nname=input('Please enter your name \n').lower()
		self.name=nname
		naddress=input('Please enter your address \n')
		self.address=naddress
		ncontact=input('please enter your contact \n')
		self.contact=ncontact
		npassword=input('please enter your Password \n')
		self.password=npassword
		nemail=input('please enter your email \n')
		self.check(nemail)
		self.email=nemail
		print('Now you can login')
		self.login()


	def details(self):
		j={self.name:{self.name:[self.address,self.contact,self.email]}}
		print(j[self.name])
		print('\n')
		print('press L for LOGIN ,H for GO ON HOMEPAGE, E for EXIT ,U for updating data \n ')
		mom=input().lower()
		if mom=='l':
			self.login()
		if mom=='h':
			self.initial()
		if mom=='e':
			print('THANKS FOR USING OUR SERVICES')
			print('----HAVE A WONDERFUL DAY AHEAD----')
			input('press enter')
			exit()
		if mom=='u':
			self.update()

	def check(self,n):  
	    if(re.search(regex,n)):  
	        print("Valid Email")
	        self.login()          
	    else:  
	        print("Invalid Email please try again with format (abc@gmail.com)") 
	        self.new() 
	        
    def clear(self):
		if name == "nt":
			_=system('cls')
		else:
			_=system('clear')

sidhu=bank('Siddhant','sector-8','9966554488','a@gmail.com','1234')
sidhu.initial()
