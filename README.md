##Języki programowania

![C](http://upload.wikimedia.org/wikipedia/commons/thumb/3/35/The_C_Programming_Language_logo.svg/226px-The_C_Programming_Language_logo.svg.png)

[Programowanie w C](http://en.wikipedia.org/wiki/C_(programming_language))

[Biblioteka komend](http://www.cplusplus.com/doc/tutorial/)

**a) operacje**
```c
#include<stdio.h>
int main(){
	int a, b;
	printf("podaj dwie liczby:\n");
	scanf("%d %d", &a, &b);
	printf("%d+%d=%d\n", a, b, a+b);
	printf("%d-%d=%d\n", a, b, a-b);
	printf("%d*%d=%d\n", a, b, a*b);
	printf("%d/%d=%lf\n", a, b, (double)a/b);
	getchar(); getchar();
	return 0;
}
```

**b) temperatury**
```c
#include<stdio.h>
//pierwszy sposób
/*int main(){
	double fahr, celsius;
	int lower=0, upper=300, step=20;
	fahr=lower; 
	while(fahr<=upper){
		celsius=(5.0/9.0)*(fahr-32.0);
		printf("%3.0lf %6.1lf\n", fahr, celsius);
		fahr=fahr+step;
	}
	return 0;
} */
//drugi sposób
/*int main(){
	double fahr; 
	for(fahr=0;fahr<=300;fahr+=20){
		printf("%3.0lf %6.1lf\n", fahr, (5.0/9)*(fahr-32));
	}
	return 0;
} */
int main(){
	double fahr=0; 
	do {
		printf("%3.0lf %6.1lf\n", fahr, (5.0/9)*(fahr-32));
		fahr+=20;
	} while(fahr<=300);
	return 0;
}
```

**c) fibonacci**
```c
#include<stdio.h>
int main(){
	int a1=1, a2=1, a3, n=2;
	printf("1, 1, ");
	do{
		a3=a1+a2;
		printf("%d, ", a3);
		a1=a2; a2=a3;
		n++;
	} while(n<45);
	return 0;
}
```

**d) trojkat**
```c
#include<stdio.h>
#define znak '*' //znak wypelnienia

main(){
	int lbwier, lw, lodst, j; //całkowita liczba, licznik wierszy, liczba odstępów
	
	printf("ile wierszy?");
	scanf("%d", &lbwier);
	
	for (lw=0;lw<lbwier;lw++){
		lodst=lbwier-lw-1;
		for(j=0;j<lodst;j++) putchar (' ');
		for(j=0;j<2*lw+1;j++) putchar(znak);
		putchar('\n');
	}
	
}
```

**01) liczby do 23**
```c
#include<stdio.h>
//pierwszy sposób
int raz(){
	int liczba=0;
	while(liczba<=23){
		printf("%d ", liczba);
		liczba+=1;
	}
	return 0;
} 
//drugi sposób
int dwa(){
	int liczba; 
	for(liczba=0;liczba<=23;liczba+=1){
		printf("%d ", liczba);
	}
	return 0;
} 
//trzeci sposób
int trzy(){
	int liczba=0; 
	do {
		printf("%d ", liczba);
		liczba+=1;
	} while(liczba<=23);
	return 0;
}
int main(){
	raz();
	printf("\n");
	dwa();
	printf("\n");
	trzy();
	printf("\n");
}
```

**02) dodawanie co 0,5**
```c
#include<stdio.h>
int raz(){
	double liczba; 
	for(liczba=-3.5;liczba<=7.5;liczba+=0.5){
		printf("%1.1lf ", liczba);
	}
	return 0;
}
int dwa(){
	double liczba=-3.5; 
	while(liczba<=7.5){
		printf("%1.1lf ", liczba);
		liczba+=0.5;
	}
	return 0;
}
int main(){
	raz();
	printf("\n");
	dwa();
	printf("\n");
}
```

