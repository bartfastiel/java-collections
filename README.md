# java-collections
Vortragsnotizen und Ressourcen zum Thema "Java Collections"

# Frage zum Kennenlernen

* Heute geht es um "Collections" (deutsch Sammlungen)
* Hat jemand von Euch eine ungewöhnliche Sammelleidenschaft? 
  * Link teilen

# Einleitungsgeschichte

* Es war einmal, vor langer, langer Zeit
  * Ein Königspaar, das eine Tochter bekommt
    * Haut so weiß wie Schnee
    * Lippen so rot wie Blut
    * Haare so schwarz wie Ebenholz
  * Der König lädt zur Tauffeier ein
  * Er baut sich ein Programm zur Partyorganisation
```java
public class Tauffeier {
    public static void main(String[] args) {
        var feen = new String[12];
        feen[0] = "Antonella";
        feen[1] = "Berta";
        feen[2] = "Cecilia";
        feen[3] = "Dora";
        feen[4] = "Eugenia";
        feen[5] = "Frieda";
        feen[6] = "Greta";
        feen[7] = "Hanna";
        feen[8] = "Ida";
        feen[9] = "Johanna";
        feen[10] = "Klara";
        feen[11] = "Lina";
        feen[12] = "Mona";
    }
}
```

  * Ups ;)
  * Die 13. Fee schimpft fürchterlich und fragt:
    * Warum muss man bei Java-Arrays eigentlich immer eine fixe Größe angeben?
    * Wäre da nicht ein wenig mehr Flexibilität angebracht?

# Gibt's da vielleicht ein neues Sprachkonstrukt?

  * Wir kennen bereits primitive Datentypen, Arrays, Objekte
    * Gibt es da vielleicht Arrays mit dynamischer Länge?
    * Nein, die Liste an Datentypen im Sprachumfang ist abgeschlossen
  * ABER: Durch geschicktes Kombinieren dieser Datentypen kann man tolle Dinge bauen! (z.B. Listen mit flexibler Länge)
  * Einige hilfreiche Klassen werden bereits "mitgeliefert"
  * Eines davon ist: `ArrayList`
  * LEGO: Wie funktioniert die ArrayList?
    * Einzelstein [o] = int, Ganzzahl
    * flache Leiste = Array [oooooooooo]
    * Wir fangen mit einer Leiste mit 10 an
      * Wir fügen einen Wert hinzu
      * Wir merken uns die Länge
    * Wenn die Leiste zu kurz wird
      * Wir nehmen eine neue, längere Leiste (in der Regel doppelt)
      * Kopieren den Inhalt der alten Leiste in die neue

```java
public class Tauffeier {
    public static void main(String[] args) {
        var feen = new ArrayList();
        feen.add("Antonella");
        feen.add("Berta");
        feen.add("Cecilia");
        feen.add("Dora");
        feen.add("Eugenia");
        feen.add("Frieda");
        feen.add("Greta");
        feen.add("Hanna");
        feen.add("Ida");
        feen.add("Johanna");
        feen.add("Klara");
        feen.add("Lina");
        feen.add("Mona");
    }
}
```

    * Die Klasse ArrayList bietet viele praktische Methoden
      * `add` fügt ein Element hinzu
      * `get` liefert ein Element an einer bestimmten Stelle
      * `set` setzt ein Element an einer bestimmten Stelle
      * `remove` entfernt ein Element an einer bestimmten Stelle
      * `size` liefert die Anzahl der Elemente
      * `clear` entfernt alle Elemente

    * Unpraktisch:
      * `get` liefert uns `Object`
      * deshalb: `List<String> <= wir geben dem Java-Compiler beim Erstellen des Objekts einen Tipp:
        * Bitte beschwere Dich, falls wir etwas anderes in der Liste speichern wollen
        * Im Gegenzug gib uns bei `get` immer String statt Object zurück
        * Einverstanden? "Ok, Deal".

    * Übung: Bitte baut Eure Anwendung aus den vergangenen Tagen auf eine ArrayList um
