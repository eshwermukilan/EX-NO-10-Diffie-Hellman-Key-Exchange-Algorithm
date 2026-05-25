# EX-NO-10-Diffie-Hellman-Key-Exchange-Algorithm

## AIM:
To Implement Diffie Hellman Key Exchange Algorithm 

## Algorithm:

1. Diffie-Hellman Key Exchange is used for securely sharing a secret key between two parties over an insecure channel.

2. Initialization: Agree on a large prime number \( p \) and a primitive root \( g \) modulo \( p \) (both are public values).

3. Key Exchange Process: 
   - Each party selects a private key and calculates their public key using the formula \( g^{\text{private key}} \mod p \).
   - Each party then shares their public key with the other.

4. Secret Key Computation: 
   - Each party computes the shared secret key using the received public key and their own private key.

5. Security: The difficulty of computing discrete logarithms ensures that the shared key remains secure even if public values are intercepted.

## Program:
```
#include <math.h>
#include <stdio.h>

long long int power(long long int a, long long int b, long long int P)
{
    if (b == 0)
        return 1;
    else if (b == 1)
        return a % P;
    else
        return ((long long int)pow(a, b)) % P;
}

int main()
{
    long long int P, G, x, a, y, b, ka, kb;

    printf("\n**Diffie-Hellman Key Exchange Algorithm**\n\n");

    printf("Enter the value of P: ");
    scanf("%lld", &P);
    printf("The value of P: %lld\n", P);

    printf("Enter the value of G (Primitive root of P): ");
    scanf("%lld", &G);
    printf("The value of G: %lld\n\n", G);

    printf("Enter the private key a for Alice: ");
    scanf("%lld", &a);
    printf("The private key a for Alice: %lld\n", a);

    printf("Enter the private key b for Bob: ");
    scanf("%lld", &b);
    printf("The private key b for Bob: %lld\n\n", b);

    
    x = power(G, a, P);   
    y = power(G, b, P);   

    printf("Public key for Alice: %lld\n", x);
    printf("Public key for Bob: %lld\n\n", y);

    ka = power(y, a, P);  
    kb = power(x, b, P);

    printf("Secret key for Alice is: %lld\n", ka);
    printf("Secret key for Bob is: %lld\n", kb);

    return 0;
}
```


## Output:
<img width="1920" height="1200" alt="Screenshot (166)" src="https://github.com/user-attachments/assets/c1b75856-4310-4ecd-8005-68954bc2988b" />



## Result:

The program is executed successfully

