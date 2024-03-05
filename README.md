# M323

## Wichtige Fachbegriffe

### Call by reference

Call by reference bedeutet, dass der Funktion / Methode die Parameter beim Aufruf als Referenz auf die Daten übergeben werden. Wenn der Inhalt der Parameter verändert wird, ändern sie sich nicht nur innerhalb des Kontexts der Funktion, sondern dauerhaft (auch ausserhalb der Funktion). Dies kann zu schwer zu lokalisierenden Seiteneffekten führen. In der funktionalen Programmierung wird "call by value" bevorzugt.

### Call by value

Call by value bedeutet, dass der Funktion / Methode die Parameter beim Aufruf als Kopie der Originaldaten übergeben werden. Wenn innerhalb der Funktion / Methode die Daten der Parameter angepasst werden, hat dies keine Auswirkungen / Seiteneffekte auf Daten ausserhalb der Funktion / Methode. Deshalb sollten in der funktionalen Programmierung die Funktionen / Methoden immer mit "call by value" aufgerufen werden.

### Eager evaluation

Eager evaluation ist das Gegenteil von lazy evaluation. Ausdrücke werden während ihrer Definition auch sofort ausgewertet (und nicht erst dann, wenn sie tatsächlich gebraucht werden).

### Impure functions

Ist das Gegenteil von pure functions - d. h. wenn eine Funktion eine oder mehrere der drei Regeln für pure functions nicht erfüllt.

### Lazy evaluation

Bei lazy evaluation werden Ausdrücke im Code erst dann ausgewertet, wenn sie wirklich gebraucht werden. Dies kann helfen, die Performance zu steigern, da nicht immer alle Teile eines Programms durchlaufen werden müssen und somit Rechenarbeit gespart werden kann. Das Gegenteil von lazy evaluation ist eager evaluation.

### Pure functions

Pure functions sind Funktionen, die drei Regeln erfüllen:

    Nur ein Rückgabewert
    Rückgabewert nur abhängig von den Aufrufparametern
    Verändert keine existierenden Werte

### Referenzielle Transparenz

Man spricht dann von referenzieller Transparenz einer Funktion, wenn anstelle des Funktionsaufrufs auch nur der Return-Wert im Code angegeben werden könnte und sich das Programm dennoch exakt gleich verhält. Ein Beispiel:

### scala

val mySum = (x: Int, y: Int) => x + y
println("Sum of 4+5: " + mySum(4, 5))  // Ausgabe: Sum of 4+5: 9
println("Sum of 4+5: " + 9)  // Ausgabe: Sum of 4+5: 9

Eine Funktion, die nicht referenziell transparent ist, wäre beispielsweise today(), die das Datum von heute zurückgibt. Wenn nun morgen ist, dann würde die Funktion beim gleichen Aufruf einen anderen Rückgabewert haben. Der Rückgabewert hängt nicht alleine von den Input-Parametern ab.

## Rekursion

Von Rekursion oder rekursiver Funktion wird gesprochen, wenn eine Funktion sich selbst aufruft. Damit das nicht in Endlosschleifen endet, braucht jede rekursive Funktion ein Abbruchkriterium - also einen Fall, in dem die Funktion sich selbst nicht mehr weiter aufruft.
