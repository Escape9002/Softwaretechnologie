[refactoring guru - composite](https://refactoring.guru/design-patterns/composite)

Das Composite-Pattern ermöglicht es, einzelne Objekte und Gruppen von Objekten einheitlich zu behandeln. Es wird verwendet, um Objekte in einer Baumstruktur zu organisieren, die eine Teil-Ganzes-Hierarchie darstellt.

Alle Objekte – sowohl die einzelnen "Blätter" (Leaves) als auch die "Container" (Composites) – implementieren eine gemeinsame Schnittstelle (Interface). Ein Client, der diese Schnittstelle verwendet, muss nicht wissen, ob er mit einem einzelnen Objekt oder einer ganzen Gruppe von Objekten arbeitet.

**Beispiel: Ein Dateisystem**  
Eine Datei (Blatt) und ein Ordner (Container) können beide über eine gemeinsame Schnittstelle Dateisystem-Element angesprochen werden, die eine Methode wie getGröße() anbietet. Fragt man einen Ordner nach seiner Größe, addiert dieser rekursiv die Größe aller enthaltenen Elemente (Dateien und Unterordner).