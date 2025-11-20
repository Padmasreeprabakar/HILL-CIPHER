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
```
int main()
{
 unsigned int key[3][3] = {{6, 24, 1}, {13, 16, 10}, {20, 17, 15}};
 unsigned int inverseKey[3][3] = {{8, 5, 10}, {21, 8, 21}, {21, 12, 8}};

 char msg[4];
 unsigned int enc[3] = {0}, dec[3] = {0};

 printf("Enter plain text: ");
 scanf("%3s", msg);

 for (int i = 0; i < 3; i++)
 for (int j = 0; j < 3; j++)
 enc[i] += key[i][j] * (msg[j] - 'A') % 26;

 printf("Encrypted Cipher Text: %c%c%c\n", enc[0] % 26 + 'A', enc[1] % 26 + 'A', enc[2] %
26 + 'A');

 for (int i = 0; i < 3; i++)
 for (int j = 0; j < 3; j++)
 dec[i] += inverseKey[i][j] * enc[j] % 26;

 printf("Decrypted Cipher Text: %c%c%c\n", dec[0] % 26 + 'A', dec[1] % 26 + 'A', dec[2] 
% 26 + 'A');

 return 0;
}
```
## OUTPUT
<img width="578" height="288" alt="Screenshot 2025-08-21 141837" src="https://github.com/user-attachments/assets/885259cf-c6f8-411c-8cc4-3e6bc1281d7e" />

## RESULT
C program to implement the hill cipher substitution techniques executed sucessfully.
