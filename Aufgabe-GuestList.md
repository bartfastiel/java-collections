# Übungsaufgabe: Gästeliste

Du baust ein Programm, um die Gästeliste für Deine Geburtstagsparty zu pflegen.

## Aufgabe 1

Schreibe eine Klasse `GuestList` mit einem Feld `guests`.

Eine Methode `addGuest` soll einen Gast als Parameter akzeptieren (Typ String) und in die Gästeliste hinzufügen.

Eine Methode `getGuests` soll die Liste der Gäste zurückgeben.

Definiere jeweils zuerst die Tests für 0, 1 und 5 Gäste und schreibe dann die Implementierung dafür.

## Aufgabe 2

Wenn Gäste mehrfach Bescheid geben, dass sie kommen, sollen sie nur einmal auf der Liste geführt werden. Doppelte
Aufrufe von `addGuest` sollen ignoriert werden.

## Aufgabe 3

Jeder Gast bringt eine Sache mit (zum Beispiel Kuchen, Getränke, Deko) um Dich beim Organisieren zu entlasten. Erweitere
die Methode `addGuest` um ein weiteres Argument `contribution` (auch vom Typ String).

Eine neue Methode `getContribution` soll ein String-Argument annehmen und dazu die Anzahl der Gäste zurückgeben, die
sich entsprechend beteiligen. (z.B. Parameter `cake` soll die Anzahl der Gäste zurückgeben, bei denen `cake`
als `contribution` angegeben war)
