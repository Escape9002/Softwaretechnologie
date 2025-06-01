Gegenstück: [[Monorphie]]

![[11-st-inheritance-polymorphism.pdf#page=36]]

Essentiell: Du hast ein Buch. Das kann vorliegen als PDf oder als Hardcover. 

Häufig wird ein Buch zuerst als PDF verschickt und dann zum Buch gemacht --> Lebenszyklus. 

> Polymorphie macht die Darstellung von Lebenszyklen einfacher. 
> Kind -> Schüler -> Studi 
> PDF -> Buch -> Wurfobjekt

Dafür gibt es Polymorphie-Diagramme

![[11-st-inheritance-polymorphism.pdf#page=40]]



# Vor und Nachteile
Schönere Software und einfache Veränderung einzelner Lebensabschnitte des Objektes.

Wenn eine Funktion aufgerufen wird, von wo laden wir diese Funktion? ```dynamic Dispatch``` muss ausgeführt werden, heißt wir müssen die richtige Funktion "teuer" suchen.
Vergleich zu Monomorphie: Hier wird die Funktion nur das eine mal definiert -> Suche nicht nötig.

![[11-st-inheritance-polymorphism.pdf#page=42]]


Weiter Vor- Nachteile:
![[11-st-inheritance-polymorphism.pdf#page=47]]

