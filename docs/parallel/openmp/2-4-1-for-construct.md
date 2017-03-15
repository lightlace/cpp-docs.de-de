---
title: "2.4.1 for Construct"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 27d2cbce-786b-4819-91d3-d55b2cc57a5e
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# 2.4.1 for Construct
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die **nach**\-Direktive identifizieren ein wiederholendes Arbeitsteilungs konstrukt, das angibt, dass die Iterationen der Schleife zugeordneten parallel ausgeführt werden.  Die Iterationen der Schleife **nach** werden über Threads verteilt, die bereits vorhanden sind, die das Team im parallelen Konstrukt ausgeführt wird, an das sie gebunden wird.  Die Syntax des **nach** Konstrukts lautet wie folgt:  
  
```  
#pragma omp for [clause[[,] clause] ... ] new-line  
   for-loop  
```  
  
 Die Klausel ist eine der folgenden Aktionen aus:  
  
 **\(privat**Variable*Liste***\)**  
  
 **\(firstprivate**Variable*Liste***\)**  
  
 **\(lastprivate**Variable*Liste***\)**  
  
 *Operator*  **\(Verringerung**:\-*Variable Liste***\)**  
  
 **geordnet**  
  
 **\(Zeitplan** *Weise* *chunk\_size*\[,\],**\)**  
  
 **nowait**  
  
 Die Einschränkungen des Direktivenprozessors Stelle in der Struktur entsprechenden **nachnach** Schleife.  Insbesondere muss die entsprechende **nach** Schleife kanonische Form aufweisen:  
  
 **\(für** *INIT\-expr* **;** *var logisch\-OP*;*b* *Zunahme\-expr***\)**  
  
 *INIT\-expr*  
 Eine der folgenden Anwendungen:  
  
 *var* \= *lbs*  
  
 *TYPE var* \= *lbs**Zahl*  
  
 *Zunahme\-expr*  
 Eine der folgenden Anwendungen:  
  
 \+\+var  
  
 *var* \+\+  
  
 \-\- *Variable*  
  
 *Variable* \-\-  
  
 *Zunahme* *var* \+\=  
  
 \- \=*Variable* selbst *reservieren Sie eine größere*  
  
 *erhöht*\+ *var* \=*Variable*  
  
 *var* \= *erhöht* \+ *var*  
  
 *var* \= *Variable* \- *incr*  
  
 *Variable*  
 Eine ganzzahlige Variable mit Vorzeichen.  Wenn diese Variablen freigegeben wird, andernfalls wird sie implizit privat für die Dauer **nach**gemacht.  Diese Variable darf nicht im Text der **nach**\-Anweisung geändert werden.  Sofern die Variable ein angegebenes **lastprivate**ist sein Wert, nachdem die Schleife unbestimmt ist.  
  
 *logisch\-OP*  
 Eine der folgenden Anwendungen:  
  
 \<  
  
 \<\=  
  
 \>  
  
 \>\=  
  
 *lbs*, *b*und  
 Ausdrücke der ganzen Zahl von Schleifen invarianten Elements.  Es gibt keine Synchronisierung während der Auswertung dieser Begriffe.  Wie alle ausgewerteten unbestimmten Ergebnissen Nebeneffekt erzeugnisses.  
  
 Beachten Sie, dass die kanonische Form die Anzahl der auf den Eintrag kann berechnet werden soll, iterationen Schleifen der Schleife.  Diese Berechnung wird mit Werten im Typ von *var*bei ganzzahligen Erweiterungen ausgeführt.  Insbesondere wenn der Wert von *b* \- *lbs* \+ *erhöht* kann nicht in diesen Typ dargestellt werden, das Ergebnis ist unbestimmt.  Darüber hinaus *logisch\-OP,* wenn \< ist *,* oder \<\= dann *Zunahme\-expr* *Variable* muss sich dazu führen, dass bei jeder Iteration der Schleife erhöht werden soll.  Wenn *logisch\-OP* \> ist *,* oder \>\= dann *Zunahme\-expr* dazu führen, dass *Variable* muss für jede Iteration der Schleife zu verringern.  
  
 Die **Zeitplan**\-Klausel gibt an, wie Iterationen der Schleife **nach** unter Threads des Teams eingeteilt werden.  Die ordnungsgemäße Ausführung eines Programms darf nicht aus welchem Thread angewiesen, eine bestimmte Iteration ausführt.  Der Wert von *chunk\_size*, wenn er angegeben wird, muss ein ganzzahliger Ausdruck der Schleifen invarianten Elements mit einem positiven Wert sein.  Es gibt keine Synchronisierung während der Auswertung des Ausdrucks.  Daher stellen alle ausgewerteten Nebeneffekte unbestimmte Ergebnisse.  Die *Art der* Zeitplan kann einer der folgenden Werte sein:  
  
 TABELLE 2\-1 Werte *arten*\-Klausel **Zeitplan**  
  
