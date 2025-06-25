[RefactoringGuru - Strategy](https://refactoring.guru/design-patterns/strategy)

Angenommen der Input für ein Problem bleibt immer der gleiche, aber die Lösungs-Wege können/müssen sich unterscheiden. 

Um nicht eine Riesen-Datei mit allen Lösungs-wegen zu haben, können wir ein Interface mit der Problem-"Eingabe" definieren und darauf dann Lösungen implementieren

zB Licht an und ausschalten. 
```java
interface Lämp {
public bool status(bool on_off);
} 

public class LED implements Lämp{
 public bool status(bool on_off){
 digitalWrite(LED_PIN, on_off);
 return true;
 }
}

public class Glühlampe implements Lämp{
	public bool status(bool on_off){
		if(on_off){
			this.setStatus(1);
		}else{
			this.setStatus(0);
		}
	return true;
	}
	
	private void setStatus(bool status){
	// ... hab ich eine Ahnung wie Glühbirnen funktionieren? NOPPEEE
	}
}

```

Und in der Main:
```java
LED led = new LED();
Glühlampe glüh = new Glühlampe();

bool on_off = 0;

led.status(on_off);
glüh.status(on_off);
```