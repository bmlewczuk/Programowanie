##Funkcje

**1) kula**
```c
#include<stdio.h>
#include<math.h>

double pole(double r){
	return (4*M_PI*r*r);
}

int main(){
	double r;
	puts("Podaj promien kuli:");
	scanf("%lf", &r);
	printf("Promien kuli to %lf", r);
	printf("\nPole kuli to %lf", pole(r));
}
```

**2) wartość bezwzględna**
```c
##include<stdio.h>
#include<limits.h>

unsigned int wart(int n){
	if(n<0) return(-n);
	else return(n);
}

int main(){
	int n;
	puts("Podaj liczbe calkowita:");
	scanf("%d", &n);
	printf("Jej wartosc bezwgledna to %u", wart(n));
	n=INT_MIN;
	printf(" a dla %d to %u", n, wart(n));
}
```

**3) potęgowanie proste**
```c
#include<stdio.h>


int potega(unsigned int n, int a){
	int i, wynik=1;
	for(i=0;i<n;i++) {
	wynik*=a;
	}
	return(wynik);
}

int main(){
	int a;
	unsigned int n;
	puts("Podaj liczbe:");
	scanf("%d", &a);
	puts("Podaj potege:");
	scanf("%u", &n);
	printf("%d do potegi %u to %d", a, n, potega(n, a));
}
```

**4) pierwiastki**
```c
#include<stdio.h>
#include<math.h>
#include<stdlib.h>

double pierw(double a, double x){
	double eps=1e-8;
	return((fabs(x-(a/x))<eps*x)?((x+a/x)/2):pierw(a, (x+a/x)/2));
	
}

int main(){
	double a;
	puts("Podaj liczbe:");
	scanf("%lf", &a);
	printf("Pierwiastek z %lf to %lf", a, pierw(a, a/2));
	printf("\n%lf", sqrt(a));
}
```

**5) szereg Maclaurina**
```c
#include<stdio.h>
#include<math.h>

double szereg(double x){
	double eps=1e-8;
	int i=1;
	double wyraz=1, suma=1;
	while (fabs(wyraz)>=eps){
		wyraz*=x/i;
		i++;
		suma+=wyraz;
	}
	return(suma);
}

int main(){
	double x;
	puts("Podaj liczbe:");
	scanf("%lf", &x);
	printf("\n%lf", szereg(x));
	printf("\n%lf", exp(x));
}
```


**6) szybkie potęgowanie**
```c
#include<stdio.h>

unsigned int szpot(unsigned int a, unsigned int n){
	int p=1;
	int q=a;
	for (int i=n;i>0;i/=2){
		if(i%2!=0) p*=q;
		q*=q;
	}
	return (p);
}

int main(){
	unsigned int a, n;
	puts ("Podaj liczbe naturalna""");
	scanf ("%u", &a);
	puts ("Podaj potege:");
	scanf ("%u", &n);
	printf ("Wynik to %u", szpot(a, n));
}
```

**7) szybkie potęgowanie z potęgami ujemnymi**
```c
#include<stdio.h>

double szpot(double a, int n){
	double p=1;
	double q=a;
	int i=n;
	for (int i=n;i!=0;i/=2){
		if(i%2!=0) p*=q;
		q*=q;	
	}
	if (n>=0) return (p);
	else return(1/p);
}

int main(){
	double a;
	int n;
	puts ("Podaj liczbe:");
	scanf ("%lf", &a);
	puts ("Podaj potege:");
	scanf ("%d", &n);
	printf ("Wynik to %lf", szpot(a, n));
}
```

**[Tablice](https://github.com/bmlewczuk/Programowanie/blob/master/Tablice.md)**
