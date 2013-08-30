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
  </osoba>
  <osoba>
     <imie>Adam</imie>
     <nazwisko>Małysz</nazwisko>
     <wiek>37</wiek>
  </osoba>
  ...
</osoby>
```

(B) czy w postaci plików oddzielanych przecinkami (CSV)
```
imie,nazwisko,wiek
Jan,Kowalski,25
Adam,Malysz,37
...
```

(C) czy w postaci plików tekstowych o stałej szerokości kolumn
```
JAN______KOWALSKI______25
ADAM_____MALYSZ________37
```
(typowo zamiast podkreślenia wstawia się spacje albo zera)

Cel zadania
============

W wybranym przez siebie znanym języku programowania (np. Python, Java, itp.) napisać program, który 
pliki tekstowe oddzielane przecinkami (B) będzie przetwarzał na plik XMLowy (A).

Program powinień być ogólny - i w miarę uniwersalny. Tak by ten sam program można było stosować
do plików tekstowych o różnym zbiorze kolumn. 

Proszę zaproponoawać jakąś strukturę generowanego XMLa - np. taką jak w powyższym przykładzie.


