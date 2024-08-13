#include <stdio.h> 
#include <ctype.h> 
#include <string.h> 
#define ALPHABET_SIZE 26 
void completeKey(char key[]) {
 int used[ALPHABET_SIZE] = {0}; 
 int key_len = strlen(key);
 int idx = key_len; 
 // Mark the used letters in the partial key 
 for (int i = 0; i < key_len; i++) {
 if (isalpha(key[i])) {
 used[tolower(key[i]) - 'a'] = 1; 
 } 
 } 
 // Fill the remaining letters in the key 
 for (int i = 0; i < ALPHABET_SIZE; i++) {
 if (!used[i]) {
 key[idx++] = 'a' + i; 
 } 
 } 
 key[idx] = '\0'; 
} 
char encryptChar(char c, char key[]) {
 if (isalpha(c)) {
 if (islower(c)) {
 return tolower(key[c - 'a']);
 } else { 
 return toupper(key[c - 'A']);
 } 
 } 
 return c; 
} 
char decryptChar(char c, char key[]) {
 for (int i = 0; i < ALPHABET_SIZE; i++) {
 if (tolower(c) == tolower(key[i])) {
 if (islower(c)) {
 return 'a' + i; 
 } else { 
 return 'A' + i; 
 } 
 } 
 } 
 return c; 
} 
void encrypt(char plaintext[], char key[]) {
 int length = strlen(plaintext);
 for (int i = 0; i < length; i++) {
 plaintext[i] = encryptChar(plaintext[i], key);
 } 
} 
void decrypt(char ciphertext[], char key[]) {
 int length = strlen(ciphertext);
 for (int i = 0; i < length; i++) {
 ciphertext[i] = decryptChar(ciphertext[i], key);
 } 
} 
int main() {
 char key[30] = {0}; // Initialize the key array with null characters 
 char plaintext[1000]; 
 printf("Enter the plaintext: ");
 fgets(plaintext, sizeof(plaintext), stdin);
 printf("Enter the partial key: ");
 fgets(key, sizeof(key), stdin);
 // Remove newline character if present in plaintext 
 if (plaintext[strlen(plaintext) - 1] == '\n') {
 plaintext[strlen(plaintext) - 1] = '\0'; 
 } 
 // Remove newline character if present in key 
 if (key[strlen(key) - 1] == '\n') {
 key[strlen(key) - 1] = '\0'; 
 } 
 // Complete the key with remaining alphabet letters 
 completeKey(key);
 printf("Completed key: %s\n", key);
 char ciphertext[strlen(plaintext) + 1];
 strcpy(ciphertext, plaintext);
 // Encrypt plaintext 
 encrypt(ciphertext, key);
 printf("Ciphertext: %s\n", ciphertext);
 // Decrypt ciphertext 
 decrypt(ciphertext, key);
 printf("Decrypted plaintext: %s\n", ciphertext);
 return 0; 
} 
