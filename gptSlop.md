Im Folgenden finden Sie eine detaillierte Beantwortung der Wissensfragen aus der Vorlesung Softwaretechnologie I, basierend auf den von Ihnen bereitgestellten Learning Outcomes.

### **Objektorientierung, Objekte, Klassen, Vererbung, Testen**

*   **Was ein Domänenmodell ist**
    Ein Domänenmodell ist ein konzeptionelles Modell einer bestimmten Problemdomäne, das die verschiedenen Entitäten, ihre Attribute und ihre Beziehungen zueinander darstellt. Es dient dazu, das Verständnis für einen bestimmten Bereich zu strukturieren und zu formalisieren, und bildet oft die Grundlage für die Softwareentwicklung.

*   **Der OO Softwareentwicklungsprozess**
    Der objektorientierte (OO) Softwareentwicklungsprozess ist ein iterativer und inkrementeller Ansatz, der sich auf die Erstellung von Objekten konzentriert, die sowohl Daten als auch Verhalten kapseln. Typische Phasen sind:
    1.  **Analyse:** Identifikation der Anforderungen und Erstellung eines Domänenmodells.
    2.  **Design:** Definition der Softwarearchitektur, der Klassen und ihrer Beziehungen.
    3.  **Implementierung:** Übersetzung des Designs in lauffähigen Code.
    4.  **Testen:** Überprüfung der Software auf Fehler und Korrektheit.
    5.  **Wartung:** Anpassung und Erweiterung der Software nach der Auslieferung.

*   **Grundkonzepte der Objektorientierung**
    Die Grundkonzepte der Objektorientierung sind:
    *   **Abstraktion:** Konzentration auf die wesentlichen Eigenschaften eines Objekts und Ausblenden unnötiger Details.
    *   **Kapselung:** Bündelung von Daten (Attributen) und den zugehörigen Operationen (Methoden) in einer Einheit, der Klasse. Der direkte Zugriff auf die Daten wird in der Regel beschränkt (Geheimnisprinzip).
    *   **Vererbung:** Möglichkeit für eine Klasse (Subklasse), Eigenschaften und Verhalten von einer anderen Klasse (Superklasse) zu erben.
    *   **Polymorphie:** Fähigkeit von Objekten unterschiedlicher Klassen, auf die gleiche Nachricht (Methodenaufruf) unterschiedlich zu reagieren.

*   **Darstellung eines Objektes im Speicher**
    Ein Objekt wird im Speicher als ein zusammenhängender Block repräsentiert, der Platz für seine Attribute (Variablen) bietet. Zudem enthält es einen Verweis auf die Klassendefinition, wo die zugehörigen Methoden gespeichert sind.

*   **Eigenschaften von Klassen, Operationen/Methoden und Attributen**
    *   **Klassen:** Baupläne für Objekte. Sie definieren Attribute und Methoden.
    *   **Attribute:** Datenelemente einer Klasse, die den Zustand eines Objekts beschreiben.
    *   **Operationen/Methoden:** Funktionen, die das Verhalten eines Objekts definieren und auf dessen Daten operieren.

*   **Arten von Methoden**
    *   **Konstruktoren:** Spezielle Methoden zur Erzeugung und Initialisierung von Objekten.
    *   **Access-Methoden (Getter/Setter):** Methoden zum Lesen und Schreiben von Attributwerten.
    *   **Instanzmethoden:** Operieren auf einer spezifischen Instanz (Objekt) einer Klasse.
    *   **Klassenmethoden (statische Methoden):** Sind an die Klasse gebunden und nicht an eine Instanz.

*   **Darstellung einer Klasse im Speicher**
    Eine Klasse wird im Speicher als eine Art Schablone abgelegt. Sie enthält Informationen über die Struktur der Objekte (Attribute) und die Implementierung der Methoden. Alle Objekte derselben Klasse teilen sich dieselbe Methodentabelle.

*   **Was ein Objekt-Lebenszyklus ist**
    Der Objekt-Lebenszyklus beschreibt die verschiedenen Zustände, die ein Objekt von seiner Erzeugung (Instanziierung) über seine Nutzung bis zu seiner Zerstörung (durch den Garbage Collector) durchläuft.

