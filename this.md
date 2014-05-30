```c
#include<stdio.h>
#include<string.h>
#include<stdlib.h>
#include<time.h>
#define MAX 24

int czasownik(){
	int f, k, suma=0;
	char haslo[MAX], porow[MAX];
	char polski [40] [MAX]={{"byc"},{"bic"},{"zaczynac"},{"zlamac"},{"kupowac"},{"lapac"},{"przybywac"},{"ciac"},{"zrobic"},{"zjesc"},{"upadac"},{"karmic"},{"znalezc"},{"latac"},{"zapomniec"},{"dostac"},{"dac"},{"isc"},{"miec"},{"slyszec"},{"wiedziec"},{"zostawic"},{"stworzyc"},{"spotkac"},{"czytac"},{"jezdzic"},{"biegac"},{"powiedziec"},{"widziec"},{"usiasc"},{"mowic"},{"wydawac"},{"plywac"},{"wziac"},{"nauczac"},{"powiedziec komus"},{"myslec"},{"nosic"},{"wygrac"},{"pisac"}};
	char jeden [40] [MAX]={{"be"},{"beat"},{"begin"},{"break"},{"buy"},{"catch"},{"come"},{"cut"},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""}};
	char dwa [40] [MAX]={{"was/were"},{"beat"},{"began"},{"broke"},{"bought"},{"caught"},{"came"},{"cut"},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""}};
	char trzy [40] [MAX]={{"been"},{"beaten"},{"begun"},{"broken"},{"bought"},{"caught"},{"come"},{"cut"},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""},{""}};
	
	srand(time(NULL));
    k=rand()%5;
	
	printf("%s\n\n", polski[k]);
    	printf("Podaj pierwsza forme czasownika '%s'\n", polski[k]);
		gets(haslo);
		if (stricmp(haslo, jeden[k]) == 0){
			printf("Bardzo dobrze!\n\n");
			suma+=1;	
		} 
		else printf("Niestety, pomylka\n\n");
		printf("Podaj druga forme czasownika '%s'\n", polski[k]);
		gets(haslo);
		if (stricmp(haslo, dwa[k]) == 0){
			printf("Bardzo dobrze!\n\n");
			suma+=1;	
		} 
		else printf("Niestety, pomylka\n\n");
		printf("Podaj trzecia forme czasownika '%s'\n", polski[k]);
		gets(haslo);
		if (stricmp(haslo, trzy[k]) == 0){
			printf("Bardzo dobrze!\n\n");
			suma+=1;	
		} 
		else printf("Niestety, pomylka.\n\n");
  
	return suma;
}

main(){
	int i, ocena, wynik=0;
	
	printf("Czasowniki nieregularne by Bartosz Lewczuk\n");
	printf("Ten program ma za zadanie sprawdzic znajomosc czasownikow nieregularnych i wystawic stosowna ocene.");
	printf("Bedziesz musial podac trzy formy wybranych angielskich czasownikow nieregularnych i zatwierdzic przyciskiem enter.");
	printf("Kazda poprawna odpowiedz bedzie warta jeden punkt. By uzyskac ocene pozytywna trzeba poda przynajmniej polowe.\n\n");
	printf("Jezeli jestes gotowy mozesz zaczac.\n\n");
	
	for(i=1;i<=8;i++){
		printf("%i wybrany czasownik to: ", i);
		wynik+=czasownik();
	}
 if (wynik>=8) ocena=(wynik-6)/3;
        else ocena=1;
    printf("Zdobyles %d na 24 punktow.\nTwoja ocena to %d", wynik, ocena);
}
```


```c
#include<stdio.h>
#include<string.h>
#include<stdlib.h>
#define MAX 24
#define MAX_FORM 10


int main(){
	FILE *plik;
	const char * const nazwaPliku="czasowniki.txt";
	int f, l, k, ocena, suma=0;
	char polski[MAX], jeden[MAX], dwa[MAX], trzy[MAX], haslo[MAX];
	
	printf("Czasowniki nieregularne by Bartosz Lewczuk\n");
	printf("Ten program ma za zadanie sprawdzic znajomosc czasownikow nieregularnych i wystawic stosowna ocene.");
	printf("Bedziesz musial podac trzy formy wybranych angielskich czasownikow nieregularnych i zatwierdzic przyciskiem enter.");
	printf("Kazda poprawna odpowiedz bedzie warta jeden punkt. By uzyskac ocene pozytywna trzeba poda przynajmniej polowe.\n\n");
	printf("Jezeli jestes gotowy mozesz zaczac.\n\n");

	
	if((plik=fopen(nazwaPliku,"r"))==NULL){
        fprintf(stderr,"Nie moge otworzyc pliku %s\n", nazwaPliku);
        exit(2);
    }
	
	fopen(nazwaPliku, "r");
	

	for (f=1;f<=8;f++){
			fscanf(plik, "%s %s %s %s", polski, jeden, dwa, trzy);
    		printf("Podaj pierwsza forme czasownika '%s'\n", polski);
			gets(haslo);
			if (stricmp(haslo, jeden) == 0){
				printf("Bardzo dobrze!\n\n");
				suma+=1;	
			} 
			else printf("Niestety, pomylka\n\n");
			printf("Podaj druga forme czasownika '%s'\n", polski);
			gets(haslo);
			if (stricmp(haslo, dwa) == 0){
				printf("Bardzo dobrze!\n\n");
				suma+=1;	
			} 
			else printf("Niestety, pomylka\n\n");
			printf("Podaj trzecia forme czasownika '%s'\n", polski);
			gets(haslo);
			if (stricmp(haslo, trzy) == 0){
				printf("Bardzo dobrze!\n\n");
				suma+=1;	
			} 
			else printf("Niestety, pomylka.\n\n");
    	
	}
    
    if(fclose(plik)!=0){
        fprintf(stderr, "Nie moge zamknac pliku %s\n", nazwaPliku);
        exit(3);
    }
        
        if (suma>=8) ocena=(suma-6)/3;
        else ocena=1;
    	printf("Zdobyłes %d na 24 punktow.\nTwoja ocena to %d", suma, ocena);
}
    


	
//	for (f=1;f<=3;f++){
//		printf("podaj %d forme czasownika\n", f);
//		gets(haslo);
//		if (stricmp(haslo, porow) == 0){
//			printf("bardzo dobrze!\n\n");
//			suma+=1;	
//		} 
//		else printf("niestety, pomylka\n\n");
//	}
//	return suma;
'''
