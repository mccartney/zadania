 Wprowadzenie
===============

Pewien system rejestracji czasu pracownikow potrafi wyprodukowac dane w postaci XMLa. Jest to zapis informacji, czym kazdy z pracownikow
w danym tygodniu pracy sie zajmowal. 
Kazdy pracownik raportuje czas za dany tydzien - wylicza, w ktorych projektach ile godzin pracowal.

Przykladowy fragment:
	<Items>
		<WeekId>201330</WeekId>
		<ResourceId>XY0005</ResourceId>
		<ResourceName>Jan Kowalski</ResourceName>
		<ProjectId>436</ProjectId>
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

oznacza, ze mamy dwa wpisy z rejestru czasu pracy. Oba dotycza tego samego pracownika - o identyfikatorze XY0005, ktory nazywa sie "Jan Kowalski". 
Oba rowniez odnosza sie do tego samego tygodnia pracy (201330). Okazuje sie, ze Jan Kowalski pracowal 33 godzin w projekcie "Projekt 1" oraz 
pozostale 7 godzin w projekcie "Projekt 2".



 
