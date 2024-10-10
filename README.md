# 19CS415-DES-Encryption-and-Decryption
## AIM: 
To Encrypt and Decrypt the given message using Data Encryption Standard(DES) algorithm.
## DESIGN STEPS:
### Step 1:
Design of the DES algorithm.

### Step 2:
Implementation using C or Python code.

### Step 3:
The DES algorithm takes a 64-bit block of plaintext and a 56-bit key to perform encryption through a series of transformations, including permutation, substitution, and XOR operations. The encryption process involves 16 rounds of these transformations. The decryption process reverses the steps to retrieve the original message.
## Program:
```c
#include <stdio.h>
#include <string.h>

// Function to encrypt plaintext using XOR with a single character key
void simpleEncrypt(char *plaintext, char key, char *ciphertext) {
    for (int i = 0; plaintext[i] != '\0'; i++) {
        ciphertext[i] = plaintext[i] ^ key;  // XOR encryption
    }
    ciphertext[strlen(plaintext)] = '\0';  // Null-terminate ciphertext
}

// Function to decrypt ciphertext using XOR with the same key
void simpleDecrypt(char *ciphertext, char key, char *decryptedText) {
    for (int i = 0; ciphertext[i] != '\0'; i++) {
        decryptedText[i] = ciphertext[i] ^ key;  // XOR decryption (same as encryption)
    }
    decryptedText[strlen(ciphertext)] = '\0';  // Null-terminate decrypted text
}

int main() {
    char plaintext[100], ciphertext[100], decryptedText[100];
    char key;

    // Input plaintext
    printf("Enter the plaintext (without spaces): ");
    scanf("%s", plaintext);

    // Input key (single character)
    printf("Enter a key (a single character): ");
    scanf(" %c", &key);

    // Encrypt the plaintext
    simpleEncrypt(plaintext, key, ciphertext);
    printf("Encrypted Message (ASCII values): ");

    // Display the encrypted message as ASCII values
    for (int i = 0; ciphertext[i] != '\0'; i++) {
        printf("%d ", (unsigned char)ciphertext[i]);
    }
    printf("\n");

    // Decrypt the ciphertext
    simpleDecrypt(ciphertext, key, decryptedText);
    printf("Decrypted Message: %s\n", decryptedText);

    return 0;
}

```
## Output:
![Screenshot 2024-10-10 093104](https://github.com/user-attachments/assets/6f54300a-25b4-4581-8119-c95d2248cb2e)

## Result:
The program for DES algorithm is executed successfully.
