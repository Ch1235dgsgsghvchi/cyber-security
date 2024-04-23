# cyber-security
def encrypt(text, shift):
    encrypted_text = ''
    for char in text:
        if char.isalpha():
            shifted = ord(char) + shift
            if char.islower():
                if shifted > ord('z'):
                    shifted -= 26
                elif shifted < ord('a'):
                    shifted += 26
            elif char.isupper():
                if shifted > ord('Z'):
                    shifted -= 26
                elif shifted < ord('A'):
                    shifted += 26
            encrypted_text += chr(shifted)
        else:
            encrypted_text += char
    return encrypted_text

def decrypt(encrypted_text, shift):
    decrypted_text = ''
    for char in encrypted_text:
        if char.isalpha():
            shifted = ord(char) - shift
            if char.islower():
                if shifted > ord('z'):
                    shifted -= 26
                elif shifted < ord('a'):
                    shifted += 26
            elif char.isupper():
                if shifted > ord('Z'):
                    shifted -= 26
                elif shifted < ord('A'):
                    shifted += 26
            decrypted_text += chr(shifted)
        else:
            decrypted_text += char
    return decrypted_text

def main():
    choice = input("Enter 'E' for encryption or 'D' for decryption: ").upper()
    if choice == 'E':
        text = input("Enter the message to encrypt: ")
        shift = int(input("Enter the shift value: "))
        encrypted_text = encrypt(text, shift)
        print("Encrypted text:", encrypted_text)
    elif choice == 'D':
        text = input("Enter the message to decrypt: ")
        shift = int(input("Enter the shift value: "))
        decrypted_text = decrypt(text, shift)
        print("Decrypted text:", decrypted_text)
    else:
        print("Invalid choice. Please enter 'E' for encryption or 'D' for decryption.")

if __name__ == "__main__":
    main()
