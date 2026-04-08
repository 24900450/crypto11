# EX-NO-11-ELLIPTIC-CURVE-CRYPTOGRAPHY-ECC


## NAME : SURYANARAYANAN T
## REG NO: 212224040341


## Aim:
To Implement ELLIPTIC CURVE CRYPTOGRAPHY(ECC)


## ALGORITHM:

1. Elliptic Curve Cryptography (ECC) is a public-key cryptography technique based on the algebraic structure of elliptic curves over finite fields.

2. Initialization:
   - Select an elliptic curve equation \( y^2 = x^3 + ax + b \) with parameters \( a \) and \( b \), along with a large prime \( p \) (defining the finite field).
   - Choose a base point \( G \) on the curve, which will be used for generating public keys.

3. Key Generation:
   - Each party selects a private key \( d \) (a random integer).
   - Calculate the public key as \( Q = d \times G \) (using elliptic curve point multiplication).

4. Encryption and Decryption:
   - Encryption: The sender uses the recipient’s public key and the base point \( G \) to encode the message.
   - Decryption: The recipient uses their private key to decode the message and retrieve the original plaintext.

5. Security: ECC’s security relies on the Elliptic Curve Discrete Logarithm Problem (ECDLP), making it highly secure with shorter key lengths compared to traditional methods like RSA.

## Program:
```c
#include <stdio.h>

int main()
{
    int x, y, a, b, p;
    int lhs, rhs;

    printf("Enter curve parameters (a, b, p): ");
    scanf("%d %d %d", &a, &b, &p);

    printf("\nPoints on the Elliptic Curve:\n");

    // Find valid points (x, y)
    for(x = 0; x < p; x++)
    {
        for(y = 0; y < p; y++)
        {
            lhs = (y * y) % p;
            rhs = (x * x * x + a * x + b) % p;

            if(lhs == rhs)
            {
                printf("(%d, %d)\n", x, y);
            }
        }
    }

    // Simple key generation
    int privateKey, publicKey;

    printf("\nEnter private key: ");
    scanf("%d", &privateKey);

    publicKey = (privateKey * 2) % p; // simplified

    printf("Public Key: %d\n", publicKey);

    return 0;
}
```
## Output:
<img width="446" height="417" alt="image" src="https://github.com/user-attachments/assets/11f370c3-40e2-4638-b024-1a963b9baaf4" />

## Result:
The program is executed successfully