*   **Unterschied des Überladens versus des Überschreibens von Methoden**
    *   **Überladen (Overloading):** Mehrere Methoden in derselben Klasse haben den gleichen Namen, aber unterschiedliche Parameterlisten (Anzahl, Typ oder Reihenfolge der Parameter).
    *   **Überschreiben (Overriding):** Eine Subklasse stellt eine eigene Implementierung für eine Methode bereit, die sie von ihrer Superklasse geerbt hat. Die Methodensignatur (Name und Parameter) muss dabei identisch sein.

*   **Unterschied zwischen Generalisierung und Spezialisierung**
    *   **Generalisierung:** Der Prozess, gemeinsame Merkmale von Klassen zu identifizieren und in einer allgemeineren Superklasse zusammenzufassen.
    *   **Spezialisierung:** Der Prozess, von einer allgemeinen Klasse aus spezifischere Subklassen abzuleiten, die zusätzliche oder veränderte Eigenschaften und Verhaltensweisen haben. Generalisierung und Spezialisierung sind zwei Seiten derselben Medaille.

*   **Unterschied zwischen einfacher und mehrfacher Vererbung**
    *   **Einfache Vererbung:** Eine Klasse kann nur von einer einzigen anderen Klasse direkt erben.
    *   **Mehrfache Vererbung:** Eine Klasse kann von mehreren anderen Klassen direkt erben und deren Eigenschaften und Methoden kombinieren. Dies kann zu Problemen wie dem "Diamond-Problem" führen.

*   **Unterschied zwischen polymorphen und monomorphen Methoden**
    *   **Polymorphe Methoden:** Methoden, die in Subklassen überschrieben werden können. Welcher konkrete Code bei einem Aufruf ausgeführt wird, entscheidet sich zur Laufzeit anhand des dynamischen Typs des Objekts.
    *   **Monomorphe Methoden:** Methoden, deren Implementierung zur Compile-Zeit feststeht (z.B. statische oder finale Methoden).

*   **Unterschiede zwischen abstrakten Klassen, Interfaces und konkreten Klassen**
    *   **Konkrete Klasse:** Eine "normale" Klasse, von der Objekte instanziiert werden können. Alle ihre Methoden sind implementiert.
    *   **Abstrakte Klasse:** Kann nicht instanziiert werden. Sie dient als Basis für Subklassen und kann sowohl implementierte als auch abstrakte (nicht implementierte) Methoden enthalten.
    *   **Interface:** Definiert nur eine Schnittstelle (Menge von Methodensignaturen), ohne Implementierungen. Eine Klasse kann mehrere Interfaces implementieren.

*   **Das Liskow'sche Ersetzungsprinzip (LSP)**
    Dieses Prinzip besagt, dass Objekte einer Subklasse in allen Kontexten anstelle von Objekten ihrer Superklasse verwendet werden können müssen, ohne dass die Korrektheit des Programms beeinträchtigt wird.

*   **Generische Klassen**
    Generische Klassen (Generics) sind Klassen, die mit einem oder mehreren Typparametern arbeiten. Dies ermöglicht es, typsichere Datenstrukturen zu erstellen, die mit verschiedenen Datentypen verwendet werden können, ohne den Code duplizieren zu müssen.

*   **Vorteile von Objektorientierung**
    *   **Wiederverwendbarkeit:** Durch Vererbung und Klassenbibliotheken.
    *   **Wartbarkeit:** Gekapselte Klassen sind leichter zu verstehen und zu ändern.
    *   **Flexibilität:** Polymorphie ermöglicht erweiterbare und flexible Systeme.
    *   **Natürliche Modellierung:** Die Welt lässt sich oft gut in Form von Objekten und ihren Interaktionen abbilden.

*   **Was Refactoring ist**
    Refactoring ist die systematische Überarbeitung von existierendem Code, um dessen interne Struktur und Lesbarkeit zu verbessern, ohne sein beobachtbares Verhalten nach außen zu ändern.

*   **Was Testen ist**
    Testen ist ein Prozess zur Überprüfung der Qualität von Software. Dabei wird die Software ausgeführt, um Fehler (Bugs) zu finden und sicherzustellen, dass sie die spezifizierten Anforderungen erfüllt.

*   **Unterschied zwischen Verifikation und Validation**
    *   **Verifikation:** "Bauen wir das Produkt richtig?" - Überprüfung, ob die Software die Spezifikationen korrekt umsetzt.
    *   **Validation:** "Bauen wir das richtige Produkt?" - Überprüfung, ob die Software die Bedürfnisse der Nutzer und Stakeholder erfüllt.