**03) kwadraty i szesciany**
```c
#include<stdio.h>
//pierwszy sposób
int raz(){
	int liczba=1, n;
	printf("Podaj gorna granice obliczen:");
	scanf("%d", &n);
	while(liczba<=n){
		printf("kwadrat %d=%d, szescian %d=%d \n", liczba, liczba*liczba, liczba, liczba*liczba*liczba);
		liczba+=1;
	}
	return 0;
} 
//drugi sposób
int dwa(){
	int liczba, n; 
	printf("Podaj gorna granice obliczen:");
	scanf("%d", &n);
	for(liczba=1;liczba<=n;liczba+=1){
		printf("kwadrat %d=%d, szescian %d=%d \n", liczba, liczba*liczba, liczba, liczba*liczba*liczba);
	}
	return 0;
} 
//trzeci sposób
int trzy(){
	int liczba=1, n; 
	printf("Podaj gorna granice obliczen:");
	scanf("%d", &n);
	do {
		printf("kwadrat %d=%d, szescian %d=%d \n", liczba, liczba*liczba, liczba, liczba*liczba*liczba);
		liczba+=1;
	} while(liczba<=n);
	return 0;
}
int main(){
	raz();
	printf("\n");
	dwa();
	printf("\n");
	trzy();
	printf("\n");
}
```

**04) suma kwadratow**
```c
#include<stdio.h>
int raz(){
	int liczba, wynik=0; 
	for(liczba=3;liczba<=15;liczba+=1){
		printf("%d ", wynik+=liczba*liczba);
		}
	return 0;
}
int dwa(){
	int liczba=3, wynik=0; 
	while(liczba<=15){
		printf("%d ", wynik+=liczba*liczba);
		liczba+=1;
	}
	return 0;
}
int main(){
	raz();
	printf("\n");
	dwa();
	printf("\n");
}
```

**05) sinus i cosinus**
```c
#include<stdio.h>
#include<math.h>
int main(){
	int stopni; 
	for(stopni=0;stopni<=180;stopni+=30){
		printf("Sinus %d stopni to %lf, cosinus to %lf \n", stopni, (double)sin(stopni*M_PI/180), (double)cos(stopni*M_PI/180));
	}
	return 0;
} 
```

**06) suma i srednia**
```c
#include<stdio.h>
int main(){
	int n, i, suma=0, a;
	printf("podaj ilosc liczb: ");
	scanf("%d", &n);
	for(i=1;i<=n;i++){
		printf("podaj %d liczbe: ", i);
		scanf("%d", &a);
		suma+=a;
	}
	printf("suma liczb: %d\n", suma);
	printf("srednia arytmetyczna liczb: %20.2lf", (double)suma/n);
	
}
```

**07) ascii, dziesietne i hexy**
```c
#include<stdio.h>
main(){
	char i;
	for(i='a';i<='k';i++){
		printf("%c %d %x \n", i, i, i);
	}
	printf("\n");
	for(i='k';i>='a';i--){
		printf("%c %d %x \n", i, i, i);
	}
}
```

**08) wstukiwanie do x**
```c
#include<stdio.h>
int main(){
	int x;
	printf("podaj znaki: ");
	while((x=getchar())!='x'){
		putchar(x);
	}
	return 0;
} 
```

**09) tabliczka 13*13**
```c
#include<stdio.h>
int main(){
	int i, n;
	for (i=1;i<=13;i++){
		for (n=1;n<=13;n++) {
			printf("%d*%d=%d ", i, n, i*n );
		}
	printf("\n");
	}
}
```

**wesja b**
```c
#include<stdio.h>
int main(){
	int i, n;
	printf("    ");
	for (i=1;i<=13;i++){
		printf ("%4d", i);
}
	printf("\n");
	for (i=1;i<=13;i++){
		printf("%4d", i);
		for (n=1;n<=13;n++) {
			printf("%4d", i*n );
		}
	printf("\n");
	}
}
```

**10) trójkąty pitagorejskie**
```c
#include<stdio.h>
#include<math.h>
int main(){
	int a,b,c;
	for(a=3;a<=100;a++){
		for(b=4;b<=100;b++){
			for (c=5;c<=100;c++){
						if ((a*a+b*b)==(c*c) && a<b)
			printf("%d %d %d \n", a, b, c);
			}
		}
	
	}
}
```
Drugie zajecia	

