 Wprowadzenie
===============

Pewien system rejestracji czasu pracownikow potrafi wyprodukowac dane w postaci XMLa. Jest to zapis informacji, czym kazdy z pracownikow
w danym tygodniu pracy sie zajmowal. 
Kazdy pracownik raportuje czas za dany tydzien - wylicza, w ktorych projektach ile godzin pracowal.

Przykladowy fragment:
```
	<Items>
		<WeekId>201330</WeekId>
		<ResourceId>XY0005</ResourceId>
		<ResourceName>Jan Kowalski</ResourceName>
		<ProjectId>136</ProjectId>
		<ProjectName>Projekt 1</ProjectName>
		<Number>33.00</Number>
	</Items>
	<Items>
		<WeekId>201330</WeekId>
		<ResourceId>XY0005</ResourceId>
		<ResourceName>Jan Kowalski</ResourceName>
		<ProjectId>504</ProjectId>
		<ProjectName>Projekt 2</ProjectName>
		<Number>7.00</Number>
	</Items>
```

oznacza, ze mamy dwa wpisy z rejestru czasu pracy. Oba dotycza tego samego pracownika - o identyfikatorze XY0005, ktory nazywa sie "Jan Kowalski". 
Oba rowniez odnosza sie do tego samego tygodnia pracy (201330). Okazuje sie, ze Jan Kowalski pracowal 33 godzin w projekcie "Projekt 1" oraz 
pozostale 7 godzin w projekcie "Projekt 2".

Opis pol:
- WeekId - identyfikator tygodnia w formacie rrrrtt, czasami z dopiskiem jednej litery na koncu
- ResourceId - jednoznaczny identyfikator pracownika
- ResourceName - jego imie i nazwisko
- ProjectId - jednoznaczny identyfikator projektu
- ProjectName - jego nazwa
- Number - liczba godzin

 Cel zadania
==============

Napisac narzedzie w XSLT, ktore takie raporty z danymi bedzie przetwarzac agregujac (sumujac) pewne informacje i produkowac raporty (podsumowania).
Raporty powinny byc plikami XHTML (lub HTML), ktore wyswietlone w przegladarce beda czytelnym dla ludzi zestawieniem danych.

Interesujace raporty:
- Dla kazdego pracownika osobno; ze wszystkich tygodni razem; z projektow ktorych id nie zaczyna sie ani na 1 ani na 2; zestawienie projektow uszeregowane malejaco ze wzglednu na liczbe godzin, np.
```
Jan Kowalski
 projekt        | godziny
----------------+----------
  407 Projekt 1 |       33
  436 Projekt 4 |       16
  504 Projekt x |        4

Stanislaw August
 projekt        | godziny
----------------+----------
  436 Projekt 4 |       10.5
  407 Projekt 1 |        6
```



