# Neo4j-Themen-Input

# Inhaltsverzeichnis

1. [Entstehungsgeschichte](#entstehungsgeschichte)
2. [Systemvoraussetzungen](#systemvoraussetzungen)
3. [Grundprinzip der Datenstruktur](#grundprinzip-der-datenstruktur)
   - 3.1 [Nodes](#nodes)
   - 3.2 [Labels](#labels)
   - 3.3 [Properties](#properties)
   - 3.4 [Relationships](#relationships)
4. [Schema u. Abfragesprache](#schema-u-abfragesprache)
   - 4.1 [Cypher Befehle](#cypher-befehle)
5. [Übersicht der Tools](#übersicht-der-tools)
   - 5.1 [Konsole / Kommandozeilenbefehle](#konsole--kommandozeilenbefehle)
   - 5.2 [GUI / Frontend Tools](#gui--frontend-tools)
   - 5.3 [Import, Export Möglichkeiten](#import-export-möglichkeiten)
6. [Modellierung](#modellierung)
7. [Berechtigungskonzept](#berechtigungskonzept)
8. [Backup u. Recovery Möglichkeiten](#backup-u-recovery-möglichkeiten)

## Entstehungsgeschichte

- Neo4j, 2007 von Emil Eifrem entwickelt
- Ursprünglich für Content-Management-Projekt
- Entwicklung zur führenden graphbasierten Datenbank

## Systemvoraussetzungen

- Plattformunabhängig
- Unterstützung für Windows, macOS, Linux
- Flexibilität für vielfältige Einsatzumgebungen

## Grundprinzip der Datenstruktur
### Nodes
In Neo4j werden Daten in Form von Nodes gespeichert. Ein Node repräsentiert eine Entität und kann verschiedene Eigenschaften (Properties) haben. Nodes sind die Bausteine der Datenbank und bilden den Ausgangspunkt für das Speichern von Informationen.
 
Beispiel eines Nodes:
 
```
[Person:John]
- Name: John Doe
- Alter: 30
```
 
### Labels
Labels werden verwendet, um Nodes zu kategorisieren und ihnen eine bestimmte Identität zu geben. Sie ermöglichen die Gruppierung von Nodes mit ähnlichen Eigenschaften. Ein Node kann mehrere Labels haben.
 
Beispiel eines Nodes mit Label:
```
[:Person]
- Name: Jane Smith
- Alter: 25
```
 
### Properties
Properties sind Schlüssel-Wert-Paare, die Informationen über einen Node speichern. Jeder Node kann mehrere Eigenschaften haben, die seine Merkmale oder Attribute darstellen.
 
Beispiel eines Nodes mit mehreren Properties:
```
[Company:Acme]
- Name: Acme Corporation
- Gegründet: 1990
- Umsatz: 1 Milliarde USD
```
 
### Relationships
Relationships repräsentieren Verbindungen zwischen Nodes. Sie ermöglichen es, Beziehungen und Abhängigkeiten zwischen verschiedenen Entitäten darzustellen. Relationships haben ebenfalls Properties, die zusätzliche Informationen über die Verbindung enthalten können.
 
Beispiel eines Relationships zwischen zwei Nodes:
```
[Person:John] --(ARBEITET_BEI)--> [Company:Acme]
- Seit: 2010
- Position: Senior Developer
```


## Schema u. Abfragesprache
Neo4j, als führende Graphdatenbank, basiert auf dem Konzept von Knoten und Beziehungen, wodurch komplexe Datenmodelle effizient abgebildet werden.
### Cypher Befehle
Cypher, die Abfragesprache von Neo4j, ermöglicht die intuitive Manipulation von Graphdaten. Hier sind einige grundlegende Befehle:
```cypher
// Knoten erstellen
CREATE (node:Label {property: value})
// Beziehung erstellen
MATCH (a:Node), (b:Node) WHERE a.property = value
CREATE (a)-[rel:RELATION]->(b)
// Abfrage
MATCH (start:Node)-[:RELATION]->(end:Node)
WHERE start.property = value
RETURN start, rel, end
```
## Übersicht der Tools
### Konsole / Kommandozeilenbefehle (Shell)
Die Neo4j-Konsole bietet direkten Zugriff auf die Datenbank. Durch die Eingabe von Cypher-Befehlen können Nutzer auf effiziente Weise mit der Datenbank interagieren und Abfragen direkt ausführen.
### GUI / Frontend Tools
Neo4j präsentiert benutzerfreundliche grafische Benutzeroberflächen, darunter der Neo4j Browser. Diese Tools ermöglichen eine visuelle Darstellung des Datenmodells, das Erstellen und Ausführen von Abfragen sowie die Analyse von Ergebnissen durch anschauliche Graphen.
## Import, Export Möglichkeiten
Neo4j erleichtert den Datenaustausch durch vielseitige Import- und Exportmöglichkeiten. Der Import von Daten aus CSV-Dateien ist gängig, während Exporte in Formaten wie CSV, JSON oder XML die nahtlose Integration mit anderen Systemen ermöglichen.

## Modellierung

Die Modellierung in Neo4j spielt eine entscheidende Rolle bei der Gestaltung effektiver Graphdatenbankstrukturen. Ein besonders nützliches Tool in diesem Kontext ist *arrows.app*. Diese Webanwendung ermöglicht es Benutzern, Graphen visuell zu modellieren und Beziehungen zwischen Nodes einfach zu erstellen. arrows.app erleichtert somit den Prozess der Planung und Umsetzung komplexer Datenmodelle in Neo4j.

## Berechtigungskonzept

Neo4j bietet ein flexibles Berechtigungskonzept, das es Administratoren ermöglicht, den Zugriff auf Datenbankressourcen zu steuern. Dies umfasst die Kontrolle über Lese- und Schreibzugriffe auf Nodes, Relationships und Properties. Durch die Definition von Rollen und Berechtigungen können Datenbankadministratoren sicherstellen, dass Benutzer nur auf die für sie relevanten Teile der Datenbank zugreifen dürfen.

## Backup u. Recovery Möglichkeiten

Die Sicherung und Wiederherstellung von Daten sind entscheidende Aspekte jeder Datenbankverwaltung. Neo4j bietet robuste Backup-Möglichkeiten, die es ermöglichen, regelmäßige Sicherungspunkte der Datenbank zu erstellen. Im Falle eines Datenverlusts oder einer Fehlfunktion ermöglichen die Recovery-Optionen die Wiederherstellung der Datenbank von einem zuvor erstellten Backup. Dies trägt dazu bei, die Integrität der Daten zu gewährleisten und Ausfallzeiten zu minimieren.
