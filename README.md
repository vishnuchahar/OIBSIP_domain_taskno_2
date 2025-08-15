# OIBSIP_domain_taskno_2
oibsip internship projects are listed here aecond one random password generator
How it works:

1.Imports:

string.ascii_letters → letters (uppercase + lowercase)

string.digits → numbers (0-9)

string.punctuation → special symbols

2.Ensures at least one letter, one digit, and one symbol for strong security.

3.Fills the rest randomly from all characters.

4.Shuffles to avoid predictable order.

5.Returns as a string.
import random
import string

def generate_password(length=12):
    # Define character sets
    letters = string.ascii_letters  # A-Z and a-z
    digits = string.digits          # 0-9
    symbols = string.punctuation    # Special characters

    # Combine all characters
    all_chars = letters + digits + symbols

    # Ensure password has at least one letter, one digit, and one symbol
    password = [
        random.choice(letters),
        random.choice(digits),
        random.choice(symbols)
    ]

    # Fill the rest of the password length with random characters
    password += random.choices(all_chars, k=length - 3)

    # Shuffle the list to make it random
    random.shuffle(password)

    # Join list to form the password string
    return ''.join(password)

# Example usage
print("Generated password:", generate_password(12))
