Wprowadzenie
===============

W świecie biznesowym systemy informatyczne wymieniają ze sobą informacje za pomocą różnych formatów danych.
Wśród tylko niebinarnych często są to formaty oparte albo na XMLu, albo jakiejś formie plików tekstowych.

Tę samą informację (albo ten sam typ wymienianych informacji) można zakodować na różne sposoby, np.

(A) w XMLu
```
<?xml version='1.0'?>
<osoby>
  <osoba>
     <imie>Jan</imie>
     <nazwisko>Kowalski</nazwisko>
     <wiek>25</wiek>
     <miejsce_urodzenia>Warszawa</miejsce_urodzenia>
  </osoba>
  <osoba>
     <imie>Adam</imie>
     <nazwisko>Małysz</nazwisko>
     <wiek>37</wiek>
     <miejsce_urodzenia>Wisła</miejsce_urodzenia>
  </osoba>
  ...
</osoby>
```

(B1) czy w postaci plików oddzielanych przecinkami z nagłówkiem (CSV)
```
imie,nazwisko,wiek,miejsce urodzenia
Jan,Kowalski,25,Warszawa
Adam,Malysz,37,Wisła
...
```

(B2) ... lub pliki tekstowe oddzielane przecinkami bez nagłówków (CSV)
```
Jan,Kowalski,25,Warszawa
Adam,Malysz,37,Wisła
...
```

(C) czy w postaci plików tekstowych o stałej szerokości kolumn
```
JAN______KOWALSKI______25Warszawa_____________
ADAM_____MALYSZ________37Wisła________________
```
(typowo zamiast podkreślenia wstawia się spacje albo zera)

Cel zadania
============

W wybranym przez siebie znanym języku programowania (np. Python, Java, itp.) napisać program, który 
pliki tekstowe oddzielane przecinkami (B1 albo B2) będzie przetwarzał na plik XMLowy (A).

W przypadku plików z nagłówkami (B1) - wygodne jest, gdy nazwy elementów XMLowych niekoniecznie są takie same jak kolumny w pliku tekstowym.
W przypadku plików bez nagłówków - trzeba się odwoływać do numeru kolejnego kolumny.

Program powinień być ogólny - i w miarę uniwersalny. Tak by ten sam program można było stosować
do plików tekstowych o różnym zbiorze kolumn. 

Proszę zaproponoawać jakąś strukturę generowanego XMLa - np. taką jak w powyższym przykładzie.


