---
title: 2.4.1 for-Konstrukt | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 27d2cbce-786b-4819-91d3-d55b2cc57a5e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cb9a554d9141223be7a5f6bc741c86b8f03511e2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46428542"
---
# <a name="241-for-construct"></a>2.4.1 for-Konstrukt

Die **für** -Direktive identifiziert eine iterative Arbeit sharing-Konstrukt, das gibt an, dass die Iterationen der Schleife zugeordnet, die parallel ausgeführt werden werden. Iterationen der **für** Schleife über Threads, die bereits im Team, das das parallele Konstrukt, das an den er gebunden ausführen verteilt sind. Die Syntax der **für** Konstrukt ist wie folgt:

```
#pragma omp for [clause[[,] clause] ... ] new-line for-loop
```

Die Klausel ist eine der folgenden:

**Private (** *Variablenliste* **)**

**Firstprivate (** *Variablenliste* **)**

**Lastprivate (** *Variablenliste* **)**

**Verringerung der (** *Operator* **:** *Variablenliste* **)**

**Sortiert**

**Zeitplan (** *Art* [**,** *Chunk_size*] **)**

**nowait**

Die **für** Richtlinie schränkt ein, auf der Struktur des entsprechenden **für** Schleife. Insbesondere die entsprechende **für** Schleife muss kanonische Form haben:

**für (** *Init-Expr* **;** *Var logische-Op-b*; *Incr-Expr* **)**

*Init-Ausdruck*<br/>
Eine der folgenden:

*Var* = *lb*

*Integer-Datentyp Var* = *lb*

*Incr-Ausdruck*<br/>
Eine der folgenden:

++ *var*

*"var"* ++

-- *var*

*"var"* --

*Var* += *Incr*

*Var* -= *Incr*

*Var* = *Var* + *Incr*

*Var* = *Incr* + *Var*

*Var* = *Var* - *Incr*

*var*<br/>
Eine ganze Zahl mit Vorzeichen-Variable. Wenn diese Variable andernfalls freigegeben werden würde, ist implizit vereinfacht private für die Dauer der **für**.   Diese Variable darf nicht geändert werden, innerhalb des Texts der **für** Anweisung. Wenn die Variable angegeben wird **Lastprivate**, dessen Wert nach die Schleife unbestimmt ist.

*logischer Vorgang durchgeführt*<br/>
Eine der folgenden:

<

\<=

>

\>=

*lb*, *b*, und *Incr*<br>
Invarianten ganzzahlige Ausdrücke eine Schleife. Es gibt keine Synchronisierung während der Auswertung dieser Ausdrücke. Daher erzeugen keine Nebeneffekte ausgewertet unbestimmte Ergebnisse.

Beachten Sie, dass die kanonische Form die Anzahl der Schleifeniterationen beim Einstieg in die Schleife berechnet werden kann. Diese Berechnung erfolgt mit den Werten in den Typ des *Var*, nach dem ganzzahlige Erweiterungen. In bestimmten, wenn der Wert des *b* - *lb* + *Incr* nicht dargestellt werden kann, Typ, das Ergebnis unbestimmt ist. Weitere, If *logische-Op* ist < oder \<= then *Incr-Expr* muss dazu führen, dass *Var* bei jeder Iteration der Schleife zu erhöhen.   Wenn *logische Op* ist > oder > = then *Incr-Expr* muss dazu führen, dass *Var* , bei jeder Iteration der Schleife zu verringern.

Die **Zeitplan** Klausel gibt an, wie Iterationen der **für** Schleife zwischen Threads des Teams aufgeteilt werden. Die Richtigkeit eines Programms darf nicht abhängig sein, auf welchem Thread eine bestimmte Iteration ausgeführt wird. Der Wert des *Chunk_size*, sofern angegeben, muss ein Schleife invariante ganzzahligen Ausdruck mit einem positiven Wert sein. Es gibt keine Synchronisierung während der Auswertung dieses Ausdrucks. Daher erzeugen keine Nebeneffekte ausgewertet unbestimmte Ergebnisse. Der Zeitplan *Art* kann einen der folgenden sein:

Tabelle 2-1 **Zeitplan** Klausel *Art* Werte