|||  
|-|-|  
|static|Wenn **Zeitplan \(statisch.** *chunk\_size,*wird**\)** Iterationen werden, unterteilt in Ausschnitte eine Größe angegeben, die durch angegeben ist, *chunk\_size*.  Die Ausschnitte sind statisch an Threads im Team in einer Roundrobinen Weise in der Reihenfolge der Thread Zahl zugewiesen.  Wenn kein *chunk\_size,* wird die Iteration leer ist in Blöcke aufgeteilt, die Größe ungefähr gleich sind, wenn ein Ausschnitt zu jedem Thread zugewiesen ist angegeben.|  
|dynamic|Wenn **dynamisch \(Zeitplan** *chunk\_size,*wird**\)** , die unterteilt werden Ausschnitte in eine Reihe von Iterationen jedes enthaltenden *chunk\_size* Iterationen angegeben.  Jeder Ausschnitt ist einem Thread zugewiesen, der eine Zuweisung wartet.  Der Thread führt den Ausschnitt der Iterationen aus und wartet dann auf seine folgende Zuweisung, bis keine Ausschnitte zugewiesen sein bleiben.  Beachten Sie, dass der letzte Block zugewiesen werden soll, kann eine kleinere Anzahl der Iterationen hat.  Wenn kein *chunk\_size,* wird es standardmäßig auf 1 festgelegt.|  
|Einführungs|Wenn **Zeitplan \(Einführungs.** *chunk\_size,*wird**\)** , die Iterationen zugewiesen wurden an Threads mit Ausschnitten in den Größen abnimmt.  Wenn ein Thread den zugewiesenen Ausschnitt von Iterationen beendet, wird er dynamisch einen anderen Ausschnitt zugewiesen, wenn keine bleiben.  Für ein *chunk\_size* 1, ist die Größe jedes Ausschnitts etwa die Anzahl der nicht zugewiesenen Iterationen durch die Anzahl der Threads.  Diese Größe verkleinern sich etwa exponential bis 1.  Für ein *chunk\_size* *k* mit dem Wert *, der* größer als 1 verringert sich die Größe exponential Info zu *k*, mit der Ausnahme, dass der letzte Block ist möglicherweise kleiner als *k\-Iterationen* .  Wenn kein *chunk\_size,* wird es standardmäßig auf 1 festgelegt.|  
|Runtime|Wenn **Zeitplan \(Common Language Runtime\)** angegeben wird, wird die Entscheidung bezüglich Planung bis zur Laufzeit verzögert.  Die *Art der* Zeitplan und die Größe der Blöcke können zur Laufzeit ausgewählt werden, indem Sie die Umgebungsvariable **OMP\_SCHEDULE**festlegt.  Diese Umgebungsvariable nicht festgelegt ist, wird der resultierende Zeitplan Implementierung\-definiert.  Wenn **Zeitplan \(Common Language Runtime\)** angegeben wird, *chunk\_size* darf nicht angegeben werden.|  
  
 In Ermangelung einer explizit definierten **Zeitplan**\-Klausel wird der Standardwert **Zeitplan** Implementierung\-definiert.  
  
 Ein OpenMP\-kompatibles Programm sollte nicht auf einem bestimmten Zeitplan für eine ordnungsgemäße Ausführung basieren.  Ein Programm sollte nicht nach einem Zeitplan erstellen *die Art, die* sich genau an das angegebene oben genannte Beschreibung entspricht, da es möglich ist, Schwankungen Implementierungen der gleichen Zeitplan über verschiedene *Art der* Compiler haben.  Die Beschreibungen können verwendet werden, um den Zeitplan auszuwählen, der für eine bestimmte Situation geeignet ist.  
  
 Die **geordnet**\-Klausel muss als **geordnet**\-Direktive Datenbindung an den **nach** Konstrukt vorhanden sein.  
  
 Es gibt eine implizite Grenze am Ende eines **nach** Konstrukts, es sei denn, eine **nowait**\-Klausel angegeben wird.  
  
 Einschränkungen für **nach**\-Direktive lauten wie folgt:  
  
-   Die **nach** Schleife muss ein strukturierter Block sein, und darf nicht durch eine break\-Anweisung ihre Ausführung beendet werden.  
  
-   Die Werte der **nach** der Ausdrücke steuer \- Schleife, die mit **nach**\-Direktive zugeordnet ist, müssen die Verfahren für alle Threads im Team sein.  
  
-   Die **nach** Schleifeniterationsvariable muss einen ganzzahligen Typ mit Vorzeichen.  
  
-   Nur eine einzige **Zeitplan**\-Klausel kann auf **nach**\-Direktive angezeigt werden.  
  
-   Nur eine einzige **geordnet**\-Klausel kann auf **nach**\-Direktive angezeigt werden.  
  
-   Nur eine einzige **nowait**\-Klausel kann auf **nach**\-Direktive angezeigt werden.  
  
-   Sie ist nicht angegeben, wieoft, oder wenn alle Nebeneffekte in der *chunk\_size*, *lbs\-*, *b\-*oder *Zunahme\-Ausdrücke* auftreten.  
  
-   Der Wert des Ausdrucks *chunk\_size* muss derselbe für alle Threads in Team sein.  
  
## Querverweise:  
  
-   **private**, **firstprivate**, **lastprivate**und **Verringerung**\-Klauseln finden [2.7.2 Abschnitt](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) auf Seite 25.  
  
-   **OMP\_SCHEDULE** Umgebungsvariablen finden [Abschnitt 4.1](../../parallel/openmp/4-1-omp-schedule.md) auf Seite 48.  
  
-   **geordnet** Konstrukt finden [2.6.6 Abschnitt](../../parallel/openmp/2-6-6-ordered-construct.md) auf Seite 22.  
  
-   [Anhang D](../../parallel/openmp/d-using-the-schedule-clause.md)Seite 93, gibt weitere Informationen über die Verwendung der Zeitplan clause.