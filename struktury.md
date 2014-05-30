**1) podstawa**

```c
#include<stdio.h>
#include<string.h>
#include<stdlib.h>
#define MAX_STUDENTOW 15

enum oceny {ndst=2, dst, db, bdb};

struct student {
	char imie[12];
	char nazwisko[16];
	enum oceny ocena;
};

int main(){
	int k, iloscStudentow=0;
	struct student Kowalski={"Jan", "Kowalski", db};
	struct student Studenci[MAX_STUDENTOW];
	FILE *plik;
	const char * const nazwaPliku="studenci.txt";
	
	Studenci[0]=Kowalski;
	iloscStudentow++;
	
	strncpy(Studenci[1].imie, "Adam", 12);
	Studenci[1].imie[11]='\0';
	strncpy(Studenci[1].nazwisko, "Wisniewski", 16);
	Studenci[1].nazwisko[15]='\0';
	Studenci[1].ocena=dst;
	iloscStudentow++;
	
	//Studenci[1].ocena=444;
	
	if((plik=fopen(nazwaPliku,"w"))==NULL){
		fprintf(stderr,"Nie moge otworzyc pliku %s\n", nazwaPliku);
		exit(2);
	}
	for(k=0; k<iloscStudentow; k++) fprintf(plik, "%s %s %d\n", Studenci[k].imie, Studenci[k].nazwisko, Studenci[k].ocena);
	
	if(fclose(plik)!=0){
		fprintf(stderr, "Nie moge zamknac pliku %s\n", nazwaPliku);
		exit(3);
	}
	return 0;
}
```

**2) wyswietlanie**
```c
int wyswietl(struct student Studenci[], int iloscStudentow){
	int k;
	for(k=0; k<iloscStudentow; k++)	printf("%s %s %d\n", Studenci[k].imie, Studenci[k].nazwisko, Studenci[k].ocena);
}

wyswietl(Studenci, iloscStudentow);
```


**3) funkcja zapis**
```c
int zapisz(struct student Studenci[], int iloscStudentow){
	FILE *plik;
	const char * const nazwaPliku="studenci.txt";
	int k;
	if((plik=fopen(nazwaPliku,"w"))==NULL){
		fprintf(stderr,"Nie moge otworzyc pliku %s\n", nazwaPliku);
		exit(2);
	}
	for(k=0; k<iloscStudentow; k++)	fprintf(plik, "%s %s %d\n", Studenci[k].imie, Studenci[k].nazwisko, Studenci[k].ocena);
	
		if(fclose(plik)!=0){
		fprintf(stderr, "Nie moge zamknac pliku %s\n", nazwaPliku);
		exit(3);
	}
}

zapisz(Studenci,iloscStudentow);
```

**4) funkcja dodaj**
```c
int dodaj(struct student Studenci[], int iloscStudentow){
	char odp, string[16];
	int o;
	printf("Czy chcesz dodac kolejnego studenta? (wcisnij t jezeli tak)");
	odp=getchar();
	getchar();
	for (;odp=='t';){
		printf("\npodaj imie: ");
		scanf("%s", &string);
		strncpy(Studenci[iloscStudentow].imie, string, 12);
		Studenci[iloscStudentow].imie[11]='\0';
		printf("\npodaj nazwisko: ");
		scanf("%s", &string);
		strncpy(Studenci[iloscStudentow].nazwisko, string, 16);
		Studenci[iloscStudentow].nazwisko[15]='\0';
		printf("\npodaj ocene: ");
		scanf("%d", &o);
		switch (o){
			case 2: Studenci[iloscStudentow].ocena=ndst;
			break;
			case 3: Studenci[iloscStudentow].ocena=dst;
			break;
			case 4: Studenci[iloscStudentow].ocena=db;
			break;
			case 5: Studenci[iloscStudentow].ocena=bdb;
			break;
		}
		iloscStudentow++;
		printf("Czy chcesz dodac kolejnego studenta? (wcisnij t jezeli tak)");
		getchar();
		odp=getchar();
			
	}
	return iloscStudentow;
}

	iloscStudentow=dodaj(Studenci, iloscStudentow);
```