**11) pierwiastki trójmianu kwadratowego**
```c
#include<stdio.h>
#include<math.h>
main(){
	int a, b, c;
	printf("Podaj pierwsza liczbe trojmianu: ");
	scanf("%d", &a);
	printf("Podaj druga liczbe trojmianu: ");
	scanf("%d", &b);
	printf("Podaj trzecia liczbe trojmianu: ");
	scanf("%d", &c);
		
	if (b*b-4*a*c>0){
		printf ("%lf %lf", (double)(-b-sqrt(b*b-4*a*c))/(2*a), (double)(-b+sqrt(b*b-4*a*c))/(2*a));
	}
	else if (b*b-4*a*c==0) printf ("%lf", (double)(-b/2*a));
		else printf("Nie ma rozwiazan");
}
```

**12) liczby doskonałe**

```c
#include<stdio.h>
#include<math.h>
int main(){
	int i,n,porow;
	for(i=6;i<=8200;i++){;
		porow=0;
		for(n=1;n<=i/2;n++){
			if(i%n==0) porow+=n;
		}
		if(porow==i)printf ("%d\n", porow);
		
		
	}
}
```

**13) 20 trojek pitagorejskich**
```c
#include<stdio.h>
int main(){
	int a,b,c,i=1;
		for(a=3;i<=20;a++){
			for(b=4;b<=100;b++){
				for (c=5;c<=100;c++){
						if ((a*a+b*b)==(c*c) && a<b){
				printf("%d %d %d \n", a, b, c);
				i++;
				}
		 	}
		}

	}
}
```

**14) Liczby zmiennoprzecinkowe**
```c
#include<stdio.h>
int main(){
	int n,i;
	double a, b, c;
	double zero=0.0;
	double max=-1/zero;
	double min=1/zero;
	puts("Ile bedzie liczb zmiennoprzecinkowych?");
	scanf("%d", &n);
	for(i=1;i<=n;i++){
		printf("Podaj %d liczbe: ", i);
		scanf("%lf", &a);
		if(a<min) min=a;
		if(a>max) max=a;
	}
	printf("Najmniejsza z podanych liczba to %lf, a najwieksza to %lf.", min, max);
}
```

**15) Dni tygodnia**
```c
#include<stdio.h>
int main(){
	int i;
	printf("Podaj numer dnia tygodnia: ");
	scanf("%d", &i);
	switch(i){
	case 1:	puts("Poniedzialek");	break;
	case 2:	puts("Wtorek"); break;
	case 3:	puts("Sroda"); break;
	case 4:	puts("Czwartek");	break;
	case 5:	puts("Piatek"); break;
	case 6:	puts("Sobota"); break;
	case 7:	puts("Niedziela"); break;
	default: puts("Nie ma takiego dnia tygodnia."); break;
	}
}
```

[komendy funkcji](http://www.cplusplus.com/doc/tutorial/functions/)

**extra) trójkąty z funkcją**
```c
#include<stdio.h>
#include<math.h>

double pole(double a, double b, double c){
	if (a+b>c && a+c>b && b+c>a){
		return((sqrt((a+b+c)*(a+b-c)*(a-b+c)*(-a+b+c)))/4);
	}
	else return(-1);
	
}

int main(){
	double a, b, c;
	puts("Podaj dlugosci bokow trojkata:");
	scanf("%lf", &a);
	scanf("%lf", &b);
	scanf("%lf", &c);
	if ((pole(a, b, c))==-1) puts("Nie ma takiego trojkata");
	else printf("Pole wynosi: %lf", pole(a, b, c));
}
```

**Zadania - funkcje**

**1)pole (powierzchnia?) kuli**

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
#include<stdio.h>
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
}
```

**3) potęgi (nie dla rekurencji)**

```c
#include<stdio.h>


int potega(int n, int a){
	int i, wynik=a;
	for(i=1;i<n;i++) {
	wynik*=a;
	}
	return(wynik);
}

int main(){
	int a, n;
	puts("Podaj liczbe:");
	scanf("%d", &a);
	puts("Podaj potege:");
	scanf("%d", &n);
	printf("%d do potegi %d to %d", a, n, potega(n, a));
}
```
**[Funkcje -c.d.](https://github.com/bmlewczuk/Programowanie/blob/master/Funkcje.md)**
