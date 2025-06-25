[RefactoringGuru - Iterator](https://refactoring.guru/design-patterns/iterator)

> **Iterator** is a behavioral design pattern that lets you traverse elements of a collection without exposing its underlying representation (list, stack, tree, etc.).

Speichere deine Schuhe bitte einmal in einer HashMap, einem Array und einer Liste ab. 
Jetzt möchte ich mir alle deine Schuhe anschauen. Wie mache ich das?

Du warst schlau und hast ein Interface erstellt für deine verschiedenen Schuh-Speicher. Das Interface nennt sich ```Iterator``` und sorgt dafür, das ich auf alle 3 Implementierungen ```hasNext(), next``` aufrufen kann. 

Ein Iterator stellt also eine Schnittstelle bereit, durch einen Speicher zu iterieren, ohne die Implementierung dieses Speichers genauer zu kennen. 