*   **Was man unter „Design by Contract” versteht**
    Design by Contract ist eine Methode zur Softwareentwicklung, bei der das Zusammenspiel von Softwarekomponenten durch "Verträge" (Spezifikationen) geregelt wird. Diese Verträge definieren Vorbedingungen, Nachbedingungen und Invarianten für Methoden.

*   **Wie Ausnahmebehandlung in Java funktioniert**
    In Java werden Fehler und Ausnahmesituationen zur Laufzeit durch `Exceptions` (Ausnahmen) signalisiert. Mit `try-catch`-Blöcken können diese Ausnahmen abgefangen und behandelt werden. Der `finally`-Block enthält Code, der immer ausgeführt wird, egal ob eine Ausnahme aufgetreten ist oder nicht.

### **Java**

*   **Ungeordnete und geordnete Java Collections**
    *   **Geordnet (Ordered):** Die Elemente haben eine definierte Reihenfolge, die beim Iterieren beibehalten wird (z. B. `List`).
    *   **Ungeordnet (Unordered):** Die Reihenfolge der Elemente ist nicht garantiert (z. B. `Set`).

*   **Unsortierte und sortierte Java Collections**
    *   **Sortiert (Sorted):** Die Elemente werden in einer bestimmten, sortierten Reihenfolge gehalten, z.B. alphabetisch oder numerisch (z.B. `TreeSet`, `TreeMap`).
    *   **Unsortiert (Unsorted):** Die Elemente werden nicht automatisch sortiert (z.B. `ArrayList`, `HashSet`).

*   **Referenzgleichheit und Wertegleichheit**
    *   **Referenzgleichheit (`==`):** Überprüft, ob zwei Referenzvariablen auf dasselbe Objekt im Speicher zeigen.
    *   **Wertegleichheit (`.equals()`):** Überprüft, ob zwei Objekte inhaltlich bzw. dem Wert nach gleich sind. Die genaue Definition der Gleichheit wird in der `equals()`-Methode der Klasse festgelegt.

*   **Kataloge mit Map**
    Eine `Map` in Java ist eine Datenstruktur, die Schlüssel-Wert-Paare speichert. Sie eignet sich hervorragend zur Darstellung von Katalogen, Wörterbüchern oder Verzeichnissen, da sie einen schnellen Zugriff auf einen Wert über seinen eindeutigen Schlüssel ermöglicht.

*   **Implementierung von Mehrfachvererbung in Java**
    Java unterstützt keine Mehrfachvererbung von Klassen. Dieses Konzept kann jedoch durch die Verwendung von **Interfaces** simuliert werden. Eine Klasse kann beliebig viele Interfaces implementieren und so deren Verhalten "erben". Seit Java 8 können Interfaces auch `default`-Methoden mit einer Standardimplementierung enthalten, was die Simulation von Mehrfachvererbung weiter annähert.

### **Entwurfsmuster**

*   **Was Entwurfsmuster sind und ihre Bedeutung**
    Entwurfsmuster sind bewährte, wiederverwendbare Lösungsschablonen für häufig auftretende Probleme im Softwareentwurf. Sie sind wichtig, weil sie eine gemeinsame Sprache für Entwickler schaffen, die Komplexität reduzieren und die Erstellung von robuster, wartbarer und flexibler Software beschleunigen.

*   **Unterschied zwischen Variabilitäts-, Extensibilitäts- und Architektur-Entwurfsmustern**
    *   **Architekturmuster:** Beschreiben grundlegende Organisationsstrukturen für Softwaresysteme (z.B. Schichtenarchitektur, Model-View-Controller).
    *   **Entwurfsmuster (Design Patterns):** Lösen spezifischere Probleme innerhalb einer Architektur (z.B. Singleton, Factory, Observer).
    *   **Idiome:** Sind programmiersprachenspezifische, grundlegende Muster (z.B. die Verwendung von `try-with-resources` in Java).

