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
