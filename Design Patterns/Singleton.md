[refactoring guru - singleton](https://refactoring.guru/design-patterns/singleton)

Ensures you only have one instance of something across the entire software. 
> Thou shall not create two hardware instances if you only have one.


> [!warning] 
> This pattern can NOT be implemented with the normal constructor, since this HAS to return a new instance

Thus:
- Make default constructor private (prevents use of `new` )
- create a `static` creation method inplace of the constructor

```java
class BNO085 {
	private static volatile BNO085 instance = null;
	 
	private BNO085 BNO085() {
		return new BNO085();
	}

	static BNO085 getInstance(){
		if ( instance == null) {
			instace = new BNO085;
		}

		return instance;
	} 
}

public static void main(){
	BNO085 sensor_0 = BNO085.getInstance();

	BNO085 sensor_1 = BNO085.getInstance();

	// both variables will point to the same object
	if(sensor_0 == sensor_1) {
		System.out.println("only one instance exists!");
	}
}
```