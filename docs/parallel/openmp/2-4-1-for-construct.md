---
title: 2.4.1 for-Konstrukt | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 27d2cbce-786b-4819-91d3-d55b2cc57a5e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dd861da77b549a73edf9aeface714b0066d88344
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="241-for-construct"></a>2.4.1 for-Konstrukt
Die **für** Richtlinie identifiziert eine iterative Arbeit sharing-Konstrukt, das gibt an, dass die zugeordneten Schleifeniterationen parallel ausgeführt werden. Der Iteration die **für** Schleife über Threads, die bereits in das Team das parallele Konstrukt, bindet, ausführen verteilt sind. Die Syntax der **für** Konstrukt ist wie folgt:  
  
```  
#pragma omp for [clause[[,] clause] ... ] new-linefor-loop  
```  
  
 Die-Klausel ist eine der folgenden:  
  
 **Private (** *Variablenliste* **)**  
  
 **Firstprivate (** *Variablenliste* **)**  
  
 **Lastprivate (** *Variablenliste* **)**  
  
 **Verringerung (** *Operator* **:** *Variablenliste***)**  
  
 **sortiert**  
  
 **Zeitplan (** *Art*[, *Chunk_size*]**)**  
  
 **nowait**  
  
 Die **für** Richtlinie schränkt ein, auf die Struktur des entsprechenden **für** Schleife. Insbesondere die entsprechende **für** Schleife benötigen kanonische Form:  
  
 **für (** *Init-Expr* **;** *Var logischen Op b*; *Incr-Expr***)**  
  
 *Init-Ausdruck*  
 Eine der folgenden:  
  
 *Var* = *lb*  
  
 *Integer-Datentyp Var* = *lb*  
  
 *Incr-Ausdruck*  
 Eine der folgenden:  
  
 ++*var*  
  
 *"var"* ++  
  
 -- *var*  
  
 *"var"* --  
  
 *Var* += *Incr*  
  
 *Var* -= *Incr*  
  
 *Var* = *Var* + *Incr*  
  
 *Var* = *Incr* + *Var*  
  
 *Var* = *Var* - *Incr*  
  
 *var*  
 Eine ganze Zahl mit Vorzeichen-Variable. Wenn diese Variable andernfalls freigegeben werden würden, es wird implizit gemacht private für die Dauer der **für**.   Diese Variable darf nicht geändert werden, im Hauptteil der **für** Anweisung. Wenn die Variable angegeben wird **Lastprivate**, dessen Wert nach die Schleife unbestimmt ist.  
  
 *logische op*  
 Eine der folgenden:  
  
 <  
  
 \<=  
  
 >  
  
 \>=  
  
 *lb*, *b*, und *Incr*  
 Invarianten Ganzzahl-Ausdrücke eine Schleife. Es gibt keine Synchronisierung während der Auswertung dieser Ausdrücke. Folglich zu ausgewerteten Nebeneffekten unbestimmte Ergebnissen führen.  
  
 Beachten Sie, dass die kanonische Form der Anzahl der Schleifeniterationen beim Einstieg in die Schleife berechnet werden soll. Diese Berechnung erfolgt mit den Werten in den Typ des *Var*, nach dem ganzzahlige Erweiterungen. In bestimmten, wenn der Wert der *b* - *lb* + *Incr* nicht dargestellt werden kann, dass Typ, das Ergebnis unbestimmt ist. Weitere, If *logische Op* ist < oder \<dann = *Incr-Expr* muss dazu führen, dass *Var* bei jeder Iteration der Schleife zu erhöhen.   Wenn *logische Op* ist > oder > = dann *Incr-Expr* muss dazu führen, dass *Var* bei jeder Iteration der Schleife zu verringern.  
  
 Die **Zeitplan** -Klausel gibt wie Iterationen der **für** Schleife auf Threads für das Team verteilt werden. Die korrekte Ausführung eines Programms muss hängen nicht Bestimmung des Threads mit eine bestimmte Iteration ausgeführt wird. Der Wert der *Chunk_size*, sofern angegeben, muss eine invariante Ganzzahlausdruck Schleife mit einem positiven Wert. Es gibt keine Synchronisierung beim Auswerten dieses Ausdrucks. Folglich zu ausgewerteten Nebeneffekten unbestimmte Ergebnissen führen. Der Zeitplan *Art* kann eines der folgenden sein:  
  
 Tabelle 2: 1 **Zeitplan** Klausel *Art* Werte  
  
