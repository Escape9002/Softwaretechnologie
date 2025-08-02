[refactoring guru - decorator](https://refactoring.guru/design-patterns/decorator)

You might have a [[Strategy]] Pattern in place to handle multiple IMU's and their base functions.

But you now need the Orientation-Data from these IMU's and want to filter their output. 

Extending the base-class is not an option since Orientation-Computation is not related to the Hardware, a new Subclass for each IMU is not a clean option and you dont always need the new Orientation-Data.

A solution would be playing DressUp. You take a random IMU, interact with its functions and offer a new Interface exposing the IMU and some new functionality.

Requirements:
- There is a common base ([[Interface]]) which can be extended with swappable features.
- You give a base instance to the constructor of the decorator to...decorate it!

```java
// the common interface for all objects
interface IMU {
	int[] getAccl();
}

// our decorator for every IMU
class FilterIMU implements IMU {
	// to wrap around object
	IMU used_imu;

	FilterIMU(IMU to_use_imu){ 
		this.used_imu = to_use_imu; 
	}

	// decorate the function with a little filter magic
	int[] getAccl(){ 
		int[] data = used_imu.getData();
		int[] filtered_data = applyFilter(data);
		return filtered_data;
	}
}

// explicit implementation
class MPU9250 implements IMU{
	// base interface stuff
	int[] getAccl(){
		// ...
	}
}

public void main(){
	// we create a base image
	IMU imu = MPU9250();

	imu.getAccl(); // we get the RAW data
	
	// and then decorate it with some new functionality
	imu = new FilterIMU(imu);
	
	imu.getAccl(); // we now get filtered data!
}
```


 - Der Adapter gibt ein völlig neues Interface, der Decorator erweitert oder lässt das interface gleich.
 - das [[Strategy]]-Pattern ermöglicht es, die Unterliegende Implementation auszutauschen, der Decorator fügt nur eine neue Oberfläche hinzu.

---

Stepping away from a pragmatic decorator:
To actually add more functionality, a little unclean smth is needed:

```java

// we need the new interface, since we now offer more functionality
interface QuaternionIMU extends IMU {
	float [] getQuats();
}

// our decorator for every IMU
class QuaternionIMU implements QuaternionIMU {
	// to wrap around object
	IMU used_imu;

	QuaternionIMU(IMU to_use_imu){ 
		this.used_imu = to_use_imu; 
		
	}
	
	int[] getAccl(){ return used_imu.getData(); }

	float [] getQuats() {
		// returns quaternions
	}
}


public void main(){
	// we create a base image
	IMU imu = MPU9250();

	// we decorate the image, but also need a new object, 
	// to update the registered functions on it 
	// (basicly so we can actually use the new functions.)
	QuaternionIMU imu_q = new QuaternionIMU(imu);
	
	imu.getQuat();
}
```

This usecase might be covered better by a [[Facade]] and [[Strategy]] Pattern tho!