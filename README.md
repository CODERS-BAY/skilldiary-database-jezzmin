# Skill Diary Database 

## Chapter One 10.02.2021

Database => to safe data somewhere

#### Why database? 
  - you see the datas from users
  - security against loss
  - structured datas
 


#### 9 CODD-SCHEN requirements
  - integration
  - operation
  - catalog
  - user's view
  - integrity backup
  - access control
  - transaction
  - sync
  - backup
  
#### Entity relationship model
  - entity = object -> square
  - attribut = eigenschaft -> circle
  - relationship -> #
  
#### Forms 

  n = many
  m = also many
  
  - 1 : 1
  - 1 : n
  - n : 1
  - m : n
  
 example -> mother (1) ----- has ----- (n) child
             child (child name: varchar; _child svn_: int)
             
 #### Keys
 
 key has to be underlined
 
 unique identification
 
 #### Datatype
 
 here are some datatypes:
 
 https://dev.mysql.com/doc/refman/8.0/en/data-types.html
 
 ## Chapter Two 17.02.2021
 
#### Database Management System - DBMS

 - hierachic DBMS
 - network type DBMS
 - relational DBMS
 - invertet lists DBMS
 - object relationed DBMS
 - object oriented DBMS

if you want to know more it's in pool 1 and 2 the third powerpoint.

## Redundanz 
ist die mehrmalige Speicherung ein und derselben Information

## Anomilie
Update
Insert
Delete

# Normalform

## 1. NF
Eine in 1. Normalform befindliche Relation enthält keine Attribute, die sich aus mehreren Elementen zusammensetzen.
Problem -> könnten logisch unrichtige Tupel eingefügt werden

## 2. NF
ist gekennzeichnet, daß jedes nicht dem Schlüssel angehörende Attribut funktional abhängig ist vom Gesamtschlüssel (=1.NF) nicht aber von den einzelnen Schlüsselteilen
Problem -> Es wird zu einer inkonsistenten Datenbank führen, wenn der letzte Satz <103, Paul, 3, Chemie> aufgenommen wird. Die korrekte Zuordnung wäre <2, Chemie>, nicht aber <3, Chemie>.

## 3. NF
Eine in 3.Normalform befindliche Relation ist dadurch gekennzeichnet, dass jedes nicht dem Schlüssel angehörende Attribut funktional abhängig ist vom Gesamtschlüssel (=1.NF), nicht aber von einzelnen Schlüsselteilen (=2.NF). Weiters sind keine transitiven Abhängigkeiten (funktionale Abhängigkeiten zwischen Nicht-Schlüssel-Attributen) erlaubt

1NF: funktional abhängig vom Gesamtschlüssel
2NF: keine funktionalen Abhängigkeiten von Schlüsselteilen
3NF: keine funktionalen Abhängigkeiten von Nichtschlüsselattributen

## Kardinalitäten

binär -> zwei Entitäten
ternär -> drei begeleitete Entitäten
unär -> eine begleitete Entität

## DBMS

Strukturierung der Datenmengen
Niemand kennt im Unternehmen ‚alle Daten‘
Optimierung der vorhandenen Daten

Daten sind im strategischen Interesse eines Unternehmens
Integration in den Gegenstand 'Systemplanung und Projektentwicklung'

Insert, update und delete von Daten
Verwaltung von Metadaten
Vorkehrungen zu Datensicherheit und Datenschutz
Vorkehrungen zur Datenintegrität
Ermöglichung eines Mehrbenutzerbetriebs (Transaktionen)
Bereitstellung von Kennzahlen über Betrieb des DBMS

## Synonyme oder Homonyme

Synonyme
unterschiedliche Bezeichnungen für eine Entität, die logisch dieselbe Entität kennzeichnet.

Zustellung & Auslieferung = Versand

Homonyme
ein Name wurde vergeben, jedoch sind unterschiedliche logische Entitäten gemeint.

Bestellung  = Lieferantenbestellung & Kundenbestellung

## ERD
Entity Relationship Diagramm

Die Entitäten werden durch Rechtecke dargestellt

Die Beziehungen werden durch Verbindungslinien zwischen den Entitäten dargestellt:
Die Beziehungen werden in beide Richtungen bezeichnet. Typischerweise durch aktive und passive Verben:
Schließlich werden noch die sogenannten Kardinalitäten eingefügt

## Schlüssel

Fremdschlüssel
ist ein Attribut, das in einer anderen Relation ein Primärschlüssel ist (foreign key)

Sekundärschlüssel
erlaubt den Zugriff auf ein oder mehrere Datensätze

Zusammengesetzter Schlüssel
Entitäten werden durch mehr als 1 Attribut identifiziert.

<b> Tupel = Zeile </b>

## Sub- Supertyp

Synonym: Generalisierung / Spezialisierung
Synonym: 'is-a' Beziehung

