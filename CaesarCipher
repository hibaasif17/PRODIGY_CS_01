def caesar_cipher(text, shift, mode):
    result = ""
    
    # Ensure the shift is within the range of 0-25
    shift = shift % 26

    for char in text:
        if char.isalpha():  # Check if the character is a letter
            # Determine the ASCII offset based on uppercase or lowercase
            offset = ord('A') if char.isupper() else ord('a')
            # Encrypt or decrypt based on the mode
            if mode == 'encrypt':
                new_char = chr((ord(char) - offset + shift) % 26 + offset)
            elif mode == 'decrypt':
                new_char = chr((ord(char) - offset - shift) % 26 + offset)
            result += new_char
        else:
            # Non-alphabetical characters are added unchanged
            result += char

    return result

def main():
    print("Caesar Cipher Program")
    
    while True:
        # Loop until a valid mode is entered
        mode = input("Choose mode (encrypt/decrypt): ").strip().lower()
        if mode not in ['encrypt', 'decrypt']:
            print("Invalid mode. Please choose 'encrypt' or 'decrypt'.")
            continue

        message = input("Enter your message: ")

        # Handle non-integer inputs for the shift value
        while True:
            try:
                shift = int(input("Enter the shift value (positive/negative allowed): "))
                break
            except ValueError:
                print("Invalid input. Please enter a valid integer for the shift value.")

        if mode == 'encrypt':
            encrypted_message = caesar_cipher(message, shift, 'encrypt')
            print(f"Encrypted Message: {encrypted_message}")
        else:
            decrypted_message = caesar_cipher(message, shift, 'decrypt')
            print(f"Decrypted Message: {decrypted_message}")
        
        # Ask if the user wants to continue or quit
        cont = input("Would you like to perform another operation? (yes/no): ").strip().lower()
        if cont != 'yes':
            print("Goodbye!")
            break

if __name__ == "__main__":
    main()
