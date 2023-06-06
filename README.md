def encrypt(message, key):
    encrypted_message = ""
    for char in message:
        if char.isalpha():
            if char.isupper():
                encrypted_char = chr((ord(char) + key - 65) % 26 + 65)
            else:
                encrypted_char = chr((ord(char) + key - 97) % 26 + 97)
        else:
            encrypted_char = char
        encrypted_message += encrypted_char
    return encrypted_message


def decrypt(encrypted_message, key):
    decrypted_message = ""
    for char in encrypted_message:
        if char.isalpha():
            if char.isupper():
                decrypted_char = chr((ord(char) - key - 65) % 26 + 65)
            else:
                decrypted_char = chr((ord(char) - key - 97) % 26 + 97)
        else:
            decrypted_char = char
        decrypted_message += decrypted_char
    return decrypted_message


# Example usage
message = "Hello, World!"
key = 3

encrypted = encrypt(message, key)
print("Encrypted message:", encrypted)

decrypted = decrypt(encrypted, key)
print("Decrypted message:", decrypted)