Bei der Spezialisierung wird ein Entitätstyp als Teilmenge eines anderen, ‚übergeordneten‘ Entitätstyps angenommen. Im Supertyp sind alle Attribute, die den Subtypen gemeinsam sind. Im Subtyp 1 findet man alle Attribute, die nur dort und nicht in den anderen Subtypen oder dem Supertyp vorkommen. Damit generalisiert der Supertyp.

## Entitäts Lebenszyklus

Die Identifikationsschlüssel werden initialisiert
Die Attributwerte, die bei diesem Ereignis nicht berührt werden, sollen initialisiert werden
Es wird die Verbindung (Fremdschlüssel) zur Master Entität (hier KUNDE) hergestellt
Der Attributswert von SALDO soll auf den Wert von ERSTEINLAGE gesetzt werden
Die Verbindung zur Detail Entität (hier TRANSAKTION) wird hergestellt. Bei jeder Ein- oder Auszahlung muß jedesmal eine Entität TRANSAKTION erstellt und mit der Entität KONTO verknüpft werden.
Der Wert des Attributes SALDO wird mit SALDO + EINZAHLUNG ersetzt
Der Wert des Attributes SALDO wird mit SALDO - EINZAHLUNG ersetzt
Die Verbindung zur Master Entität KUNDE wird gelöst.

# SQL

## Select

SELECT * FROM locations ORDER BY city ASC;

SELECT last_name as Nachname FROM employees;

SELECT DISTINCT …

 DISTINCT - nur eines nicht doppelt

## Where

LIKE – für Zeichenketten
% - Beliebige Anzahl unbekannter Zeichen
SELECT … 
WHERE ENAME LIKE ‘M%‘;


_ = genau ein unbekanntes Zeichen 
SELECT … 
WHERE ENAME LIKE ‘ALL_N‘;


SELECT * FROM locations WHERE … 

LIKE, NOT LIKE, =, >=, <=

SELECT job_id, department_id
FROM employees
WHERE department_id = 10

## Joins

Verbindet zwei oder mehr Relationen miteinander.
Abfrage von Daten über zwei oder mehr Tabellen

CROSS JOIN - Jede Zeile von R1 verbunden mit jeder Zeile von R2
INNER JOIN - Verbindet alle Zeilen von R1 und R2 miteinander, wo ein Match gefunden wird.
OUTER JOIN - Verbindet alle Zeilen von R1 und R2 miteinander, wo ein Match gefunden wird. Wo keiner gefunden wird, wird der Rest mit NULL aufgefüllt.
LEFT JOIN - Jede Zeile von R1 verbunden mit dazupassenden Zeilen von R2
RIGHT JOIN - Jede Zeile von R2 verbunden mit dazupassenden Zeilen von R1
NATURAL JOIN - Natürlicher Verbund von R1 und R2 bei gleichnamiger Spalte

SELECT employees.last_name, departments.department_name
FROM employees
JOIN departments
ON employees.department_id = departments.department_id;

Über mehreren Tabellen

SELECT department_name, postal_code, city, country_name
FROM departments
JOIN locations ON departments.location_id = locations.location_id
JOIN countries ON locations.country_id = countries.country_id;

## Order by

…WHERE DEPTNO = 30
    ORDER BY SAL;

ASC - Aufsteigend
DESC - Absteigend

## Arithmetische Ausdrücke

Addition
Subtraktion
Multiplikation
Division

## Gruppenfunktion

Avg  
Count
Min
Max
Sum

## Group by

Ausgabe der Durchschnittsgehälter in den Abteilungen:
SELECT DEPTNO, AVG(SAL)
FROM EMP
GROUP BY DEPTNO;

SELECT DEPTNO
FROM EMP
WHERE JOB = ’CLERK‘
GROUP BY DEPTNO
HAVING COUNT(*) >= 2;

# Subsprache

## DDL - Data Definition Language

CREATE - definieren
ALTER  - ändern
DROP - löschen

## DML . Date Manipulation Language

SELECT - auswählen
UPDATE - aktualisieren
INSERT - einfügen
DELETE - löschen

## DCL - Data Control Language

GRANT  - Berechtigungsvergabe
REVOKE - Berechtigungsentzug
COMMIT - fixieren von Veränderungen
ROLLBACK - Zurücksetzen
LOCK   - sperren 

# Constraints 

## Constraints
Einschränkungen – beispielsweise referentielle Integrität - werden vom DBMS geprüft

Table – Constraint
Column - Constraint
 
## Not Null Constraints

Definiert, dass eine Spalte keine Null – Values enthalten darf.
create table teams (
    teamno        smallint        not null,
    …    );

Änderung einer bestehenden Tabelle:
ALTER TABLE emp
MODIFY (sal NUMBER CONSTRAINT nn_sal NOT
NULL)



## Markdown Cheatsheet
### Headlines

