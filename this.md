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
	char jeden [40] [MAX]={{"be"},{"beat"},{"begin"},{"break"},{"buy"},{"catch"},{"come"},{"cut"},{"do"},{"eat"},{"fall"},{"feed"},{"find"},{"fly"},{"forget"},{"get"},{"give"},{"go"},{"have"},{"hear"},{"know"},{"leave"},{"make"},{"meet"},{"read"},{"ride"},{"run"},{"say"},{"see"},{"sit"},{"speak"},{"spend"},{"swim"},{"take"},{"teach"},{"tell"},{"think"},{"wear"},{"win"},{"write"}};
	char dwa [40] [MAX]={{"was/were"},{"beat"},{"began"},{"broke"},{"bought"},{"caught"},{"came"},{"cut"},{"did"},{"ate"},{"fell"},{"fed"},{"found"},{"flew"},{"forgot"},{"got"},{"gave"},{"went"},{"had"},{"heard"},{"knew"},{"left"},{"made"},{"met"},{"read"},{"rode"},{"ran"},{"said"},{"saw"},{"sat"},{"spoke"},{"spent"},{"swam"},{"took"},{"taught"},{"told"},{"thought"},{"wore"},{"won"},{"wrote"}};
	char trzy [40] [MAX]={{"been"},{"beaten"},{"begun"},{"broken"},{"bought"},{"caught"},{"come"},{"cut"},{"done"},{"eaten"},{"fallen"},{"fed"},{"found"},{"flown"},{"forgotten"},{"got"},{"given"},{"gone"},{"had"},{"heard"},{"known"},{"left"},{"made"},{"met"},{"read"},{"ridden"},{"run"},{"said"},{"seen"},{"sat"},{"spoken"},{"spent"},{"swum"},{"taken"},{"taught"},{"told"},{"thought"},{"worn"},{"won"},{"written"}};
	
	srand(time(NULL));
    k=rand()%40;
	
	printf("%s\n\n", polski[k]);
	
	for(f=1;f<=3;f++){
		if(f==1) strcpy(porow, jeden[k]);
		else if (f==2) strcpy(porow, dwa[k]);
			else strcpy(porow, trzy[k]);
		printf("Podaj %d forme czasownika '%s':\n", f, polski[k]);
		gets(haslo);
		if (stricmp(haslo, porow) == 0){
			printf("Bardzo dobrze!\n\n");
			suma+=1;	
		} 
		else printf("Niestety, pomylka\n\n");
		
	}
/*    	printf("Podaj pierwsza forme czasownika '%s':\n", polski[k]);
		gets(haslo);
		if (stricmp(haslo, jeden[k]) == 0){
			printf("Bardzo dobrze!\n\n");
			suma+=1;	
		} 
		else printf("Niestety, pomylka\n\n");
		printf("Podaj druga forme czasownika '%s':\n", polski[k]);
		gets(haslo);
		if (stricmp(haslo, dwa[k]) == 0){
			printf("Bardzo dobrze!\n\n");
			suma+=1;	
		} 
		else printf("Niestety, pomylka\n\n");
		printf("Podaj trzecia forme czasownika '%s':\n", polski[k]);
		gets(haslo);
		if (stricmp(haslo, trzy[k]) == 0){
			printf("Bardzo dobrze!\n\n");
			suma+=1;	
		} 
		else printf("Niestety, pomylka.\n\n");*/
  
	return suma;
}

int ocena(int wynik){
	 if (wynik>=8) return (wynik-6)/3;
        else return 1;
}

main(){
	int i, wynik=0;
	
	printf("Czasowniki nieregularne by Bartosz Lewczuk\n");
	printf("Ten program ma za zadanie sprawdzic znajomosc czasownikow nieregularnych \ni wystawic stosowna ocene.");
	printf("Bedziesz musial podac trzy formy wybranych \nangielskich czasownikow nieregularnych i zatwierdzic przyciskiem enter.\n");
	printf("Kazda poprawna odpowiedz bedzie warta jeden punkt. By uzyskac ocene \npozytywna trzeba poda przynajmniej polowe.\n\n");
	printf("Jezeli jestes gotowy mozesz zaczac.\n\n");
	
	for(i=1;i<=8;i++){
		printf("%i wybrany czasownik to: ", i);
		wynik+=czasownik();
	}
    printf("Zdobyles %d na 24 punktow.\nTwoja ocena to %d", wynik, ocena(wynik));
}

'''
