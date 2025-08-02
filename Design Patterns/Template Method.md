[refactoring guru - template](https://refactoring.guru/design-patterns/template-method)

Some algorithms can work with slight alterations on a huge set of problems.
To be able to reuse it often, cut it into steps. You can then change the steps without impacting the algorithms logic!

Routefinding:
1. load Map
2. compute shortest route
3. return route

The Map and the returned Route might have different data-structures, making an [[Adapter]] necessary. You can write that adapter in a subclass and keep the logic alive.

Your Template should have a final-part which steps through the algorithm and does what you want. This part must be final, so always the same return thingy can be expected.

```java
abstract class Navi(){

	 // 1. Die Template-Methode. 
	 // Sie ist final, damit Subklassen sie nicht ändern können!
    public final Points[] findRoute() {
        // SCHRITT 1: Lade die Karte (spezifisch für die Subklasse)
        HashMap<Points> mapData = loadMap();

        // SCHRITT 2: Berechne die Route (gemeinsame Logik für alle)
        HashMap<Points> rawRoute = computeCoreRoute(mapData);

        // SCHRITT 3: Formatiere die Route für die Ausgabe (spezifisch für die Subklasse)
        Points[] formattedRoute = formatRoute(rawRoute);
        
        return formattedRoute;
    }

	// the dynamic parts to be overwritten
	protected abstract HashMap<Points> loadMap();
	protected abstract Points[] getRoute();

	// some shared logic, could be overwritten, but not necessary
	protected HashMap<Points> computeShortestRoute(){
		HashMap<Points> data = loadMap();

		/*
		 * Some funny dark magic here
		 * Easy peasey routing algorithm
		 */
		 
		 return route;
	}
}

class PlaneNavi extends Navi{
	HashMap<Points> loadMap(){
		// ask the tower for the map-stuff
		return data;
	}

	Points[] getRoute() {
		// return route as Vectors with Heading and altitude.
	}
}

class CarNavi extends Navi {
	HashMap<Points> loadMap(){
		// load the local GFX data map
		return data;
	}

	Points[] getRoute() {
		// return route as GFX Route
	}
}

public static void main() {
	Navi car_navi = new CarNavi();
	Navi plane_navi = new PlaneNavi();

	// the same call, different procedures behind them!
	car_navi.findRoute();
	plane_navi.findRoute();

}
```

The difference to the [[Strategy]] pattern is that we only use a different strategy for subproblems and we dont provide these solutions.
Each Navi has to handle its loading and returning. If it where a strategy, that would dynamicly be taken care of for us.