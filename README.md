# 8 Implementation of error detection using CRC CCITT [16 bit] technique

# CRC-16 Bit Error Detection 

## 🧠 AIM
To write a program for error detection using the Cyclic Redundancy Check (CRC-16 bit) technique.

## 🛠️ EQUIPMENTS REQUIRED
1. Personal Computer  
2. C++ Compiler

## 📋 ALGORITHM
1. Open Code::Blocks application and create a new file.  
2. Type the code provided below.  
3. Save the file with a `.c` extension in the desired location.  
4. Run the program using **Build and Run**.  
5. Provide polynomial values to generate the output polynomial using the CRC error detection technique.  
6. The output polynomial is obtained through this technique.

## 💻 PROGRAM

```c
#include<stdio.h>
#include<string.h>
#define Nstrlen(g)

char t[128], cs[128], g[] = "111";
int a, e, c;

void xor() {
    for(c = 1; c < N; c++)
        cs[c] = ((cs[c] == g[c]) ? '0' : '1');
}

void crc() {
    for(e = 0; e < N; e++)
        cs[e] = t[e];
    do {
        if(cs[0] == '1')
            xor();
        for(c = 0; c < N - 1; c++)
            cs[c] = cs[c + 1];
        cs[c] = t[e++];
    } while(e <= a + N - 1);
}

void main() {
    printf("\nEnter poly: ");
    scanf("%s", t);
    printf("\nGen poly is: %s", g);
    a = strlen(t);
    for(e = a; e < a + N - 1; e++)
        t[e] = '0';
    printf("\nModified t[u]: %s", t);
    crc();
    printf("\nChecksum is: %s", cs);
    for(e = a; e < a + N - 1; e++)
        t[e] = cs[e - a];
    printf("\nFinal code word is: %s", t);
    printf("\nTest error detection 0(yes) 1(no)?: ");
    scanf("%d", &e);
    if(e == 0) {
        printf("Enter position where error is to be inserted: ");
        scanf("%d", &e);
        t[e] = (t[e] == '0') ? '1' : '0';
        printf("Erroneous data: %s\n", t);
    }
    crc();
    for(e = 0; (e < N - 1) && (cs[e] != '1'); e++);
    if(e < N - 1)
        printf("Error detected");
    else
        printf("No error detected");



}

## 💻 OUTPUT

<img width="724" height="331" alt="image" src="https://github.com/user-attachments/assets/1f5d9e2b-ad28-4b27-8d96-a50fc26f9752" />

RESULT
Thus the error detection using CRC-CCITT[16 bit] technique is implemented and the output is obtained and verified successfully.



