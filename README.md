# Task-01-Caesar-Cipher
Cybersecurity Internship Tasks
def caesar_cipher(text, shift, mode):
    result = ""

    for char in text:
        if char.isalpha():
            if char.isupper():
                base = ord('A')
            else:
                base = ord('a')

            if mode == "encrypt":
                new_char = chr((ord(char) - base + shift) % 26 + base)
            else:
                new_char = chr((ord(char) - base - shift) % 26 + base)

            result += new_char
        else:
            result += char

    return result


print("----- Caesar Cipher Program -----")

message = input("Enter the message: ")
shift = int(input("Enter shift value: "))
choice = input("Enter encrypt or decrypt: ").lower()

if choice == "encrypt":
    print("Encrypted Message:", caesar_cipher(message, shift, "encrypt"))
elif choice == "decrypt":
    print("Decrypted Message:", caesar_cipher(message, shift, "decrypt"))
else:
    print("Invalid choice!")