*   **Entwurfsmuster dieser drei Kategorien von Entwurfsmustern**
    Die klassischen "Gang of Four"-Entwurfsmuster werden in drei Kategorien eingeteilt:
    1.  **Erzeugungsmuster (Creational Patterns):** Befassen sich mit der Erzeugung von Objekten (z.B. Factory Method, Abstract Factory, Singleton).
    2.  **Strukturmuster (Structural Patterns):** Befassen sich mit der Zusammensetzung von Klassen und Objekten zu größeren Strukturen (z.B. Adapter, Composite, Decorator).
    3.  **Verhaltensmuster (Behavioral Patterns):** Befassen sich mit der Kommunikation und Interaktion zwischen Objekten (z.B. Observer, Strategy, Command).

### **Modellierung, UML**

*   **Wozu man die UML-Modellierung benutzt**
    UML (Unified Modeling Language) wird verwendet, um Softwaresysteme zu visualisieren, zu spezifizieren, zu konstruieren und zu dokumentieren. Sie bietet eine standardisierte grafische Notation, um verschiedene Aspekte eines Systems darzustellen.

*   **Unterschied zwischen objektorientierter Analyse und objektorientiertem Entwurf**
    *   **Analyse (OOA):** Fokus auf das "Was". Identifiziert Objekte und Klassen im Problembereich und deren Beziehungen, um das System zu verstehen und zu modellieren.
    *   **Entwurf (OOD):** Fokus auf das "Wie". Transformiert das Analysemodell in ein Lösungsmodell, das implementiert werden kann. Dabei werden konkrete Klassen, Schnittstellen und die Softwarearchitektur definiert.

*   **Welche Modellfragmente in ein Analyse- und welche in ein Entwurfsmodell gehören**
    *   **Analysemodell:** Enthält typischerweise Anwendungsfalldiagramme, konzeptionelle Klassendiagramme und Aktivitätsdiagramme, die die Problemdomäne beschreiben.
    *   **Entwurfsmodell:** Enthält detaillierte Klassendiagramme (mit Methoden und Attribut-Typen), Sequenzdiagramme, Komponentendiagramme und Zustandsdiagramme, die die Lösungsarchitektur beschreiben.

*   **Beziehung zwischen einem OO Modell und einer Sicht eines Systems**
    Ein OO-Modell ist eine vollständige Beschreibung eines Systems. Eine **Sicht** ist eine Abstraktion davon, die nur bestimmte Aspekte des Modells hervorhebt und für eine bestimmte Zielgruppe (z.B. Entwickler, Kunde) relevant ist. UML-Diagramme sind Werkzeuge zur Darstellung dieser Sichten.

*   **Welche UML-Modelle sich für die Modellierung eines Objekt-Lebenszyklus eignen**
    Am besten eignen sich **Zustandsdiagramme (State Machine Diagrams)**, da sie die Zustände eines Objekts und die Übergänge zwischen diesen Zuständen explizit modellieren.

*   **Wie man Objektnetze in UML modelliert**
    Objektnetze, also konkrete Instanzen von Klassen und ihre Beziehungen zu einem bestimmten Zeitpunkt, werden in UML mit **Objektdiagrammen** modelliert.

*   **Schritte von der Problemanalyse bis zur Implementierung**
    Ein typischer Ablauf ist:
    1.  **Anforderungsanalyse:** Was soll das System leisten?
    2.  **Objektorientierte Analyse:** Modellierung der Problemdomäne.
    3.  **Architekturentwurf:** Definition der groben Struktur des Systems.
    4.  **Objektorientierter Entwurf:** Detaillierte Ausarbeitung der Klassen und Interaktionen.
    5.  **Implementierung:** Umsetzung des Entwurfs in Code.
    6.  **Testen:** Überprüfung des Codes.

*   **UML-Diagramme für die statische und dynamische Modellierung**
    *   **Statische Modellierung (Struktur):** Klassendiagramm, Objektdiagramm, Komponentendiagramm, Verteilungsdiagramm.
    *   **Dynamische Modellierung (Verhalten):** Anwendungsfalldiagramm, Sequenzdiagramm, Kommunikationsdiagramm, Zustandsdiagramm, Aktivitätsdiagramm.

*   **Unterschied zwischen Protokollzustandsmodell und Verhaltenszustandsmodell**
    *   **Verhaltenszustandsmodell:** Beschreibt den vollständigen Lebenszyklus eines Objekts inklusive aller Zustände, Übergänge und Aktionen.
    *   **Protokollzustandsmodell:** Eine speziellere Form, die nur die erlaubte Reihenfolge von Operationen auf einem Objekt festlegt, ohne interne Aktionen zu beschreiben.