|||  
|-|-|  
|static|Wenn **Zeitplan (statisch,** *Chunk_size***)** angegeben ist, sind Iterationen in Segmenten mit einer Größe von angegebenen unterteilt *Chunk_size*. Die Blöcke werden Threads im Team eine Roundrobin in der Reihenfolge die Thread-Anzahl statisch zugewiesen. Wenn kein *Chunk_size* angegeben ist, wird der Speicherplatz für die Iteration ist unterteilt in Blöcke unterteilt, die ungefähr im Größe mit einem beschädigten für jeden Thread zugewiesen sind.|  
|dynamic|Wenn **Zeitplan (dynamische,** *Chunk_size***)** angegeben ist, wird die Iterationen sind in einer Reihe von Segmenten, die jeweils unterteilt *Chunk_size* Iterationen. Jeder Block wird ein Thread zugewiesen, die für eine Zuordnung darauf warten. Der Thread Segments von Iterationen ausführt, und klicken Sie dann für die nächste Zuweisung wartet, bis keine Blöcke weiterhin zugewiesen werden. Beachten Sie, dass das letzte Segment zugewiesen werden soll, eine kleinere Anzahl von Iterationen aufweisen kann. Wenn kein *Chunk_size* angegeben ist, wird standardmäßig auf 1.|  
|Einführung|Wenn **Zeitplan (geführt,** *Chunk_size***)** angegeben ist, werden Threads in Segmenten mit abnehmenden Größen Iterationen zugewiesen sind. Wenn ein Thread seine zugewiesenen Dateiblock Iterationen abgeschlossen ist, wird er einen anderen Block dynamisch zugewiesen, bis keine mehr übrig sind. Für eine *Chunk_size* 1, wird die Größe jedes Segments ungefähr der Anzahl der nicht zugewiesene Iterationen dividiert durch die Anzahl der Threads. Diese Größen werden ungefähr auf 1 exponentiell verringern. Für eine *Chunk_size* mit dem Wert *k* größer als 1 ist, die Größen verringern ungefähr exponentiell zu *k*, außer dass das letzte Segment weniger möglicherweise  *k* Iterationen. Wenn kein *Chunk_size* angegeben ist, wird standardmäßig auf 1.|  
|Laufzeit|Wenn **schedule(runtime)** angegeben wird, die Entscheidung zur Planung bis zur Laufzeit verzögert wird. Der Zeitplan *Art* und Größe der Segmente zur Laufzeit ausgewählt werden kann, durch Festlegen der Umgebungsvariablen **OMP_SCHEDULE**. Wenn diese Umgebungsvariable nicht festgelegt ist, wird der resultierende Zeitplan Implementierung definiert. Wenn **schedule(runtime)** angegeben wird, *Chunk_size* muss nicht angegeben werden.|  
  
 In Ermangelung einer explizit definierte **Zeitplan** -Klausel, werden die Standardeinstellungen **Zeitplan** ist implementierungsdefiniert.  
  
 Ein OpenMP-kompatibles Programm nach einem bestimmten Zeitplan für die korrekte Ausführung, nicht empfehlenswert. Ein Programm, nach einem Zeitplan nicht empfehlenswert *Art* entsprechen, das genau mit der Beschreibung oben, da es möglich ist, die Variationen in den Implementierungen der von dem gleichen Zeitplan aufweisen *Art* über zwischen den verschiedenen Compilern. Die Beschreibungen können verwendet werden, um den Zeitplan auszuwählen, der für eine bestimmte Situation geeignet ist.  
  
 Die **sortiert** Klausel muss vorhanden sein, wenn **sortiert** Direktiven Binden an die **für** erstellen.  
  
 Besteht eine implizite Barriere am Ende einer **für** erstellen, es sei denn, eine **Nowait** -Klausel angegeben ist.  
  
 Einschränkungen für die **für** Richtlinie lauten wie folgt:  
  
-   Die **für** Schleife muss einem strukturierten Block und darüber hinaus die Ausführung muss nicht abgeschlossen werden durch eine **Break** Anweisung.  
  
-   Die Werte der Schleife Steuern von Ausdrücken die **für** Schleife zugeordnet eine **für** Richtlinie muss für alle Threads im Team identisch sein.  
  
-   Die **für** Schleifeniterationsvariable muss ein Ganzzahltyp mit Vorzeichen aufweisen.  
  
-   Nur ein einzelner **Zeitplan** -Klausel kann angezeigt werden, auf eine **für** Richtlinie.  
  
-   Nur ein einzelner **sortiert** -Klausel kann angezeigt werden, auf eine **für** Richtlinie.  
  
-   Nur ein einzelner **Nowait** -Klausel kann angezeigt werden, auf eine **für** Richtlinie.  
  
-   Es ist nicht angegeben, If oder wie oft eine Seite innerhalb Auswirkungen nach sich ziehen die *Chunk_size*, *lb*, *b*, oder *Incr* Ausdrücke auftreten.  
  
-   Der Wert, der die *Chunk_size* Ausdruck muss für alle Threads in der Team identisch sein.  
  
## <a name="cross-references"></a>Referenzen:  
  
-   **private**, **Firstprivate**, **Lastprivate**, und **Verringerung** -Klausel finden Sie unter [Abschnitt 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) auf Seite "25".  
  
-   **OMP_SCHEDULE** Umgebung-Variable verwenden, finden Sie unter [Abschnitt 4.1](../../parallel/openmp/4-1-omp-schedule.md) auf Seite 48.  
  
-   **sortiert** erstellen, finden Sie unter [Abschnitt 2.6.6](../../parallel/openmp/2-6-6-ordered-construct.md) auf der Seite "22".  
  
-   [Anhang D](../../parallel/openmp/d-using-the-schedule-clause.md), Seite 93, erhalten Sie weitere Informationen zur Verwendung der Schedule-Klausel.