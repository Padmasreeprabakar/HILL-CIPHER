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
## NAME : Padma sree P
## REG NO : 212224220070

STEP-1: Read the plain text and key from the user. STEP-2: Split the plain text into groups of length three. STEP-3: Arrange the keyword in a 3*3 matrix.
STEP-4: Multiply the two matrices to obtain the cipher text of length three.
STEP-5: Combine all these groups to get the complete cipher text.

## PROGRAM :
~~~
K = [[3,3],[2,5]]
def inv(K):
    d = (K[0][0]*K[1][1] - K[0][1]*K[1][0]) % 26
    for x in range(1,26):
        if (d*x)%26==1: di=x; break
    return [[K[1][1]*di%26, -K[0][1]*di%26], [-K[1][0]*di%26, K[0][0]*di%26]]
def hill(t, K):
    t = t.upper().replace(" ","")
    if len(t)%2: t += 'X'
    r = ""
    for i in range(0,len(t),2):
        p = [ord(t[i])-65, ord(t[i+1])-65]
        e = [(K[0][0]*p[0]+K[0][1]*p[1])%26, (K[1][0]*p[0]+K[1][1]*p[1])%26]
        r += chr(e[0]+65)+chr(e[1]+65)
    return r
msg = "ANTO WILLIAMS"
enc = hill(msg, K)
dec = hill(enc, inv(K))
print("Encrypted:", enc)
print("Decrypted:", dec)
~~~

## OUTPUT:
<img width="1852" height="1098" alt="image" src="https://github.com/user-attachments/assets/b38f5870-f6aa-4e48-80f2-f25e2047deee" />


## RESULT:
The program is executed successfully