*   **Wozu Zustandsmodelle in der UML-Modellierung eingesetzt werden**
    Zustandsmodelle (Zustandsdiagramme) werden eingesetzt, um das reaktive Verhalten eines einzelnen Objekts zu modellieren, insbesondere bei Systemen mit komplexen Lebenszyklen und vielen Zuständen.

*   **Unterschied zwischen Anwendungsfall (Use Case) und Szenario**
    *   **Anwendungsfall:** Beschreibt eine Interaktion zwischen einem Akteur und dem System, um ein bestimmtes Ziel zu erreichen. Er umfasst alle möglichen Abläufe.
    *   **Szenario:** Beschreibt einen einzigen, konkreten Durchlaufpfad durch einen Anwendungsfall (z.B. den Erfolgsfall oder einen bestimmten Fehlerfall).

*   **Was eine Kollaboration in UML ist**
    Eine Kollaboration beschreibt eine Gruppe von zusammenwirkenden Objekten (Rollen), die gemeinsam eine bestimmte Aufgabe erfüllen. Sie wird oft verwendet, um die Realisierung eines Anwendungsfalls zu modellieren.

*   **Unterschied zwischen einem strukturellen und einem dynamischen Verfahren in der objektorientierten Analyse**
    *   **Strukturelle Verfahren:** Konzentrieren sich auf die statische Struktur des Systems (z.B. welche Klassen gibt es und wie sind sie verbunden?).
    *   **Dynamische Verfahren:** Konzentrieren sich auf das zeitliche Verhalten des Systems (z.B. wie interagieren Objekte, um eine Aufgabe zu erledigen?).

*   **Was ein Metamodell im Unterschied zu einem Modell ist**
    *   **Modell:** Eine Abstraktion oder Beschreibung eines Systems (z.B. ein UML-Klassendiagramm beschreibt ein Softwaresystem).
    *   **Metamodell:** Beschreibt die Sprache oder die Regeln, mit denen Modelle erstellt werden. Das UML-Metamodell definiert zum Beispiel, was eine "Klasse" oder eine "Assoziation" ist und wie diese Elemente in einem UML-Modell verwendet werden dürfen.

*   **Verfeinerungsschritte beim Übergang vom Analyse- zum Entwurfs- und Implementierungsmodell**
    Dieser Übergang ist ein Prozess der schrittweisen Konkretisierung:
    *   **Analyse -> Grobentwurf:** Konzeptionelle Klassen werden zu Entwurfsklassen, die Architektur wird festgelegt, technische Randbedingungen fließen ein.
    *   **Grobentwurf -> Feinentwurf:** Klassen werden mit konkreten Datentypen, Algorithmen und Methodensignaturen angereichert.
    *   **Feinentwurf -> Implementierungsmodell:** Der Entwurf wird in eine spezifische Programmiersprache und Technologieplattform übersetzt.

### **Softwarearchitektur und Architekturprinzipien**

*   **Was komplexe Objekte sind**
    Komplexe Objekte sind Objekte, die aus mehreren anderen, einfacheren Objekten zusammengesetzt sind. Ihre Struktur und ihr Verhalten ergeben sich aus dem Zusammenspiel ihrer Teile. Das Composite-Entwurfsmuster ist ein Weg, um solche Strukturen zu handhaben.

*   **Was ein Kontextmodell ist**
    Ein Kontextmodell (oder Kontextdiagramm) stellt ein System und seine Interaktionen mit der Außenwelt (externe Systeme, Benutzer, Sensoren) dar. Es definiert die Systemgrenzen und die Schnittstellen zur Umgebung.

*   **Was eine Top-Level-Architektur ist**
    Die Top-Level-Architektur ist die grobe, übergeordnete Struktur eines Softwaresystems. Sie zerlegt das System in seine Hauptkomponenten oder Subsysteme und definiert deren Verantwortlichkeiten und Beziehungen.

*   **Was Kohäsion und Kopplung von Subsystemen bzw. Komponenten ist**
    *   **Kohäsion:** Das Maß, in dem die Elemente innerhalb einer Komponente funktional zusammengehören. **Ziel: hohe Kohäsion**.
    *   **Kopplung:** Das Maß der Abhängigkeit zwischen verschiedenen Komponenten. **Ziel: geringe Kopplung**.