|||
|-|-|
|static|Wenn **Zeitplan (statische** *Chunk_size* **)** angegeben ist, Iterationen werden in Blöcken mit einer Größe von angegeben unterteilt *Chunk_size*. Die Blöcke werden für Threads in das Team in einem roundrobinverfahren in die Thread-Anzahl, Reihenfolge der statisch zugewiesen werden. Wenn kein *Chunk_size* angegeben ist, wird der Speicherplatz für die Iteration ist unterteilt in Blöcke unterteilt, die ungefähr gleich groß ist, abschnittsweise für jeden Thread zugewiesen sind.|
|dynamic|Wenn **Zeitplan (dynamische** *Chunk_size* **)** angegeben ist, wird die Iterationen werden in einer Reihe von Blöcken, die jeweils unterteilt *Chunk_size* Iterationen. Jeder Block wird ein Thread zugewiesen, der für eine Zuweisung wartet. Der Thread den Block von Iterationen ausgeführt und wartet dann auf die nächste Zuweisung, bis sich keine Blöcke befinden, um die zugewiesen werden. Beachten Sie, dass eine kleinere Anzahl von Iterationen das letzte Segment zugewiesen werden kann. Wenn kein *Chunk_size* angegeben ist, wird der Standardwert lautet 1.|
|geführtes|Wenn **Zeitplan (geführtes,** *Chunk_size* **)** angegeben wird, wird die Iterationen für Threads in Blöcken mit abnehmenden Größen zugewiesen sind. Wenn ein Thread seine zugewiesene Teil der Iterationen abgeschlossen ist, wird er einen anderen Block dynamisch zugewiesen, bis keine mehr vorhanden. Für eine *Chunk_size* von 1, wird die Größe jedes Segments ungefähr der Anzahl der nicht zugewiesenen Iterationen geteilt durch die Anzahl der Threads. Diese Größen werden ungefähr 1 exponentiell verringern. Für eine *Chunk_size* mit dem Wert *k* größer als 1 ist, die Größe zu verringern ungefähr exponentiell zu *k*, außer dass das letzte Segment weniger als möglicherweise  *k* Iterationen. Wenn kein *Chunk_size* angegeben ist, wird der Standardwert lautet 1.|
|Laufzeit|Wenn **Schedule(Runtime)":** angegeben wird, die Entscheidung zur Planung bis zur Laufzeit verzögert wird. Der Zeitplan *Art* und Größe der Segmente kann zur Laufzeit ausgewählt werden, durch Festlegen der Umgebungsvariablen **OMP_SCHEDULE**. Wenn diese Umgebungsvariable nicht festgelegt ist, wird der daraus resultierende Zeitplan Implementierung definiert. Wenn **Schedule(Runtime)":** angegeben wird, *Chunk_size* darf nicht angegeben werden.|

Ohne einen explizit definierten **Zeitplan** -Klausel, ist der **Zeitplan** wird durch die Implementierung definiert.

Eine OpenMP-kompatible Anwendung in einem bestimmten Zeitplan für die richtige Ausführung ist nicht empfehlenswert. Ein Programm nach einem Zeitplan nicht empfehlenswert *Art* genau zu die Beschreibung oben entsprechen, da es möglich ist, haben Variationen in den Implementierungen von dem gleichen Zeitplan *Art* über verschiedenen Compilern. Die Beschreibungen können verwendet werden, den Zeitplan auswählen, der für eine bestimmte Situation geeignet ist.

Die **sortiert** Klausel muss vorhanden sein, wenn **sortiert** Direktiven Binden an die **für** zu erstellen.

Ist eine implizite Barriere am Ende einer **für** erstellen, es sei denn, eine **Nowait** -Klausel angegeben ist.

Einschränkungen für die **für** Richtlinie lauten wie folgt:

- Die **für** Schleife muss einem strukturierten Block sein, und darüber hinaus die Ausführung nicht durch abgeschlossen sein muss eine **Break** Anweisung.

- Die Werte der Schleife steuern Ausdrücke die **für** Schleife zugeordneten eine **für** Richtlinie muss für alle Threads im Team, das identisch sein.

- Die **für** Schleife-Iterationsvariable muss einen Ganzzahltyp mit Vorzeichen aufweisen.

- Nur eine einzige **Zeitplan** Klausel darf sich auf eine **für** Richtlinie.

- Nur eine einzige **sortiert** Klausel darf sich auf eine **für** Richtlinie.

- Nur eine einzige **Nowait** Klausel darf sich auf eine **für** Richtlinie.

- Es ist nicht angegeben, If oder wie oft jede Seite in Auswirkungen nach sich ziehen die *Chunk_size*, *lb*, *b*, oder *Incr* Ausdrücke treten.

- Der Wert des der *Chunk_size* Ausdruck muss für alle Threads im Team, das identisch sein.

## <a name="cross-references"></a>Datenbankübergreifende Verweise:

- **private**, **Firstprivate**, **Lastprivate**, und **Verringerung** Klauseln finden Sie unter [Abschnitt 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) auf Seite 25.

- **OMP_SCHEDULE** Umgebung Variablen, finden Sie unter [Abschnitt 4.1](../../parallel/openmp/4-1-omp-schedule.md) auf 48.

- **geordnete** erstellen, finden Sie unter [Abschnitt 2.6.6](../../parallel/openmp/2-6-6-ordered-construct.md) auf Seite 22.

- [Anhang D](../../parallel/openmp/d-using-the-schedule-clause.md), Seite 93, erhalten Sie weitere Informationen zum Verwenden der Schedule-Klausel.