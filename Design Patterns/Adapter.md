Docker works with Yaml, creating new VMs from a template works with CloudInit.
To use CloudInit configs for Docker, you need an Adapter.

This adapter offers an [[Interface]] to call for you with Cloud-Init specific stuff and translates those calls to Docker-Calls. For this, the Docker-Calls are a [[Composite]] within the Adapter.

Requirements: 
- public client-side [[Interface]]
- an wrapper around the functions we translate to (can be done with [[Composite]])

```java
// public interface for your client-code
interface CloudInit{
	void startVM(String conf);
}

// Adapter class
class CloudToDockerAdapter implements CloudInit {
	// the wrapper we operate on for translation
	Docker docker_instance = new Docker();

	// the interface the CloudInit exposes
	void startVM(String conf){
		// parse to docker specific stuff and execute
		docker_instance.run(conf);
	}
}
```

Adapters can connect two sides of code which might have a different architecture by translating their actions.
