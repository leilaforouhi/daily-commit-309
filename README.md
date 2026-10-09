def caesar_cipher(text, shift):
    result = []

    for char in text:
        if char.isalpha():
            base = ord("A") if char.isupper() else ord("a")
            shifted = (ord(char) - base + shift) % 26
            result.append(chr(base + shifted))
        else:
            result.append(char)

    return "".join(result)


if __name__ == "__main__":
    message = "Daily GitHub Commit"
    shift = 3

    encrypted = caesar_cipher(message, shift)
    decrypted = caesar_cipher(encrypted, -shift)

    print("Original:", message)
    print("Encrypted:", encrypted)
    print("Decrypted:", decrypted)
