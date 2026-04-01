# testproject1
import re

def check_password(password):
    score = 0

    if len(password) >= 8:
        score += 1
    if re.search("[a-z]", password) and re.search("[A-Z]", password):
        score += 1
    if re.search("[0-9]", password):
        score += 1
    if re.search("[!@#$%^&*]", password):
        score += 1

    if score <= 2:
        return "Weak"
    elif score == 3:
        return "Medium"
    else:
        return "Strong"

pwd = input("Enter password: ")
print("Strength:", check_password(pwd))
