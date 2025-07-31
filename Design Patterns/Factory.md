We dont care how something is achieved but its always the same thing done.
We create a factory which builds objects capable of doing Chaos but the implementation for Chaos is within the object itself.

Requirements:
- The to-create objects have to share a [[Interface]]
- 

```java
// The Product declares the interface, which is common to all objects.
interface IMU {
    int[] getData();
}

// Concrete Products are different implementations of the product interface.
class BNO085 implements IMU {
    @Override
    public int[] getData() {
		// ...
    }
}

// The Factory declares the method that returns new product objects.
abstract class ImuFactory {
    // The "Factory Method"
    abstract IMU createIMU();

    // The creator can have other business logic that works with the products.
    public void processImuData() {
        // Call the factory method to create a Product object.
        IMU imu = createIMU();
        // Now, use the product.
        int[] data = imu.getData();
        // ... do something with the data
        System.out.println("Processing data...");
    }
}

// Concrete Creators override the base factory method so it returns a different type of product.
class BNO085Factory extends ImuFactory {
    @Override
    public IMU createIMU() {
        return new BNO085();
    }
}

// 5. Client Code
class Application {
    public static void main(String[] args) {
        // The client code works with an instance of a concrete creator.
        ImuFactory imuFactory;

        // Let's say a configuration decides which IMU to use.
        String config = "BNO"; // or "MPU"

        if (config.equals("BNO")) {
            imuFactory = new BNO085Factory();
        } else {
            imuFactory = new MPU9250Factory();
        }

        // The client uses the factory to do its work, without knowing the concrete product class.
        // The business logic in processImuData is decoupled from the concrete IMU sensor.
        imuFactory.processImuData();
    }
}
```