# Python-Password-Strength-Checker
#Source Code Here
import re  # Regular Expression module

def password_strength_checker(password):
    if len(password) < 8 or len(password) > 10:
        return "Please enter 8 to 10 characters password"

    strength_point = 0

    if re.search(r'[A-Z]', password):
        strength_point += 1
    if re.search(r'[a-z]', password):
        strength_point += 1
    if re.search(r'\d', password):
        strength_point += 1
    if re.search(r'[@#$%^&*,/.]', password):
        strength_point += 1
    if len(password) >= 8:
        strength_point += 1

    if strength_point == 5:
        return f"Your Password Strength is STRONG 🔥"
    elif strength_point >= 3:
        return f"Your Password Strength is MEDIUM ⚠️"
    else:
        return f"Your Password Strength is WEAK ❌"

while True:
    user_input = input("Enter your password: ")
    print(password_strength_checker(user_input))
