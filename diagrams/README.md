 Diagramy
==========

Algorytmy mozna zapisywac na wiele sposobow. Zwykle zapisuje sie (implementuje) w jakims jezyku programowania,
niektorzy uzywaja tzw. pseudo-kodu. Innym sposobem jest wyrazenie algorytmu w postaci diagramu.

Proponujemy nastepujaca notacje diagramow, ktora sklada sie z takich elementow:
<table>
 <tr> <th> <img src='starter.png' alt='START'/>  START </th> <td> poczatek programu, moze byc tylko jeden w calym diagramie. </td> </tr>
 <tr> <th> <img src='starter.png' alt='STOP'/> STOP </th> <td> koniec programu, moze wystepowac wiele razy. </td> </tr>
 <tr> <th> <img src='activity.png' alt='Instrukcja'/> </th> <td> podstawowa instrukcja przypisania wartosci. Wewnatrz prostokatu pisze sie przypisanie, np. a <- 3 podstawia wartosc "3" pod nazwe "a", 
a z kolei `b <- a+1` do wartosci "a" dodaje 1 i podstawia wynik pod nazwe "b", itp. </td> </tr>
 <tr> <th> <img src='condition_small.png' alt='Warunek'/> </th> <td> podaje sie jeden warunek np. `x > 3`, dodatkowo z tego elementu wychodza dwie strzalki "TAK" oraz "NIE" - reprezentujace co ma sie dziac jesli warunek jest spelniony, a co jesli nie. </td> </tr>
 <tr> <th> strzalki laczace elementy diagramu </th> <td> z jednego elementu moze wychodzic tylko jedna strzalka (z wyjatkiem warunkow - tam dwie), do jednego elementu moze wchodzic potencjalnie wiele strzalek. </td> </tr>
</table>

 Cel
=====

Uzywajac elementow diagramu opisanych powyzej, stworz program (diagram), ktory rozwiazuje zadanie opisane ponizej.

Sposob wyrazenia diagramu jest dowolny. Mozna uzyc jakiegos programu komputerowego do rysowania, ale rownie dobrze mozna 
narysowac na kartce i zrobic zdjecie rysunku.

 Zadanie
=========

Jest dana tablica TAB oraz jej długość DL. Tablica zawiera cyfry od 1 do 9. Cyfry mogą występować dowolnie w tablicy, na przykład tablica może mieć postać [8,8,2,5,3,1,4,6,7,5]. 
Oprócz tego dane sa dwie dodatkowe cyfry C1 i C2 (też od 1 do 9) np C1=8 C2=2.
Napisac program, który dla zadanej tablicy TAB, jej długości DL, oraz dwóch cyfr C1 i C2 sprawdzi, czy w tablicy TAB występuje cyfra C1 i bezpośrednio po niej C2.

Przykład 1:
``` 
TAB=[8,8,2], DL=3, C1=8, C2=2 
```
wynik będzie TAK, gdyż w tablicy występuje cyfra 8 i bezpośrednio po niej cyfra 2.

Przykład 2: 
```
TAB=[2,2,3], DL=3, C1=2, C2=2 
```
wynik będzie TAK, gdyż w tablicy występuje cyfra 2 i bezpośrednio po niej cyfra 2.

Przykład 3:
```
TAB=[4,2,3,7], DL=4, C1=4, C2=3 
```
wynik będzie NIE, gdyż za cyfrą 4 nie występuje bezpośrednio cyfra 3.

Przykład 4:
```
TAB=[7,4,3,5,4,2,6,8,8,1], DL=10, C1=4, C2=2 
```
wynik będzie TAK, gdyż w tablicy występuje cyfra 4, po której bezpośrednio występuje cyfra 2.


 Przyklad 
==========

Ponizszy diagram jest przykladowym rozwiazaniem innego zadania.

Zadanie:

```
Dana jest tablica liczb o nazwie TABELA o dlugosci N. Stworzyc program, ktory wylicza srednia arytmetyczna z liczb z tej tablicy.
```



