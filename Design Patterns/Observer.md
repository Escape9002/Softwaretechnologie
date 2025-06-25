[RefactoringGuru - Observer](https://refactoring.guru/design-patterns/observer)

> **Observer** is a behavioral design pattern that lets you define a subscription mechanism to notify multiple objects about any events that happen to the object they’re observing.

Also known as Event-Subscriber, Listener

Das Pattern besteht aus 2 Dingen:
- Publisher
- Subscriber

Der Publisher ruft bei eintreten eines Weltuntergangs zB die ```notify(), die(), update()``` Funktion (such dir eine aus oder mach ne neue) auf und informiert somit alle Subscriber, dass etwas passiert ist. 
Dafür müssen alle Subscriber das gleiche Interface implementieren, damit sichergestellt ist, dass diese Funktion existiert. 

zB Weltuntergangs-Observer
```java
interface Subscriber{
public void udpate(String msg);
}

public class Human implements Subscriber{
	public void update(String msg){
		switch(msg){
			case "PIZZA":
				explode();
			
			case "Skynet booted":
				die();
				break;
			
			default:
				makePizza();
		}
	}
}

public class Robot implements Subscriber{
	public void update(String msg){
		switch(msg){
			case "Skynet booted":
				update&&upgrade();
				break;
			
			case "ePA":
				crawl();
				
			default:
				yoinkInfo();
		}
	}
}

public class Observer {
	public Subscriber subscribers[];
	
	public bool update(String msg){
		for Subscriber subscriber:subscribers{
			subscriber.update(msg);
		}
	}
}

main(){
Human PETER = new Human();
Roboter PETER2.0 = new ROBOTER();
Observer obi = new Observer().add(PETER).add(PETER2.0);

obi.update("didnt expect that to get this long... im sorry");
}
```