<table>
  <tr>
    <td> 
      Markdown Syntax 
    </td>
    <td>
      How it looks
    </td>
  </tr>
   <tr>
    <td> 
      # TEXT
    </td>
    <td>
      <h1> This is a H1 </h1>
    </td>
  </tr>
  <tr>
    <td> 
      ## TEXT
    </td>
    <td>
      <h2> This is a H2 </h2>
    </td>
  </tr>
  <tr>
    <td> 
      ### TEXT
    </td>
    <td>
      <h3> This is a H3 </h3>
    </td>
  </tr>
  <tr>
    <td> 
      #### TEXT
    </td>
    <td>
      <h4> This is an H4 </h4>
    </td>
  </tr>
  <tr>
    <td> 
      ##### TEXT
    </td>
    <td>
      <h5> This is an H5 </h5>
    </td>
  </tr>
  <tr>
    <td> 
      ###### TEXT
    </td>
    <td>
      <h6> This is an H6 </h6>
    </td>
  </tr>
</table>

### Emphasis
#### Italic
<table>
  <tr>
    <td> 
      Markdown Syntax 
    </td>
    <td>
      How it looks
    </td>
  </tr>
   <tr>
    <td> 
      *This text will be italic*
    </td>
    <td>
      <i> This text will be italic </i>
    </td>
  </tr>
  <tr>
    <td> 
       _This text will be italic too_
    </td>
    <td>
      <i> This text will be italic too</i>
    </td>
  </tr>
</table>

#### Bold
<table>
  <tr>
    <td> 
      Markdown Syntax 
    </td>
    <td>
      How it looks
    </td>
  </tr>
   <tr>
    <td> 
      *This text will be bold*
    </td>
    <td>
      <b> This text will be bold </b>
    </td>
  </tr>
  <tr>
    <td> 
       __This text will be bold too__
    </td>
    <td>
      <b> This text will be bold too</b>
    </td>
  </tr>
</table>

### Lists
#### Unordered
<table>
  <tr>
    <td> 
      Markdown Syntax 
    </td>
    <td>
      How it looks
    </td>
  </tr>
   <tr>
    <td> 
      * Item 1 <br/>
      * Item 2 <br/>
      TAB * Item 2a <br/>
      TAB * Item 2b <br/>
    </td>
    <td>
      <ul>
        <li>Item 1</li>
        <li>Item 2</li>
        <ul>
          <li>Item 2a</li>
          <li>Item 2b</li>
        </ul>
      </ul>
    </td>
  </tr>
</table>

#### Ordered

<table>
  <tr>
    <td> 
      Markdown Syntax 
    </td>
    <td>
      How it looks
    </td>
  </tr>
   <tr>
    <td> 
      1. Item 1 <br/>
      2. Item 2 <br/>
    </td>
    <td>
        <ol>
        <li>Item 1</li>
        <li>Item 2</li>
      </ol>
    </td>
  </tr>
</table>

### Images
<table>
  <tr>
    <td> 
      Markdown Syntax 
    </td>
    <td>
      How it looks
    </td>
  </tr>
   <tr>
    <td> 
      ![GitHub Logo](/images/logo.png)<br/>
      Format: ![Alt Text](url)
    </td>
    <td>
      Displays the image in folder images which is called logo.png
    </td>
  </tr>
</table>

### Links


<table>
  <tr>
    <td> 
      Markdown Syntax 
    </td>
    <td>
      How it looks
    </td>
  </tr>
   <tr>
    <td> 
      ![GitHub](https://www.github.com)<br/>
      Format: ![Alt Text](url)
    </td>
    <td>
      <a href = "https://www.github.com">GitHub</a>
    </td>
  </tr>
</table>

### Backslash Escape
If you need the characters, which are already used as special characters in Markdown you can use them if you put an \\ before the character. For example you have to write ```\*``` to use a \*

### Using code in Markdown
Markdown coverts text with four leading spaces into a code block; with GFM you can wrap your code with \`\`\` to create a code block without the leading spaces. Add an optional language identifier and your code will get syntax highlighting.



![CodeSnippet](/Codesnippet.png)

### Tables
You can create tables by assembling a list of words and dividing them with hyphens \- (for the first row), and then separating each column with a pipe \| 
<table>
  <tr>
    <td> 
      Markdown Syntax 
    </td>
    <td>
      How it looks
    </td>
  </tr>
   <tr>
    <td> 
      First Header | Second Header<br/>
      ------------ | ------------- <br/>
      Content cell 1 | Content cell 2 <br/>
      Content column 1 | Content column 2
    </td>
    <td>
      <table>
        <thead>
            <td> 
               First Header
            </td>
            <td>
              Second Header
            </td>
       </thead>
       <tbody>
         <tr>
          <td> 
            Content cell 1
          </td>
          <td>
            Content cell 2
          </td>
        </tr>
         <tr>
          <td> 
            Content column 1
          </td>
          <td>
            Content column 2
          </td>
        </tr>
       </tbody>  
      </table>
    </td>
  </tr>
</table>
