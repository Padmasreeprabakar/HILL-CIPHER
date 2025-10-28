# HILL CIPHER
HILL CIPHER
EX. NO: 3 AIM:
 

IMPLEMENTATION OF HILL CIPHER
 
## To write a C program to implement the hill cipher substitution techniques.

## DESCRIPTION:

Each letter is represented by a number modulo 26. Often the simple scheme A = 0, B
= 1... Z = 25, is used, but this is not an essential feature of the cipher. To encrypt a message, each block of n letters is  multiplied by an invertible n × n matrix, against modulus 26. To
decrypt the message, each block is multiplied by the inverse of the m trix used for
 
encryption. The matrix used
 
for encryption is the cipher key, and it sho
 
ld be chosen
 
randomly from the set of invertible n × n matrices (modulo 26).


## ALGORITHM:

STEP-1: Read the plain text and key from the user. STEP-2: Split the plain text into groups of length three. STEP-3: Arrange the keyword in a 3*3 matrix.
STEP-4: Multiply the two matrices to obtain the cipher text of length three.
STEP-5: Combine all these groups to get the complete cipher text.

## PROGRAM 

```c
#include <stdio.h>
#include <string.h>

int main() {
    unsigned int key[3][3] = { {6,24,1}, {13,16,10}, {20,17,15} };      // Encryption key
    unsigned int invKey[3][3] = { {8,5,10}, {21,8,21}, {21,12,8} };    // Decryption key
    unsigned int num[3], res[3];
    char msg[4];   // buffer for 3 letters + null terminator
    int i, j, t;

    printf("Enter a 3-letter word: ");
    scanf("%3s", msg);

    if(strlen(msg)!=3){
        printf("Error: Input must be exactly 3 letters.\n");
        return 1;
    }

    // Convert letters to numbers
    for(i=0;i<3;i++) num[i] = msg[i]-'A';

    // Encrypt
    for(i=0;i<3;i++){
        t=0;
        for(j=0;j<3;j++) t += key[i][j]*num[j];
        res[i] = t%26;
    }
    printf("Encrypted Cipher Text: ");
    for(i=0;i<3;i++) printf("%c", res[i]+'A');

    // Decrypt
    for(i=0;i<3;i++){
        t=0;
        for(j=0;j<3;j++) t += invKey[i][j]*res[j];
        num[i] = t%26;
    }
    printf("\nDecrypted Plain Text: ");
    for(i=0;i<3;i++) printf("%c", num[i]+'A');

    printf("\n");
    return 0;
}
```

## OUTPUT

<img width="427" height="202" alt="image" src="https://github.com/user-attachments/assets/55e3c93d-7ed3-419f-8615-5b9788072199" />

## RESULT
A C program to implement the hill cipher substitution technique has been implemented.
