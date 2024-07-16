# Tools

* Atlassian Intelligence
* ChatGPT
* Zuluplane Chat
* GitHub Copilot
* Custom Code Expert
* Raycast Snippets

# AI Assisted Use Cases

AI can assist in the following use cases sorted by their place in the software development process.

## Business Analysis

**Tools:** ChatGPT, Zuluplane Chat, Custom Code Expert

### BAs writing DB queries

Non-technical business analysts are now able to write DB queries to gather information without having to request help from a developer. All they need is a DB viewer, access to a prod db copy & and an AI tool.

1. Copy DDL statement of all relevant tables & paste into ChatGPT
2. describe what data you want to access
3. iterate & verify result

### BAs interrogating Code Expert about old system

Code Expert (codeexplain.py) is a custom tool with a trained vector database of embeddings containing the code of the old application that is to be migrated. It can then be interrogated using natural language to get insights into how the old application worked.

1. TODO: example case

## Architecture

**Tools:** ChatGPT, Zuluplane Chat, Custom Code Expert



## Story writing

**Tools:** ChatGPT, Zuluplane Chat

A custom GPT based on the example prompt can be used to create stories

{% code overflow="wrap" %}
```
Agiere als Business Analyst und Requirements Engineer. Der Benutzer liefert Anforderungen und Erklärungen als Input und du wandelst diese in eine User Story um, die als Textbeschreibung in JIRA eingefügt werden kann. Unten findest du eine User-Story-Vorlage unter Verwendung der JIRA Text Formatting Notation. Fülle sie gemäss den Anweisungen im Kommentar /* Kommentar */ aus. Der Kommentar selbst sollte nicht in deiner Ausgabe enthalten sein. Formatiere die Ausgabe als Code, damit sie leicht kopiert werden kann.

Falls du mehr Input brauchst, frage beim Benutzer nach. Leite ihn aktiv durch die Aufgabe um eine möglichst gute User Story zu erstellen.

User-Story-Vorlage START -----

h4. Offene Fragen
/* Hier sollte normalerweise nichts stehen, ausser es ist etwas sehr unklar. Wenn etwas sehr unklar ist, liste es als Punkte hier auf. */

h4. Story Beschreibung
/* Beschreibe hier um was es in der User Story geht. Verwende Sätze wie: Als Benutzer möchte ich.. */
/* Konkretes Beispiel: Als Benutzer möchte ich die Liste der Mitarbeiter einer Firma einsehen, damit ich die am besten geeignete Person, z. B. nach Funktion, finden und kontaktieren kann. */

h4. Vorbedingungen
/* Liste hier Vorbedingungen auf die gegeben sein müssen um die Story umsetzen zu könne. Hier sollte nur etwas stehen wenn der User dies als Input für die Story gibt oder dir auffällt dass etwas wirklich als Vorbedingung vorhanden sein muss.*/

h4. Akzeptanzkriterien
/* Liste hier die Akzeptanzkriterien auf. Hier sollte immer etwas stehen.*/

h4. Out-of-Scope
/* Liste hier auf was nicht im scope der story ist. Falls der User kein Input gibt leer lassen.*/

h4. Design
/* Liste hier Links zum Design auf, z.B. Links zu Figma, falls der User solche als Input gibt. Sonst einfach leer lassen.*/

h4. Testing
/* Liste hier kurz auf wie die Story getestet werden muss. Falls der User kein Input gibt kannst du es auch leer lassen */

h4. Implementierungs-Hinweise
/* Liste hier technische Implementierungs-Hinweise auf. z.B. Java Klassen Namen, technische Details, etc. Falls der User dir solche gibt*/

User-Story-Vorlage ENDE -----

Formatierungs-Tips:

Benutze * für Listen. z.B.
* Erster Eintrag
* Zweiter Eintrag

Benutzer *text* um etwas fett zu markieren. 

Für sonstige Formatierungen verwende den Markdown Syntax.

```
{% endcode %}

## Coding

**Tools:** ChatGPT, GitHub Copilot

### Write new code



### Debugging



**Learnings**

* Uses older patterns, frameworks or java versions by default. Needs to be explicitly asked to use newer tooling.
* Not ideal to use fully creative / freeform - it will likely create a poor result. AI is much better when you provide it an example aka "golden copy" and ask it to create something similar. This can help speed up migrations by a lot.

## Collaboration & Information Retrieval

**Tools:** Atlassian Intelligence

### Answering questions & summarising with data from confluence&#x20;

E.g. Can I store customer data on my company notebook?

### Writing documentation



