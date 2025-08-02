[refactoring guru - state](https://refactoring.guru/design-patterns/state)

Your code has **some** states and you need to handle them neatly, without ending up with a [1000 row if-else](https://tuacm.com/blog/switch-statements-wont-fix-yandere-simulator/).

Simply create an interface for the actions you want to be able to do and then implement State-Classes which specify what specificly is going to happen. Which State-Class to call is handled in a Context-Class. The context can be altered by the state-classes.

Requirements:
- A context-class the client can interact with.
	- delegates calls to the correct state-class
	- thus wraps all state-classes via their common interface
	- stores the current state (via a variable assigned to the correct state class)
- A common interface of actions for allstateclasses.
	- Can also be an abstract class
- The state classes
	- Implement the interface or abstract class


## Example:

imagine a BLE-Server with these States:
- connected
- disconnected

and you would like to handle these actions:
- advertise
- send
- receive
- connected <-- Dont forget your state-changing actions!
- disconnected <-- Dont forget your state-changing actions!

The Context will be handled by the `BLEServer`


```java
// The context
class BLEServer {
    // the "wrapper" around all states and storage of which state 
    // we are currently in
    protected IBLEState currentState;

    public BLEServer() {
        // Der Anfangszustand ist "disconnected".
        this.currentState = new BLEDisconnectedState(this);
    }

	// this function is package private and should be used by the state 
	// classes. This way, we can control State change behaviour in one place
	void changeState(IBLEState newState) {
        // Hier könnte man noch Logik einbauen (z.B. Logging)
        this.currentState = newState;
    }

    // Der Kontext delegiert alle Aktionen an den aktuellen Zustand.
    public void advertise() {
        currentState.advertise();
    }

    public void send(String msg) {
        currentState.send(msg);
    }

    public String receive() {
        return currentState.receive();
    }
    
    // Auch die Aktionen, die den Zustand ändern, werden delegiert.
    public void onDeviceConnected() {
        currentState.onDeviceConnected();
    }

    public void onDeviceDisconnected() {
        currentState.onDeviceDisconnected();
    }
}

// Das State-Interface: Definiert, was JEDER Zustand können muss.
interface IBLEState {
    void advertise();
    void send(String msg);
    String receive();
    void onDeviceConnected();
    void onDeviceDisconnected();
}

// Konkreter Zustand 1: Implementiert das Verhalten für "Connected".
class BLEConnectedState implements IBLEState {
    private BLEServer server; // Back-Reference zum Kontext

    public BLEConnectedState(BLEServer server) {
        this.server = server;
    }

    @Override
    public void advertise() { /* Stoppe Advertising, da verbunden */ }

    @Override
    public void send(String msg) { /* Sende die Nachricht */ }

    @Override
    public String receive() { /* Empfange Daten */ return "data"; }

    @Override
    public void onDeviceConnected() { /* Tue nichts, sind bereits verbunden */ }
    
    @Override
    public void onDeviceDisconnected() {
        // Hier passiert der Zustandsübergang!
        System.out.println("Gerät getrennt. Wechsle zum Disconnected-Zustand.");
        this.server.changeState(new BLEDisconnectedState(server));
    }
}

// Konkreter Zustand 2: Implementiert das Verhalten für "Disconnected".
class BLEDisconnectedState implements IBLEState {
    private BLEServer server;

    public BLEDisconnectedState(BLEServer server) {
        this.server = server;
    }

    @Override
    public void advertise() { /* Starte Advertising */ }

    @Override
    public void send(String msg) { throw new Error("Nicht verbunden!"); }

    @Override
    public String receive() { throw new Error("Nicht verbunden!"); }
    
    @Override
    public void onDeviceConnected() {
        // Hier passiert der Zustandsübergang!
        System.out.println("Gerät verbunden. Wechsle zum Connected-Zustand.");
        this.server.changeState(new BLEConnectedState(server))
    }
    
    @Override
    public void onDeviceDisconnected() { /* Tue nichts, sind bereits getrennt */ }
}

// Client-Code
public void main() {
	BLEServer myBleDevice = new BLEServer();

	myBleDevice.send("Hallo"); // Wirft einen Fehler, wie erwartet.
	
	myBleDevice.onDeviceConnected(); // Löst den Zustandswechsel aus.
	
	myBleDevice.send("Hallo"); // Funktioniert jetzt, weil der Zustand gewechselt hat.
}
```