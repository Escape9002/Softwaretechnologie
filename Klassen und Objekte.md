Code sollte eine Aufgabe haben und diese garantiert abschließen. Es macht Sinn, diese Aufgabe in Sub-Aufgaben zu spalten, um Teilprobleme zu lösen. Die Lösung für diese Teilprobleme ist häufig auch für andere Probleme anwendbar (Post und Steuer brauchen zB eine Adresse).

Teil-Lösungen implementieren mithilfe von Objekten / Klassen.

```java
public class Server{
	int[] IP_ADRESS;
	String NAME;
	int[] MAC_ADRESS;

	// Constructor
	public Server(IP_ADDRESS, NAME, MAC_ADDRESS){
	...
	};

	public boolean wake(){
	...
	};
	
	public boolean sleep(){
	...
	};
}
```

# Vererbung
Die organisierte Wiederverwendung dieser Teillösungen ist das, was uns hier am meisten interessiert. 
Im Java-Syntax gibt es 2 bekannte Wege, Wiederverwendung zu realisieren:

### ```implements ```
Ihr habt ein Objekt und wollt garantieren, dass wann auch immer ihr dieses Objekt verwendet, bestimmte Variablen und Funktionen definiert sind. Hier stehen nur die Namen, nicht die Definitionen der Teillösungen! Die Lösung dieser Teilprobleme wird dem Verwender des Objekts überlassen.
Also...die Casting-Form eines Legosteins, aber Farbe und Material musst du entscheiden.
### ```extends```
Ihr habt schon eine vollständige Teillösung geschrieben, also Variablen und Funktionen die ihr braucht definiert und geschrieben. Menschen die dieses Objekt verwenden, haben einen fertigen Legostein bekommen!

Wenn ihr die Klasse ```Server``` verwenden wollt, welches Keyword müsst ihr benutzen?
- [ ] ```public lel implements Server```
- [ ] ```public lel extends Server```

##### Lösung
Momentan wäre `extends` die richtige Wahl, da wir die Teilprobleme in der Klasse lösen.  
In Java sind "abstrakte Lösungen" wie folgt gekennzeichnet:

```java
interface Server {
  int[] IP_ADRESS;
  String NAME;
  int[] MAC_ADRESS;

  boolean wake();
  boolean sleep();
}
```

Witzig: Ihr könnt auch `implements` verwenden und dann die definierten Funktionen mittels `@Override` einfach neu definieren.

Siehe auch [[14-st-programmieren-mit-loechern.pdf#page=13]]

## UML
![[UML]]


## Interfaces
![[14-st-programmieren-mit-loechern.pdf#page=13]]

