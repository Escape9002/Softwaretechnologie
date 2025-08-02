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


---

Instead of having one core logic to do things, you might need multiple. Like sending things over: Wifi, BLE and Morse.

You can abstract these "Hardware" implementations using a Base-Class and then decorating that base-class with the actual needed implementations. 

Requirements:
- the Base and Explizit Objects all implement the same [[Interface]]
- The client only interacts with the base
- the base holds a object of the real implementation ([[Composite]] style)

```java
// the common interface for all objects
interface IMU {
	int[] getAccl();
}

// our base image 
class BaseImu implements IMU {
	// to wrap around object
	IMU used_imu;

	BaseImu(){ /** create new IMU */ }
	getAccl(){ return used_imu.getData(); }
}

// explicit implementation
class MPU6050 implements IMU{
	// base interface stuff
	int[] getAccl(){
		// ...
	}

	// some other functionality we may feature
	int[] getGyro() {
		// ...
	}
}

// explicit implementation
class MPU9250 implements IMU{
	// base interface stuff
	int[] getAccl(){
		// ...
	}

	// some other functionality we may feature
	int[] getQuats() {
		// ...
	}
}

public void main(){
	// we decorate our BaseIMU with a specific implementation
	// here we use the MPU6050 and can NOT access its special sauce
	// since that special sauce is not in the base-interface
	BaseImu imu = MPU6050();

	imu.getAccl();

	// we can @runtime change the IMU to another one
	// we can keep working without missing functions, 
	// since we can only use the interface functions
	imu = MPU9250();

	imu.getAccl();
}
```