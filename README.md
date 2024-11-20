#include <stdio.h>
#include <string.h>
#include <stdlib.h>

char *ChargerChaine(int N) {
    char *chaine = (char*)malloc(N+1); 
    printf("Veuillez saisir la chaine:\n");
    fgets(chaine, N, stdin);
    chaine[strcspn(chaine, "\n")] = '\0'; 
    return chaine;
}

int Longueur(char *ch) {
    return strlen(ch);
}

void ChargerTab(char *p, char Tab[]) {
    strcpy(Tab, p);
}

void InverserTab(char Tab[], char T[], int m) {
    for (int i = 0; i < m; i++) {
        T[i] = Tab[m-i-1];
    }
}

void AfficherTab(char Tab[], int m) {
    for (int i = 0; i < m; i++) {
        printf("%c", Tab[i]);
    }
    printf("\n");
}

int main() {
    int n;
    printf("Veuillez saisir la taille maximale de la chaine:\n");
    scanf("%d", &n);
    char *ch = ChargerChaine(n);
    int m = Longueur(ch);
    char Tab[m], T[m];
    ChargerTab(ch, Tab);
    printf("La chaine originale: \n");
    AfficherTab(Tab, m);
    InverserTab(Tab, T, m);
    printf("La chaine inversée:\n");
    AfficherTab(T, m);
    free(ch);
    return 0;
}