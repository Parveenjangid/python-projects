# python-projects
# To select the random password 

import random
import string

def password_generator(length):
    characters = string.ascii_letters + string.digits + string.punctuation
    password = "".join(random.choice(characters) for i in range(length))
    if ("<" in password) or (">" in password):
        return characters
    elif check_password(password):
        return password
    
def check_password(password):
    if (any(char.islower() for char in password) and
        any(char.isupper() for char in password) and
        any(char.isdigit() for char in password) and
        any(char in string.punctuation for char in password)):
        return True
    else:
        return False
    
#_main_

def ask():
    length = int(input("Enter the length of the password: "))
    if length < 12:
        print("Password should be atleast of 12 characters")
    elif length >= 12:
        print(password_generator(length))

ask()
