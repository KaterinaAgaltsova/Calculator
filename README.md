# Calculator
Calculator will prevent from imputing incorrect data 
# Ask a user to input any calculation with two numbers

while True:
    try:
        x = float(input("Enter x: "))
        operator = input("Enter your operator: ")       
        y = float(input("Enter y: "))
        break
      

    except (ValueError): #Shows the message if the input is wrong
        print ("Please enter a number")
     
total = (x, operator, y)  

# The If loop calculates the equation depending on the operator

if (operator == "+"):
    total = x + y

elif (operator == "-"):
    total = x - y

elif (operator == "*"):
    total = x * y

elif (operator == "/"):
    try:
        total = x / y

    except ZeroDivisionError: #Shows error message if trying didive by zero
         print("You cannot divide by zero")   


else: 
    print ("The operator should be +, -, * or /, Please choose the correct operator")

print(f"{x} {operator} {y} = {total}")

with open ("equation.txt", 'w') as file: #Writes the equation in a file
    file.write(f"{x} {operator} {y} = {total}")


print(" Choose your option: \n 1. Enter the numbers \n 2. Open the file") 
choice = int(input("Please enter 1 or 2: ")) # User's choice to keep entering the numbers for equation or open the file

if choice == 1: # User keeps entering the numbers
    while True:
        try:
            x = float(input("Enter x: "))
            operator = input("Enter operator: ")       
            y = float(input("Enter y: "))
            break
      

        except (ValueError): #Shows the message if the input is wrong
            print ("Please enter a number")
     
    total = (x, operator, y)  


    if (operator == "+"):
        total = x + y

    elif (operator == "-"):
        total = x - y

    elif (operator == "*"):
        total = x * y

    elif (operator == "/"):
        try:
            total = x / y

        except ZeroDivisionError: #Shows error message if trying didive by zero
            print("You cannot divide by zero")          

    else: 
        print ("The operator should be +, -, * or /, Please choose the correct operator")

    print(f"{x} {operator} {y} = {total}")

else:
    open_file = input("Please enter the file name: ") # User''s entering the file name
   
try:
    file = open(open_file, "r")
    print(file.read())
    

except  FileNotFoundError:
    print ("File doesn't exist")
        

""" 
I eventually couldn't work out how to use try/except code as used if/else, however mentors helped me with understanding of how to work with the files.

with open ("equation.txt", "r") as file: 
        if open_file == "equation.txt":
            file_content = file.read()
            print(file_content)
        
        else:
            print("File is not found") """
