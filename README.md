<h1>Password Strength Checker Lab</h1>

<h2>Description</h2>
This is a script that checks the strength of a given password. The script first imports the regular expression library (re) and defines the minimum password length. Next, it defines a function called "check_password_strength" which takes in a password as a parameter. The function checks the length of the password and makes sure it's at least 8 characters long. If the password is too short it returns "Too short". If the length is ok, it uses regular expressions to check if the password contains at least one uppercase letter, one lowercase letter, one digit and one special character, If any of these conditions is not met, it returns the corresponding message. If all the conditions passed, it returns "Strong". Finally, the script tests the function by taking a password as input and check the strength of the password by calling the function and printing the result.
<br />


<h2>Languages and Utilities Used</h2>

- <b>Python</b> 

<h2>Environments Used </h2>

- <b>Windows 11</b>

<h2>Program Walkthrough:</h2>

<b>Step 1: This line imports the regular expression library, which will be used to check for certain patterns in the password.</b>

```python
import re
```
<b>Step 2: This line defines a variable "MIN_LENGTH" and assigns it a value of 8. This variable will be used to check if the password is long enough.</b>

```python
MIN_LENGTH = 8
```

<b>Step 3: This is the start of the function "check_password_strength" that takes in a single argument, "password", which is the password that will be checked for strength.</b>

```python
def check_password_strength(password):
```
<b>Step 4:This block of code checks if the length of the "password" is less than the MIN_LENGTH variable. If it is, the function returns the string "Too short".</b>

```python
if len(password) < MIN_LENGTH:
        return "Too short"
```
<b>Step 5:This block of code uses the re.search function to check if there is at least one uppercase letter in the password. If there is not, the function returns the string "Missing uppercase letter".</b>

```python
elif not re.search("[A-Z]", password):
        return "Missing uppercase letter"
```
<b>Step 6: This block of code is similar to the previous one but it checks for the presence of at least one lowercase letter in the password. If there is not, the function returns the string "Missing lowercase letter".</b>

```python
elif not re.search("[a-z]", password):
        return "Missing lowercase letter"
```
<b>Step 7: This block of code is similar to the previous one but it checks for the presence of at least one digit in the password. If there is not, the function returns the string "Missing digit".</b>

```python
elif not re.search("[0-9]", password):
        return "Missing digit"
```
<b>Step 8: This block of code is similar to the previous one but it checks for the presence of at least one special character in the password. If there is not, the function returns the string "Missing special character".</b>

```python
elif not re.search("[!@#\$%^&\*]", password):
        return "Missing special character"
```

<b>Step 9: If nothing else presents itself as an error the code will consider the password to be a "Strong" type</b>

```python
  else:
        return "Strong"
```
<b>Step 10: Lastly test the password checking funtion to make sure the password provided matches the check put into place before. Print the result either "Weak" or "Strong"</b>
        
```python
    # Step 3: Test the password checking function
password = input("Enter a password: ")
result = check_password_strength(password)
print(result)
```
<b> The final result should look like this:</b>
```python
import re

# Step 1: Define the minimum password length
MIN_LENGTH = 8

# Step 2: Define the password checking function
def check_password_strength(password):
    # Step 2.1: Check the password length
    if len(password) < MIN_LENGTH:
        return "Too short"
    # Step 2.2: Check for the presence of at least one uppercase letter
    elif not re.search("[A-Z]", password):
        return "Missing uppercase letter"
    # Step 2.3: Check for the presence of at least one lowercase letter
    elif not re.search("[a-z]", password):
        return "Missing lowercase letter"
    # Step 2.4: Check for the presence of at least one digit
    elif not re.search("[0-9]", password):
        return "Missing digit"
    # Step 2.5: Check for the presence of at least one special character
    elif not re.search("[!@#\$%^&\*]", password):
        return "Missing special character"
    else:
        return "Strong"

# Step 3: Test the password checking function
password = input("Enter a password: ")
result = check_password_strength(password)
print(result)
```
