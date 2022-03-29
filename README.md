# java-collections

Vortragsnotizen und Ressourcen zum Thema "Java Collections"

# Vorstellung

* Seit meiner Kindheit Programmierer, schon in Schulzeit Programmierunterricht gehalten
* Vor knapp 20 Jahren an Akademie Java gelernt (ähnlich wie hier)
* Lead-Developer, Scrum-Master, Team-Coach

Ich möchte
* das Unterrichtskonzept kennenlernen
* mich auf mein erstes Bootcamp im Mai vorbereiten
* gemeinsam Spaß haben

Danke, dass ich hier sein darf.

# Frage zum Kennenlernen

* Heute geht es um "Collections" (deutsch Sammlungen)
* Hat jemand von Euch eine ungewöhnliche Sammelleidenschaft?
    * Briefmarken
    * Diddl-Postkarten
    * Münzen

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
        * Achtung: primitive Datentypen können nicht angegeben werden - da muss man statt  `int` dann `Integer`
          schreiben

## Übung: Bitte baut Eure Anwendung aus den vergangenen Tagen auf eine ArrayList um

## Duplikate vermeiden

## Schlüssel-Wert-Paare

## Übung: Bitte baut Eure Anwendung aus den vergangenen Tagen auf eine HashMap um

## Falls noch Zeit ist

* Collections.sort
* String.join
* Übersicht über die vielen anderen Collections
  * TreeSet, ConcurrentHashMap, usw.
* Übung "GuestList"

## Zusammenfassung: Wie wähle ich die richtige Collection?

* Willst Du einfach nur mehrere Werte in einer Variablen speichern?<br/>`List<...> meineListe = new ArrayList<...>();`
* Willst Du auch vorne und hinten ein Element einfügen und löschen können (z.B. Warteliste)
  ?<br/>`Queue<...> meineWarteschlange = new LinkedList<...>();` (oder `Deque<...>`)
* Willst Du Duplikate vermeiden?<br/>`Set<...> meineSammlung = new HashSet<...>();`
* Willst Du Schlüssel-Wert-Paare verwalten?<br/>`Map<...> meinNachschlagewerk = new Hashmap<...>()`

Und für Spezialfälle suche im Internet nach einer geeigneten Klasse (vorzugsweise aus dem Standard-Java-Umfang)
Z.B. Unveränderliches, automatisch Sortiertes, für gleichzeitige Zugriffe, usw.

Arrays wie int[] oder String[] sind nur für spezielle Anwendungsbereiche.

**Achtung** Bei `Hash...`-Klassen muss definiert werden, was als "Duplikat" gilt. Dazu: `equals` und `hashCode`
überschreiben.

## Abschluss-Übung

Jeder Teilnehmer soll eine dieser Aufgaben per privater Nachricht bekommen. Reihum soll ein Teilnehmer nach dem anderen
seine Aufgabe vorlesen. Dann diskutiert die Gruppe gemeinsam die beste Lösung (= den passenden Collection-Typ).

Jeweils soll entschieden werden, passt "ArrayList", "LinkedList", "HashSet" oder "HashMap" am besten? (Bonus: jeweils noch das passende Interface - also "Queue", "Stack", "Map", "Set" usw.)

Welche Collection ist am besten für die Aufgabe?

"Du möchtest die Züge eines Schachspiels mitschreiben. Eine Klasse 'Schachzug' hast du bereits."

"Für die Webseite des Sportvereins möchtest Du die Sportarten aufzählen. Die Reihenfolge soll genau der Reihenfolge in
der gedruckten Brochure entsprechen."

"Du bringst abgezählte Schokoladenosterhasen mit ins Büro und möchtest notieren, welchem Deiner Kollegen Du bereits
einen Hasen ausgeteilt hast, um niemandem aus Vergesslichkeit zwei zu geben."

"In Deinem neu entwickelten Online-Shop suchst Du eine Speicherform für den Warenkorb. Du möchtest Pro Artikelnummer die
Menge im Warenkorb speichern."

"Du schreibst eine Verwaltungssoftware für Zahnarztpraxen. Es sollen die Patienten entsprechend Ihrer Ankunft in der
Praxis gespeichert werden und nach und nach immer ein Patient in den Behandlungsraum geschickt werden. Wer am längsten
wartet, soll jeweils als nächstes aufgerufen werden."

"In Deiner neuen Software für die Personalabteilung möchtest Du abspeichern, welcher Kollege bereits die
Datenschutzerklärung unterschrieben hat."

"In dem von Dir entwickelten Briefmarkenonlineshop möchtest Du pro Artikelnummer den Preis in Euro abspeichern."

"Eine Schreinerei möchte während des Jahres die Adressen der Kunden sammeln und dann zu Weihnachten Grußkarten
verschicken."

"Du möchtest für eine Grundschulklasse eine Tabelle mit dem Schulfach und der dazugehörigen Lehrkraft speichern."

"Du verteilst bei einem Theaterstück die Rollen. Du weißt die zu besetzenden Rollen und möchtest nach und nach den
Schauspieler dazu festlegen."

"Du entwickelst eine Upload-Funktion für Dateien. Alle vom Anwender ins Fenster gezogenen, hochzuladenden Dateien sollen
mit einer Warteanimation dargestellt werden. Sobald eine Datei fertig hochgeladen ist, soll sie aus der Ansicht
verschwinden. Es soll jeweils die Datei hochgeladen werden, die als Erstes ins Fenster gezogen wurde."

## Further Reading

* https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/doc-files/coll-overview.html
