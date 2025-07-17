[RefactoringGuru - Iterator](https://refactoring.guru/design-patterns/iterator)

> **Iterator** is a behavioral design pattern that lets you traverse elements of a collection without exposing its underlying representation (list, stack, tree, etc.).

Speichere deine Schuhe bitte einmal in einer HashMap, einem Array und einer Liste ab. 
Jetzt möchte ich mir alle deine Schuhe anschauen. Wie mache ich das?

Du warst schlau und hast ein Interface erstellt für deine verschiedenen Schuh-Speicher. Das Interface nennt sich ```Iterator``` und sorgt dafür, das ich auf alle 3 Implementierungen ```hasNext(), next``` aufrufen kann. 

Ein Iterator stellt also eine Schnittstelle bereit, durch einen Speicher zu iterieren, ohne die Implementierung dieses Speichers genauer zu kennen. 

--- 

# Rust specific iterator
Iterators iterate over Items, if they are implemented with [[Monads]], we can do fancy shit!

Iterators in Rust are lazy --> they wont act on the data until they are accessed.

There are 3 different iterators:

[Table from here](https://blog.coolhead.in/difference-between-intoiter-iter-and-itermut-in-rust)

| iterator     | Mutability | Ownership                                                              |
| ------------ | ---------- | ---------------------------------------------------------------------- |
| .iter()      | read-only  | &\<T> .. Borrows the elements immutably                                |
| .into_iter() | read_only  | \<T> .. into_iter() consumes your data, you CAN NOT use it after this. |
| iter_mut()   | read_write | &mut \<T> .. allows modifying the original collection.                 |
into_iter() is the default in for-loops etc.