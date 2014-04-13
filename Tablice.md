##Tablice

1) przód i tył
```c
#include<stdio.h>

int main(){
	int k;
	int dane[7] = {-44, 5, 67, -2, 0, 33, 77};
	for (k=0;k<7;k++){
		printf ("%d ", dane[k]);
	}
	puts("");
	for (k=6;k>=0;k--){
		printf ("%d ", dane[k]);
	}
}
```

2) sprawdzenie liczby
```c
#include<stdio.h>

int sprawdz(int dane[], int a){
	int k;
	for (k=0;k<7;k++){
		if(dane[k]==a) return(1);
	}	
}



int main(){
	int a;
	int dane[7] = {-44, 5, 67, -2, 0, 33, 77};
	printf("podaj liczbe calkowita: ");
	scanf("%d", &a);
	if (sprawdz(dane, a)==1) printf("ta liczba znajduje sie w tablicy");
	else printf("nie ma tej liczby w tablicy");
}
```

3) napis
```c
#include<stdio.h>
#include<ctype.h>
#include<string.h>
#define MAX 128

int main(){
	int c, i;
	char napis[MAX];
	printf("podaj napis malymi literami: ");
	gets(napis);
	for (c=0;c<=strlen(napis);c++){	
	printf("%c", toupper(napis[c]));
	}
}
	
```

4) liczby zmiennoprzecinkowe
```c
#include<stdio.h>
#define MAX 128

int main(){
	int n, i;
	double liczby[MAX];
	double naj=-1/0.0;
	printf("ile liczb zmiennoprzecinkowych? ");
	scanf("%d", &n);
	for(i=0;i<n;i++){
		printf("podaj %d liczbe: ", i+1);
		scanf("%lf", &liczby[i]);
	}
	for (i=0;i<n;i++){
		if(liczby[i]>naj) naj=liczby[i];
	}
	printf("najwieksza z podanych liczba jest: %lf", naj);
}
```

5) srednia artymetyczna
```c
#include<stdio.h>
#define MAX 128

int main(){
	int n, i;
	double liczby[MAX];
	double suma=0;
	printf("ile liczb zmiennoprzecinkowych? ");
	scanf("%d", &n);
	for(i=0;i<n;i++){
		printf("podaj %d liczbe: ",	i+1);
		scanf("%lf", &liczby[i]);
	}
	for (i=0;i<n;i++){
		suma+=liczby[i];
	}
	printf("srednia artymetyczna to %lf", suma/n);
}
```

6) tablice to podstawa programowania
```c
#include<stdio.h>

int main(){
	int c, i;
	char tekst[]="Tablice to podstawa programowania";
	for (c=sizeof(tekst)/sizeof(tekst[0])-2;c>=0;c--){	
		printf("%c", tekst[c]);
	}
}
```