*   **Das Geheimnisprinzip von Komponenten**
    Dieses Prinzip (auch Information Hiding genannt) besagt, dass eine Komponente ihre internen Implementierungsdetails vor anderen Komponenten verbergen sollte. Der Zugriff sollte nur über eine klar definierte, stabile Schnittstelle erfolgen.

*   **Das Schichtenprinzip**
    Das Schichtenprinzip (Layering) strukturiert ein System in hierarchische Schichten, wobei jede Schicht nur auf Dienste der direkt darunter liegenden Schicht zugreifen darf. Typische Beispiele sind die Trennung in Präsentations-, Logik- und Datenschicht.

*   **Die BCED Schichten eines Softwaresystems**
    Dies bezieht sich wahrscheinlich auf eine spezifische Schichtenarchitektur. Ohne weiteren Kontext könnte eine gängige Interpretation sein:
    *   **B**oundary (Grenze): Schnittstellen zur Außenwelt (z.B. GUIs, APIs).
    *   **C**ontrol (Steuerung): Steuert die Abläufe und koordiniert die Interaktionen.
    *   **E**ntity (Entität): Repräsentiert die Kerndaten und die Geschäftslogik der Domäne.
    *   **D**atabase (Datenbank): Verantwortlich für die persistente Speicherung der Daten.

*   **Was eine Plattform als Komponente der Infrastruktur ist**
    Eine Plattform ist eine Softwareumgebung, die die Grundlage für die Ausführung von Anwendungen bildet. Sie stellt grundlegende Dienste und Ressourcen bereit (z.B. Betriebssystem, Datenbank, Application Server) und ist somit ein zentraler Teil der technischen Infrastruktur.

### **Projektmanagement**

*   **Wie man den Aufwand eines Softwareprojektes schätzen kann**
    Aufwandsschätzung kann durch verschiedene Methoden erfolgen:
    *   **Expertenschätzung:** Befragung erfahrener Entwickler.
    *   **Analogieverfahren:** Vergleich mit ähnlichen, bereits abgeschlossenen Projekten.
    *   **Algorithmische Modelle:** Verwendung von Formeln, die auf Metriken wie Codezeilen oder Funktion-Points basieren (z.B. COCOMO).
    *   **Bottom-up-Schätzung:** Zerlegung des Projekts in kleine Arbeitspakete, deren Aufwand geschätzt und dann summiert wird.

*   **Was ein Gantt-Diagramm ist**
    Ein Gantt-Diagramm ist ein Balkendiagramm, das den Zeitplan eines Projekts visualisiert. Es zeigt die einzelnen Aufgaben, ihre Dauer, Start- und Endzeitpunkte sowie ihre Abhängigkeiten voneinander auf einer Zeitachse.

*   **Was ein Meilenstein ist**
    Ein Meilenstein ist ein wichtiger Kontrollpunkt in einem Projektplan, der den Abschluss einer bedeutenden Phase oder eines wichtigen Ergebnisses markiert. Meilensteine haben keine Dauer, sondern sind Ereignisse zu einem bestimmten Zeitpunkt.

*   **Welche Aufgaben das Konfigurationsmanagement hat**
    Das Konfigurationsmanagement hat die Aufgabe, alle Artefakte eines Projekts (Code, Dokumente, Modelle etc.) über den gesamten Lebenszyklus hinweg zu identifizieren, zu versionieren, zu verwalten und ihre Konsistenz zu sichern.

*   **Was ein Phasenmodell ist und welche Beispiele für Phasenmodelle es gibt**
    Ein Phasenmodell ist ein Vorgehensmodell in der Softwareentwicklung, das den Entwicklungsprozess in aufeinanderfolgende Phasen unterteilt.
    *   **Beispiele:**
        *   **Wasserfallmodell:** Ein sequenzielles Modell, bei dem eine Phase vollständig abgeschlossen sein muss, bevor die nächste beginnt.
        *   **V-Modell:** Eine Erweiterung des Wasserfallmodells, das den Entwicklungsphasen entsprechende Testphasen gegenüberstellt.
        *   **Inkrementelle und iterative Modelle (z.B. Spiralmodell, Scrum):** Das Produkt wird in kleinen, wiederholten Zyklen entwickelt und schrittweise erweitert.