---
title: 2. Anweisungen
ms.date: 01/18/2019
ms.assetid: d1a69374-6c03-45fb-8c86-e91cea8adae8
ms.openlocfilehash: 125d2d83b277e62d007e3a208e426ea717d52790
ms.sourcegitcommit: 382e247c0f1b4cb7c2dab837b8b6fdff24bff47a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2019
ms.locfileid: "55087339"
---
# <a name="2-directives"></a>2. Anweisungen

Anweisungen basieren auf `#pragma` Direktiven, die in den C- und C++-Standards definiert.  Compiler, die der OpenMP-C- und C++-API unterstützen, werden eine Befehlszeilenoption enthalten, die aktiviert und ermöglicht die Darstellung alle OpenMP Compilerdirektiven.

## <a name="21-directive-format"></a>2.1 direktivenformat

Die Syntax einer OpenMP-Direktive wird offiziell angegeben, indem die Grammatik in [Anhang C](c-openmp-c-and-cpp-grammar.md), informell wie folgt:

```cpp
#pragma omp directive-name  [clause[ [,] clause]...] new-line
```

Jede Anweisung beginnt mit `#pragma omp`, um das Potenzial für einen Konflikt mit anderen (nicht-OpenMP oder Anbieter-Erweiterungen mit OpenMP)-Pragma-Direktiven mit den gleichen Namen zu reduzieren. Der Rest der Anweisung folgt die Konventionen der C- und C++-Standards für Compiler-Direktiven. Insbesondere Leerraum kann verwendet werden vor und nach der `#`, und manchmal darf Leerzeichen verwendet werden, um die Wörter in einer Anweisung zu trennen. Vorverarbeitungstoken befolgen die `#pragma omp` makroersetzung unterliegen.

Richtlinien beachtet werden. Die Reihenfolge der Klauseln in Anweisungen keine Bedeutung. Klauseln auf Anweisungen können wiederholt werden, bei Bedarf gemäß den Einschränkungen, die in der Beschreibung der einzelnen Klauseln aufgeführt. Wenn *Variablenliste* wird in einer Klausel nur Variablen angegeben werden muss. Nur ein *Richtlinie-Name* kann pro Richtlinie angegeben werden.  Beispielsweise ist nicht die folgende Anweisung zulässig:

```cpp
/* ERROR - multiple directive names not allowed */
#pragma omp parallel barrier
```

Eine OpenMP-Direktive gilt für höchstens einer nachfolgenden Anweisung, die einem strukturierten Block sein muss.

## <a name="22-conditional-compilation"></a>2.2 bedingte Kompilierung

Die `_OPENMP` Makroname wird durch OpenMP konforme Implementierungen als dezimale Konstante definiert *Yyyymm*, die das Jahr und Monat der genehmigten Spezifikation sein. Dieses Makro muss nicht das Subjekt einer `#define` oder `#undef` -präprozessanweisung.

```cpp
#ifdef _OPENMP
iam = omp_get_thread_num() + index;
#endif
```

Wenn der Anbieter Erweiterungen mit OpenMP definieren, können sie weitere vordefinierte Makros angeben.

## <a name="23-parallel-construct"></a>2.3 parallel-Konstrukt

Die folgende Anweisung definiert ein paralleles Bereichs, das in einem Bereich des Programms ist, die von vielen Threads parallel ausgeführt werden soll. Diese Direktive ist das grundlegende Konstrukt, das die parallele Ausführung beginnt.

```cpp
#pragma omp parallel [clause[ [, ]clause] ...] new-line   structured-block
```

Die *Klausel* ist eine der folgenden:

- `if(` *scalar-expression* `)`
- `private(` *variable-list* `)`
- `firstprivate(` *variable-list* `)`
- `default(shared | none)`
- `shared(` *variable-list* `)`
- `copyin(` *variable-list* `)`
- `reduction(` *operator* `:`  *variable-list* `)`
- `num_threads(` *integer-expression* `)`

Wenn ein Thread eines parallelen Konstrukts nähert, wird ein Team von Threads erstellt, wenn eine der folgenden Fälle zutrifft:

- Keine `if` -Klausel vorhanden ist.
- Die `if` Ausdruck ausgewertet wird, einen Wert ungleich NULL.

Dieser Thread wird die master-Thread des Teams, mit einer Thread-Anzahl von 0 (null), und alle Threads in der master-Thread, einschließlich die Region parallel ausgeführt. Wenn der Wert des der `if` Ausdruck NULL ist, wird die Region wird serialisiert.

Um die Anzahl der Threads zu bestimmen, die angefordert werden, werden die folgenden Regeln in der Reihenfolge betrachtet. Die erste Regel, deren Bedingung erfüllt ist, werden angewendet werden:

1. Wenn die `num_threads` -Klausel vorhanden ist, und klicken Sie dann der Wert des der ganzzahlige Ausdruck wird die Anzahl der Threads angefordert.

1. Wenn die `omp_set_num_threads` Library-Funktion aufgerufen wurde, und klicken Sie dann der Wert des Arguments in der zuletzt ausgeführten Aufruf wird die Anzahl der Threads angefordert.

1. Wenn die Umgebungsvariable `OMP_NUM_THREADS` definiert ist, wird der Wert dieser Umgebungsvariablen die Anzahl der Threads, die angefordert wird.

1. Wenn keine der oben genannten Methoden verwendet wird, wird die Anzahl der angeforderten Threads Implementierung definiert.

Wenn die `num_threads` -Klausel vorhanden ist, und klicken Sie dann die Anzahl der Threads, die vom angeforderten ersetzt die `omp_set_num_threads` Bibliotheksfunktion oder das `OMP_NUM_THREADS` Umgebungsvariable nur für den parallelen Bereich, die er angewendet wird. Später parallele Bereichen sind nicht betroffen.

Die Anzahl der Threads, die den parallelen Bereich ausgeführt werden. zudem hängt davon ab, ob die dynamische Anpassung der Anzahl der Threads aktiviert ist. Wenn dynamische platzierungseinstellung deaktiviert ist, wird die angeforderte Anzahl von Threads die parallelen Bereichs ausgeführt. Wenn die dynamische Anpassung aktiviert ist, ist die angeforderte Anzahl von Threads die maximale Anzahl von Threads, die den parallelen Bereich ausgeführt werden können.

Wenn es sich bei ein paralleler Bereich gefunden wird, während dynamische Anpassung der Anzahl von Threads ist deaktiviert, und die Anzahl der Threads, die für den parallelen Bereich angefordert wird, mehr als die Zahl, die das System zur Laufzeit bereitstellen kann, ist das Verhalten des Programms Implementierung definiert. Eine Implementierung kann z. B. die Ausführung des Programms unterbrechen, oder den parallelen Bereich serialisieren kann.

Die `omp_set_dynamic` Library-Funktion und die `OMP_DYNAMIC` Umgebungsvariable zum Aktivieren und deaktivieren die dynamische Anpassung der Anzahl von Threads verwendet werden kann.

Die Anzahl der physischen Prozessoren tatsächlich die Threads hosten, zu jedem Zeitpunkt wird die Implementierung definiert. Nach der Erstellung bleibt die Anzahl der Threads im Team für die Dauer der parallelen Region konstant. Er kann entweder explizit vom Benutzer oder automatisch vom System zur Laufzeit aus einer parallel-Region in eine andere geändert werden.

Die Anweisungen in der dynamischen Wertebereich des parallelen Bereichs enthaltenen von allen Threads ausgeführt werden, und einen Pfad von Anweisungen, der sich von anderen Threads wird von jeder Thread ausgeführt werden kann. Anweisungen, die außerhalb der lexikalischen Wertebereich eines parallelen Bereichs gefunden werden als verwaiste Direktiven bezeichnet.

Es gibt eine implizite Barriere am Ende eines parallelen Bereichs ein. Nur die master-Thread des Teams wird die Ausführung am Ende eines parallelen Bereichs fortgesetzt.

Wenn ein Thread in einem Team, das Ausführen eines parallelen Bereichs ein anderes paralleles Konstrukt auftritt, erstellt ein neues Team, und es wird als übergeordneter das neue Team. Standardmäßig werden die geschachtelten parallele Bereichen serialisiert. Daher wird in der Standardeinstellung ein geschachtelten paralleles Bereichs von einem Team besteht aus einem Thread ausgeführt. Das Standardverhalten kann geändert werden, mit der Common Language Runtime-Bibliotheksfunktion `omp_set_nested` oder die Umgebungsvariable `OMP_NESTED`. Die Anzahl der Threads in einem Team, die ausführen ein geschachtelten paralleles Bereichs ist jedoch die Implementierung definiert.

Einschränkungen für die `parallel` Richtlinie lauten wie folgt:

- Höchstens ein `if` Klausel kann in der Richtlinie angezeigt werden.

- Es wurde nicht angegeben, ob alle Effekte in der If Seite Ausdruck oder `num_threads` Ausdruck auftreten.

- Ein `throw` innerhalb ein paralleles Bereichs muss dazu führen, dass in der dynamischen Wertebereich denselben strukturierten Block Fortsetzen der Ausführung ausgeführt, und es muss abgefangen werden, von dem gleichen Thread, der die Ausnahme ausgelöst hat.

- Nur eine einzige `num_threads` Klausel kann in der Richtlinie angezeigt werden. Die `num_threads` Ausdruck im Kontext des parallelen Bereichs ausgewertet wird, und muss zu einer positiven Ganzzahl ausgewertet.

- Die Reihenfolge der Auswertung der `if` und `num_threads` Klauseln ist nicht angegeben.

### <a name="cross-references"></a>Querverweise

- `private`, `firstprivate`, `default`, `shared`, `copyin`, und `reduction` Klauseln ([Abschnitt 2.7.2](#272-data-sharing-attribute-clauses))
- [OMP_NUM_THREADS](4-environment-variables.md#42-omp_num_threads) -Umgebungsvariable
- [Omp_set_dynamic](3-run-time-library-functions.md#317-omp_set_dynamic-function) Library-Funktion
- [OMP_DYNAMIC](4-environment-variables.md#43-omp_dynamic) -Umgebungsvariable
- [Omp_set_nested](3-run-time-library-functions.md#319-omp_set_nested-function) Funktion
- [OMP_NESTED](4-environment-variables.md#44-omp_nested) -Umgebungsvariable
- [Omp_set_num_threads](3-run-time-library-functions.md#311-omp_set_num_threads-function) Library-Funktion

## <a name="24-work-sharing-constructs"></a>2.4 Arbeitsteilungskonstrukte

Ein Konstrukt Freigabe von Arbeit verteilt, die Ausführung der Anweisung zugeordnet, unter den Mitgliedern des Teams, die auftreten. Die gemeinsame Verwendung von Work-Anweisungen keine neuen Threads zu starten, und besteht keine implizite Hindernisse beim Einstieg in eine gemeinsame Verwendung von Work-Konstrukt.

Erstellt die Abfolge der Freigabe von Arbeit und `barrier` Direktiven, die auftreten müssen für jeden Thread in einem Team identisch sein.

OpenMP definiert die folgenden Arbeitsteilungskonstrukte, und diese Konstrukte werden in den folgenden Abschnitten beschrieben:

- [für](#241-for-construct) Richtlinie
- [Abschnitte](#242-sections-construct) Richtlinie
- [einzelne](#243-single-construct) Richtlinie

### <a name="241-for-construct"></a>2.4.1 for-Konstrukt

Die `for` -Direktive identifiziert eine iterative Arbeit sharing-Konstrukt, das gibt an, dass die Iterationen der Schleife zugeordnet, die parallel ausgeführt werden werden. Iterationen der `for` Schleife über Threads, die bereits im Team, das das parallele Konstrukt, das an den er gebunden ausführen verteilt sind. Die Syntax der `for` Konstrukt ist wie folgt:

```cpp
#pragma omp for [clause[[,] clause] ... ] new-line for-loop
```

Die Klausel ist eine der folgenden:

- `private(` *variable-list* `)`
- `firstprivate(` *variable-list* `)`
- `lastprivate(` *variable-list* `)`
- `reduction(` *operator* `:` *variable-list* `)`
- `ordered`
- `schedule(` *kind* [`,` *chunk_size*] `)`
- `nowait`

Die `for` Richtlinie schränkt ein, auf der Struktur des entsprechenden `for` Schleife. Insbesondere die entsprechende `for` Schleife muss kanonische Form haben:

`for (` *Init-Expr* `;` *Var logische-Op-b* `;` *Incr-Ausdruck* `)`

*init-expr*<br/>
Eine der folgenden:

- *var* = *lb*
- *Integer-Datentyp Var* = *lb*

*incr-expr*<br/>
Eine der folgenden:

- `++` *var*
- *var* `++`
- `--` *var*
- *var* `--`
- *var* `+=` *incr*
- *var* `-=` *incr*
- *var* `=` *var* `+` *incr*
- *var* `=` *incr* `+` *var*
- *var* `=` *var* `-` *incr*

*var*<br/>
Eine ganze Zahl mit Vorzeichen-Variable. Wenn diese Variable andernfalls freigegeben werden würde, ist implizit vereinfacht private für die Dauer der `for`. Ändern Sie diese Variable innerhalb des Texts nicht die `for` Anweisung. Wenn die Variable angegeben wird `lastprivate`, dessen Wert nach die Schleife unbestimmt ist.

*logical-op*<br/>
Eine der folgenden:

- `<`
- `<=`
- `>`
- `>=`

*lb*, *b*, und *Incr*<br>
Invarianten ganzzahlige Ausdrücke eine Schleife. Es besteht keine Synchronisierung während der Auswertung von diesen Ausdrücken kann auf, damit keine Nebeneffekte ausgewertet zu unvorhersehbaren Ergebnissen führen.

Die kanonische Form können die Anzahl der Schleifeniterationen beim Einstieg in die Schleife berechnet werden soll. Diese Berechnung erfolgt mit den Werten in den Typ des *Var*, nach dem ganzzahlige Erweiterungen. In bestimmten, wenn der Wert des *b* `-` *lb* `+` *Incr* nicht dargestellt werden kann, Typ, das Ergebnis unbestimmt ist. Weitere, If *logische Op* ist `<` oder `<=`, klicken Sie dann *Incr-Expr* muss dazu führen, dass *Var* bei jeder Iteration der Schleife zu erhöhen.   Wenn *logische Op* ist `>` oder `>=`, klicken Sie dann *Incr-Expr* muss dazu führen, dass *Var* , bei jeder Iteration der Schleife kleiner zu werden.

Die `schedule` Klausel gibt an, wie Iterationen der `for` Schleife zwischen Threads des Teams aufgeteilt werden. Die Richtigkeit eines Programms darf nicht abhängig sein, auf welchem Thread eine bestimmte Iteration ausgeführt wird. Der Wert des *Chunk_size*, sofern angegeben, muss ein Schleife invariante ganzzahligen Ausdruck mit einem positiven Wert sein. Es besteht keine Synchronisierung während der Auswertung dieses Ausdrucks auf, damit keine Nebeneffekte ausgewertet zu unvorhersehbaren Ergebnissen führen. Der Zeitplan *Art* kann eine der folgenden Werte:

Tabelle 2-1: `schedule` Klausel *Art* Werte

|||
|-|-|
|static|Wenn `schedule(static,` *Chunk_size* `)` angegeben ist, Iterationen werden in Blöcken mit einer Größe von angegeben unterteilt *Chunk_size*. Die Blöcke werden für Threads in das Team in einem roundrobinverfahren in die Thread-Anzahl, Reihenfolge der statisch zugewiesen werden. Wenn kein *Chunk_size* angegeben ist, wird der Speicherplatz für die Iteration ist unterteilt in Blöcke unterteilt, die ungefähr gleich groß ist, abschnittsweise für jeden Thread zugewiesen sind.|
|dynamic|Wenn `schedule(dynamic,` *Chunk_size* `)` angegeben ist, wird die Iterationen werden in einer Reihe von Blöcken, die jeweils unterteilt *Chunk_size* Iterationen. Jeder Block wird ein Thread zugewiesen, der für eine Zuweisung wartet. Der Thread den Block von Iterationen ausgeführt und wartet dann auf die nächste Zuweisung, bis sich keine Blöcke befinden, um die zugewiesen werden. Das letzte Segment zugewiesen werden, möglicherweise eine kleinere Anzahl von Iterationen. Wenn kein *Chunk_size* angegeben ist, wird der Standardwert lautet 1.|
|geführtes|Wenn `schedule(guided,` *Chunk_size* `)` angegeben wird, wird die Iterationen für Threads in Blöcken mit abnehmenden Größen zugewiesen sind. Wenn ein Thread seine zugewiesene Teil der Iterationen abgeschlossen ist, hat er einen anderen Block dynamisch zugewiesen, bis keine verlassen wird. Für eine *Chunk_size* von 1, wird die Größe jedes Segments ungefähr der Anzahl der nicht zugewiesenen Iterationen geteilt durch die Anzahl der Threads. Diese Größen werden fast exponentiell auf 1 verringern. Für eine *Chunk_size* mit dem Wert *k* größer als 1 ist, die Größe zu verringern fast exponentiell zu *k*, außer dass das letzte Segment weniger als möglicherweise *k* Iterationen. Wenn kein *Chunk_size* angegeben ist, wird der Standardwert lautet 1.|
|runtime|Wenn `schedule(runtime)` angegeben wird, die Entscheidung zur Planung bis zur Laufzeit verzögert wird. Der Zeitplan *Art* und Größe der Segmente kann zur Laufzeit ausgewählt werden, durch Festlegen der Umgebungsvariablen `OMP_SCHEDULE`. Wenn diese Umgebungsvariable nicht festgelegt ist, wird der daraus resultierende Zeitplan Implementierung definiert. Wenn `schedule(runtime)` angegeben wird, *Chunk_size* darf nicht angegeben werden.|

Ohne einen explizit definierten `schedule` -Klausel, ist der `schedule` wird durch die Implementierung definiert.

Eine OpenMP-kompatible Anwendung sollte nicht in einem bestimmten Zeitplan für die richtige Ausführung basieren. Ein Programm darf nicht nach einem Zeitplan basieren *Art* genau zu die Beschreibung oben entsprechen, da es möglich ist, haben Variationen in den Implementierungen von dem gleichen Zeitplan *Art* über verschiedenen Compilern. Die Beschreibungen können verwendet werden, den Zeitplan auswählen, der für eine bestimmte Situation geeignet ist.

Die `ordered` Klausel muss vorhanden sein, wenn `ordered` Direktiven Binden an die `for` zu erstellen.

Ist eine implizite Barriere am Ende einer `for` erstellen, es sei denn, eine `nowait` -Klausel angegeben ist.

Einschränkungen für die `for` Richtlinie lauten wie folgt:

- Die `for` Schleife muss einem strukturierten Block sein, und darüber hinaus die Ausführung nicht durch abgeschlossen sein muss eine `break` Anweisung.

- Die Werte der Schleife steuern Ausdrücke die `for` Schleife zugeordneten eine `for` Richtlinie muss für alle Threads im Team, das identisch sein.

- Die `for` Schleife-Iterationsvariable muss einen Ganzzahltyp mit Vorzeichen aufweisen.

- Nur eine einzige `schedule` Klausel darf sich auf eine `for` Richtlinie.

- Nur eine einzige `ordered` Klausel darf sich auf eine `for` Richtlinie.

- Nur eine einzige `nowait` Klausel darf sich auf eine `for` Richtlinie.

- Es ist nicht angegeben, If oder wie oft jede Seite in Auswirkungen nach sich ziehen die *Chunk_size*, *lb*, *b*, oder *Incr* Ausdrücke treten.

- Der Wert des der *Chunk_size* Ausdruck muss für alle Threads im Team, das identisch sein.

#### <a name="cross-references"></a>Querverweise

- `private`, `firstprivate`, `lastprivate`, und `reduction` Klauseln ([Abschnitt 2.7.2](#272-data-sharing-attribute-clauses))
- [OMP_SCHEDULE](4-environment-variables.md#41-omp_schedule) -Umgebungsvariable
- [geordnete](#266-ordered-construct) erstellen
- [Zeitplan](d-using-the-schedule-clause.md) Klausel

### <a name="242-sections-construct"></a>2.4.2 Abschnitte zu erstellen.

Die `sections` -Direktive identifiziert ein noniterative Arbeit sharing-Konstrukt, das einen Satz von Konstrukten gibt an, die auf die Threads in einem Team aufgeteilt werden. Jeder Abschnitt wird von einem Thread im Team einmal ausgeführt. Die Syntax der `sections` Richtlinie lautet wie folgt:

```cpp
#pragma omp sections [clause[[,] clause] ...] new-line
   {
   [#pragma omp section new-line]
      structured-block
   [#pragma omp section new-linestructured-block ]
...
}
```

Die Klausel ist eine der folgenden:

- `private(` *variable-list* `)`
- `firstprivate(` *variable-list* `)`
- `lastprivate(` *variable-list* `)`
- `reduction(` *operator* `:`  *variable-list* `)`
- `nowait`

Jeder Abschnitt vorangestellt ist eine `section` Richtlinie, obwohl die `section` Richtlinie ist optional für den ersten Abschnitt. Die `section` Anweisungen müssen innerhalb der lexikalischen Wertebereich angezeigt werden die `sections` Richtlinie. Ist eine implizite Barriere am Ende einer `sections` zu erstellen, es sei denn, eine `nowait` angegeben ist.

Einschränkungen für die `sections` Richtlinie lauten wie folgt:

- Ein `section` Richtlinie muss nicht außerhalb der lexikalischen Wertebereich angezeigt werden. die `sections` Richtlinie.

- Nur eine einzige `nowait` Klausel darf sich auf eine `sections` Richtlinie.

#### <a name="cross-references"></a>Querverweise

- `private`, `firstprivate`, `lastprivate`, und `reduction` Klauseln ([Abschnitt 2.7.2](#272-data-sharing-attribute-clauses))

### <a name="243-single-construct"></a>2.4.3 single-Konstrukt

Die `single` -Direktive identifiziert ein Konstrukt, das angibt, dass die zugehörigen strukturierte Block von nur einem Thread im Team (nicht unbedingt der master-Thread) ausgeführt wird. Die Syntax der `single` Richtlinie lautet wie folgt:

```cpp
#pragma omp single [clause[[,] clause] ...] new-linestructured-block
```

Die Klausel ist eine der folgenden:

- `private(` *variable-list* `)`
- `firstprivate(` *variable-list* `)`
- `copyprivate(` *variable-list* `)`
- `nowait`

Es gibt eine implizite Barriere nach der `single` erstellen, es sei denn, eine `nowait` -Klausel angegeben ist.

Einschränkungen für die `single` Richtlinie lauten wie folgt:

- Nur eine einzige `nowait` Klausel darf sich auf eine `single` Richtlinie.
- Die `copyprivate` Klausel darf nicht verwendet werden, mit der `nowait` Klausel.

#### <a name="cross-references"></a>Querverweise

- `private`, `firstprivate`, und `copyprivate` Klauseln ([Abschnitt 2.7.2](#272-data-sharing-attribute-clauses))

## <a name="25-combined-parallel-work-sharing-constructs"></a>2.5 kombinierte parallele Arbeitsteilungskonstrukte

Kombinierte parallele Arbeitsteilungskonstrukte werden Verknüpfungen zum Angeben eines parallelen Bereichs, das nur eine gemeinsame Verwendung von Work-Konstrukt verfügt. Die Semantik dieser Anweisungen entsprechen die explizite Angabe einer `parallel` -Direktive gefolgt von einer single-Konstrukt, der auf der Freigabe von Arbeit.

In den folgenden Abschnitten wird beschrieben, die kombinierte parallele Arbeitsteilungskonstrukte werden:

- [für die parallele](#251-parallel-for-construct) Richtlinie
- [Parallel Sections-](#252-parallel-sections-construct) Richtlinie

### <a name="251-parallel-for-construct"></a>2.5.1 Parallel for-Konstrukt

Die `parallel for` Richtlinie ist eine Abkürzung für eine `parallel` Bereich, nur eine einzige enthält `for` Richtlinie. Die Syntax der `parallel for` Richtlinie lautet wie folgt:

```cpp
#pragma omp parallel for [clause[[,] clause] ...] new-linefor-loop
```

Mit dieser Direktive können alle Klauseln der der `parallel` Richtlinie und die `for` Direktive, mit Ausnahme der `nowait` -Klausel, wobei identische Bedeutung und den gleichen Einschränkungen. Die Semantik ist derselbe, als wenn explizit eine `parallel` unmittelbar nach der Richtlinie eine `for` Richtlinie.

#### <a name="cross-references"></a>Querverweise

- [Parallele](#23-parallel-construct) Richtlinie
- [für](#241-for-construct) Richtlinie
- [Daten-Attribut-Klauseln](#272-data-sharing-attribute-clauses)

### <a name="252-parallel-sections-construct"></a>2.5.2 parallel Abschnitte zu erstellen.

Die `parallel sections` Richtlinie stellt eine Verknüpfung-Form für die Angabe einer `parallel` Region, die nur eine einzige `sections` Richtlinie. Die Semantik ist derselbe, als wenn explizit eine `parallel` unmittelbar nach der Richtlinie eine `sections` Richtlinie. Die Syntax der `parallel sections` Richtlinie lautet wie folgt:

```cpp
#pragma omp parallel sections  [clause[[,] clause] ...] new-line
   {
   [#pragma omp section new-line]
      structured-block
   [#pragma omp section new-linestructured-block  ]
   ...
}
```

Die *Klausel* kann eine der Klauseln, die vom akzeptiert die `parallel` und `sections` -Anweisungen außer der `nowait` Klausel.

#### <a name="cross-references"></a>Querverweise

- [Parallele](#23-parallel-construct) Richtlinie
- [Abschnitte](#242-sections-construct) Richtlinie

## <a name="26-master-and-synchronization-directives"></a>2.6 Master- und Synchronisierung-Direktiven

Die folgenden Abschnitte beschreiben:

- [master](#261-master-construct) construct
- [kritische](#262-critical-construct) erstellen
- [Barriere](#263-barrier-directive) Richtlinie
- [atomic](#264-atomic-construct) construct
- [leeren](#265-flush-directive) Richtlinie
- [geordnete](#266-ordered-construct) erstellen

### <a name="261-master-construct"></a>2.6.1 master-Konstrukt

Die `master` -Direktive identifiziert ein Konstrukt, das einem strukturierten Block gibt an, die durch die master-Thread des Teams ausgeführt wird. Die Syntax der `master` Richtlinie lautet wie folgt:

```cpp
#pragma omp master new-linestructured-block
```

Andere Threads im Team, das führen nicht den zugeordneten strukturierten Block. Es gibt keine implizite Hindernisse, die entweder zu Beginn oder nach Beendigung der master-Konstrukt.

### <a name="262-critical-construct"></a>2.6.2 critical-Konstrukt

Die `critical` -Direktive identifiziert ein Konstrukt, die Ausführung von einem zugeordneten strukturierten Block auf einen einzelnen Thread zu einem Zeitpunkt beschränkt. Die Syntax der `critical` Richtlinie lautet wie folgt:

```cpp
#pragma omp critical [(name)]  new-linestructured-block
```

Eine optionale *Namen* kann zum Identifizieren des kritischen Bereichs verwendet werden. Bezeichner, die zum Identifizieren von eines kritischen Bereichs verfügen über eine externe Bindung und in einem Namespace, der getrennt von den Namespaces, die von Bezeichnungen, Tags, Mitglieder und wie gewöhnliche Bezeichner verwendet werden.

Ein Thread wartet am Anfang des einem kritischen Bereich, bis kein anderer Thread einen kritischen Bereich (eine beliebige Stelle im Programm), mit dem gleichen Namen ausgeführt wird. Alle unbenannten `critical` Anweisungen in den nicht angegebenen Namen zugeordnet.

### <a name="263-barrier-directive"></a>2.6.3 Barrier-Direktive

Die `barrier` Richtlinie synchronisiert alle Threads in einem Team. Wenn gefunden, wartet jeden Thread im Team, das, bis alle anderen dieser Punkt erreicht haben. Die Syntax der `barrier` Richtlinie lautet wie folgt:

```cpp
#pragma omp barrier new-line
```

Nachdem alle Threads in das Team die Barriere aufgetreten ist, beginnt jeder Thread im Team, das die Anweisungen nach der Barrier-Direktive parallel ausgeführt. Da die `barrier` Richtlinie kein sprachanweisung "C" als Teil der Syntax, es gibt einige Einschränkungen für die Platzierung innerhalb eines Programms. Weitere Informationen über die formale Grammatik finden Sie unter [Anhang C](c-openmp-c-and-cpp-grammar.md). Das folgende Beispiel veranschaulicht diese Einschränkungen.

```cpp
/* ERROR - The barrier directive cannot be the immediate
*          substatement of an if statement
*/
if (x!=0)
   #pragma omp barrier
...

/* OK - The barrier directive is enclosed in a
*      compound statement.
*/
if (x!=0) {
   #pragma omp barrier
}
```

### <a name="264-atomic-construct"></a>2.6.4 atomic-Konstrukt

Die `atomic` Richtlinie stellt sicher, dass eine bestimmte Speicheradresse atomar aktualisiert wird, anstatt eine Offenlegung für die Möglichkeit, mehrere gleichzeitige Threads zu schreiben. Die Syntax der `atomic` Richtlinie lautet wie folgt:

```cpp
#pragma omp atomic new-lineexpression-stmt
```

Die Ausdrucksanweisung muss es sich um einen der folgenden Formate aufweisen:

- *x binop* `=` *expr*
- *x* `++`
- `++` *x*
- *x* `--`
- `--` *x*

In den vorherigen Ausdrücken:

- *X* ist ein l-Wert-Ausdruck mit skalaren Typ.

- *Expr* ist ein Ausdruck mit skalaren Typ, und sie nicht das Objekt vom angegebenen verweisen *x*.

- *Binop* nicht ist ein überladener Operator, und ist einer der `+`, `*`, `-`, `/`, `&`, `^`, `|`, `<<`, oder `>>`.

Obwohl es Implementierung definiert ist, gibt an, ob eine Implementierung ersetzt alle `atomic` Direktiven mit `critical` Direktiven, die die gleiche eindeutige *Namen*, `atomic` Richtlinie ermöglicht bessere Optimierung . Häufig Hardware-Anweisungen stehen zur Verfügung, das unteilbare Update mit den geringsten Aufwand ausführen kann.

Nur das Laden und den Speicher für das Objekt vom angegebenen *x* atomar sind; die Auswertung von *Expr* nicht atomisch. Um Racebedingungen zu vermeiden, alle Updates des Speicherorts parallel geschützt werden sollte, mit der `atomic` Direktive, mit Ausnahme derjenigen, die bekannt ist, dass Racebedingungen kostenlos zur Verfügung gestellt.

Einschränkungen für die `atomic` Richtlinie lauten wie folgt:

- Alle atomic Verweise auf den Speicherort X in der gesamten Anwendung muss einen kompatiblen Typ sein.

#### <a name="examples"></a>Beispiele

```cpp
extern float a[], *p = a, b;
/* Protect against races among multiple updates. */
#pragma omp atomic
a[index[i]] += b;
/* Protect against races with updates through a. */
#pragma omp atomic
p[i] -= 1.0f;

extern union {int n; float x;} u;
/* ERROR - References through incompatible types. */
#pragma omp atomic
u.n++;
#pragma omp atomic
u.x -= 1.0f;
```

### <a name="265-flush-directive"></a>2.6.5 flush-Direktive

Die `flush` -Direktive, ob die explizite oder implizite Gewährleistung aus, gibt einen "threadübergreifende" Sequenzpunkt, der an dem die Implementierung erforderlich, um sicherzustellen, dass alle Threads in einem Team eine konsistente Sicht der bestimmte Objekte (unten angegeben) im Arbeitsspeicher verfügen. Dies bedeutet, dass die vorherige auswertungen von Ausdrücken, die auf diese Objekte verweisen, die abgeschlossen sind und noch nicht nachfolgende auswertungen angefangen haben. Z. B. Compiler müssen die Werte der Objekte von Registern wiederherstellen, auf den Speicher und Hardware möglicherweise leeren Puffer schreiben, in den Speicher und die Werte der Objekte aus dem Speicher erneut zu laden.

Die Syntax der `flush` Richtlinie lautet wie folgt:

```cpp
#pragma omp flush [(variable-list)]  new-line
```

Wenn die Objekte, die Synchronisierung erfordern können alle Variablen festgelegt werden, können diese Variablen angegeben werden, in der optionalen *Variablenliste*. Wenn ein Zeiger in vorhanden ist. die *Variablenliste*, wird der Zeiger selbst geleert, nicht das Objekt der Zeiger verweist auf.

Ein `flush` Direktive ohne eine *Variablenliste* aller freigegebenen Objekte mit Ausnahme der Objekte mit automatischer Speicherdauer synchronisiert. (Dies ist wahrscheinlich einen höheren Aufwand als ein `flush` mit einem *Variablenliste*.) Ein `flush` Direktive ohne eine *Variablenliste* wird implizit für die folgenden Anweisungen:

- `barrier`
- Am Eingang und das Ende von `critical`
- Am Eingang und das Ende von `ordered`
- Am Eingang und das Ende von `parallel`
- Beim Beenden von `for`
- Beim Beenden von `sections`
- Beim Beenden von `single`
- Am Eingang und das Ende von `parallel for`
- Am Eingang und das Ende von `parallel sections`

Die Richtlinie ist nicht impliziert, wenn eine `nowait` -Klausel vorhanden ist. Beachten Sie, die die `flush` Richtlinie wird nicht implizit für eine der folgenden:

- Klicken Sie auf einen Eintrag in `for`
- Auf einen Eintrag in "oder" Beenden `master`
- Klicken Sie auf einen Eintrag in `sections`
- Klicken Sie auf einen Eintrag in `single`

Ein Verweis, der den Wert eines Objekts mit einem Volatile-qualified-Typ greift auf verhält, als wäre es ein `flush` Richtlinie, die das Objekt am vorherigen Sequenzpunkt angeben. Ein Verweis, der den Wert eines Objekts mit einem Volatile-qualified-Typ ändert, verhält sich, als wäre es ein `flush` Richtlinie, die dieses Objekt die nachfolgende Folge Zeitpunkt angeben.

Da die `flush` Richtlinie kein sprachanweisung "C" als Teil der Syntax, es gibt einige Einschränkungen für die Platzierung innerhalb eines Programms. Weitere Informationen über die formale Grammatik finden Sie unter [Anhang C](c-openmp-c-and-cpp-grammar.md). Das folgende Beispiel veranschaulicht diese Einschränkungen.

```cpp
/* ERROR - The flush directive cannot be the immediate
*          substatement of an if statement.
*/
if (x!=0)
   #pragma omp flush (x)
...

/* OK - The flush directive is enclosed in a
*      compound statement
*/
if (x!=0) {
   #pragma omp flush (x)
}
```

Einschränkungen für die `flush` Richtlinie lauten wie folgt:

- Eine Variable, die im angegebenen ein `flush` Richtlinie darf keinen Verweistyp handelt.

### <a name="266-ordered-construct"></a>2.6.6 sortierten Konstrukt

Die folgenden vor einem strukturierten Block ein `ordered` Richtlinie ausgeführt wird, in der Reihenfolge, in denen Iterationen in einer sequenziellen Schleife ausgeführt. Die Syntax der `ordered` Richtlinie lautet wie folgt:

```cpp
#pragma omp ordered new-linestructured-block
```

Ein `ordered` Richtlinie im dynamischen Wertebereich liegen eine `for` oder `parallel for` zu erstellen. Die `for` oder `parallel for` , der die Richtlinie der `ordered` Konstrukt Bindungen müssen einen `ordered` -Klausel angegeben, wie in beschrieben [Abschnitt 2.4.1](#241-for-construct). Bei der Ausführung eine `for` oder `parallel for` erstellen Sie mit einer `ordered` -Klausel `ordered` Konstrukte unbedingt ausgeführt werden, in der Reihenfolge, in dem sie in eine sequenzielle Ausführung der Schleife ausgeführt werden würde.

Einschränkungen für die `ordered` Richtlinie lauten wie folgt:

- Eine Iteration einer Schleife mit einem `for` Konstrukt muss nicht die gleiche ordered-Direktive mehr als einmal ausgeführt, und er nicht ausgeführt werden muss mehr als eine `ordered` Richtlinie.

## <a name="27-data-environment"></a>2.7 datenumgebung

In diesem Abschnitt wird eine Richtlinie und mehrere Klauseln zum Steuern der datenumgebung während der Ausführung von parallelen Bereichen wie folgt:

- Ein [Threadprivate](#271-threadprivate-directive) Richtlinie wird bereitgestellt, um für einen Thread Dateigültigkeitsbereichs-, -Namespace-Gültigkeitsbereich oder Blockbereiche mit statischen Variablen lokalen machen.

- Klauseln, die auf die Direktiven zum Steuern der Freigabe Attribute von Variablen für die Dauer der parallelen oder Freigabe von Arbeit Konstrukte angegeben werden können, werden in beschrieben [Abschnitt 2.7.2](#272-data-sharing-attribute-clauses).

### <a name="271-threadprivate-directive"></a>2.7.1 Threadprivate-Direktive

Die `threadprivate` Direktive macht der benannten Datei-Bereich, Namespace-Gültigkeitsbereich oder Blockbereiche mit statischen Variablen in der *Variablenliste* einem Thread zugehörig. *Variablenliste* ist eine durch Trennzeichen getrennte Liste von Variablen, die einen unvollständigen Typ besitzen. Die Syntax der `threadprivate` Richtlinie lautet wie folgt:

```cpp
#pragma omp threadprivate(variable-list) new-line
```

Jeder Kopie eine `threadprivate` Variable initialisiert wird einmal an einem nicht angegebenen Punkt im Programm vor dem ersten Verweis auf diese Kopie, und klicken Sie auf die übliche Weise (d. h., wie die Masterkopie in einer seriellen Ausführung des Programms initialisiert werden würde). Beachten Sie, dass ein Objekt verwiesen wird, in eine explizite Initialisierung von einer `threadprivate` Variablen und der Wert des Objekts vor dem ersten Verweis auf eine Kopie der Variable geändert wird, dann ist das Verhalten undefiniert.

Wie mit eine private Variable, ein Thread nicht ein anderer Thread Kopie verweisen muss eine `threadprivate` Objekt. Bei der seriellen Bereichen und masterregionen des Programms werden die Verweise auf die master-Thread-Kopie des Objekts.

Nachdem die erste Region für die parallele ausgeführt wird, die Daten in die `threadprivate` ist gewährleistet, dass Objekte beibehalten werden, nur wenn threads von dynamischen Mechanismus deaktiviert wurde, und wenn die Anzahl der Threads für alle parallelen Bereichen unverändert bleibt.

Die Einschränkungen fest, die `threadprivate` Richtlinie lauten wie folgt:

- Ein `threadprivate` Richtlinie für Datei-Gültigkeitsbereich oder im Namespace-Gültigkeitsbereich von Variablen muss außerhalb beliebige Definition oder Deklaration angezeigt werden, und alle Verweise auf Variablen in der Liste muss lexikalisch vorangestellt sein.

- Jede Variable in der *Variablenliste* von einer `threadprivate` Richtlinie auf Datei- oder Namespacebereich muss die Deklaration einer Variablen auf Datei- oder Namespacebereich, der die Direktive lexikalisch vorausgeht finden Sie unter.

- Ein `threadprivate` Richtlinie für Blockbereiche mit statischen Variablen muss im Gültigkeitsbereich der Variablen und nicht in einem geschachtelten Bereich angezeigt werden. Die Richtlinie muss lexikalisch alle Verweise auf Variablen in der Liste der vorangestellt sein.

- Jede Variable in der *Variablenliste* von eine `threadprivate` Richtlinie im Blockbereich muss auf eine Variablendeklaration im gleichen Bereich, der die Direktive lexikalisch vorausgeht verweisen. Die Deklaration von Variable muss den static-Speicherklassenspezifizierer verwenden.

- Wenn eine Variable, in angegeben wird eine `threadprivate` -Direktive in einer Übersetzungseinheit, es muss angegeben werden eine `threadprivate` -Direktive in jeder Übersetzungseinheit, die in der sie deklariert ist.

- Ein `threadprivate` Variable darf nicht in jeder Klausel nur erscheinen die `copyin`, `copyprivate`, `schedule`, `num_threads`, oder die `if` Klausel.

- Die Adresse einer `threadprivate` Variable ist eine adresskonstante nicht.

- Ein `threadprivate` Variable darf keinen, einen unvollständigen Typ oder ein Verweistyp.

- Ein `threadprivate` Variablen keine POD-Klassentyp muss eine erreichbare, eindeutige Kopierkonstruktor verfügen, wenn er mit einem expliziten Initialisierer deklariert wird.

Im folgende Beispiel wird veranschaulicht, wie ändern eine Variable, die in einer Initialisierung wird angezeigt, nicht definiertes Verhalten verursachen kann, und wie dieses Problem zu vermeiden, indem Sie ein zusätzliches Objekt und einen Kopierkonstruktor.

```cpp
int x = 1;
T a(x);
const T b_aux(x); /* Capture value of x = 1 */
T b(b_aux);
#pragma omp threadprivate(a, b)

void f(int n) {
   x++;
   #pragma omp parallel for
   /* In each thread:
   * Object a is constructed from x (with value 1 or 2?)
   * Object b is copy-constructed from b_aux
   */
   for (int i=0; i<n; i++) {
      g(a, b); /* Value of a is unspecified. */
   }
}
```

#### <a name="cross-references"></a>Querverweise

- [Dynamische threads](3-run-time-library-functions.md#317-omp_set_dynamic-function)
- [OMP_DYNAMIC](4-environment-variables.md#43-omp_dynamic) -Umgebungsvariable

### <a name="272-data-sharing-attribute-clauses"></a>2.7.2 Datenfreigabe-attributklauseln

Mehrere Direktiven akzeptieren-Klauseln, die einem Benutzer ermöglichen, die gemeinsame Nutzung Attribute von Variablen für die Dauer des Bereichs zu steuern. Freigabe Attribut Klauseln gelten nur für Variablen im lexikalischen Block der Richtlinie auf dem die Klausel wird angezeigt. Nicht alle der folgenden Klauseln sind für alle Anweisungen zulässig. Die Liste der Klauseln, die für eine bestimmte Richtlinie gültig sind, werden mit der Direktive beschrieben.

Wenn eine Variable ist sichtbar, wenn eine parallele oder Arbeit-sharing-Konstrukt festgestellt wird, und die Variable nicht in einer Freigabe Attribut-Klausel angegeben ist oder `threadprivate` die Richtlinie, klicken Sie dann die Variable wird freigegeben. Statische Variablen, die innerhalb der dynamischen Wertebereich eines parallelen Bereichs deklariert werden, gemeinsam genutzt. Heap zugewiesenen Speicher (z. B. `malloc()` in C oder C++ oder `new` -Operator in C++) freigegeben wird. (Der Zeiger an den Arbeitsspeicher, kann jedoch jedoch entweder privat oder freigegeben sein.) Variablen mit automatischer Speicherdauer innerhalb der dynamischen Wertebereich eines parallelen Bereichs deklariert sind privat.

Die meisten Klauseln akzeptieren einen *Variablenliste* Argument, das eine durch Trennzeichen getrennte Liste von Variablen ist, die angezeigt werden. Wenn eine Variable in verwiesen Datenfreigabeklausel im Attribut weist einen Typ, der aus einer Vorlage abgeleitet und es keine weiteren Verweise auf diese Variable im Programm, das Verhalten nicht definiert ist.

Alle Variablen, die in Direktivenklauseln angezeigt werden, müssen sichtbar sein. Klauseln nach Bedarf wiederholt werden können, aber keine Variable kann in mehr als eine Klausel angegeben werden, außer dass eine Variable in beiden angegeben werden, kann eine `firstprivate` und `lastprivate` Klausel.

Die folgenden Abschnitte beschreiben die Klauseln für die Datenfreigabe-Attribut:

- [private](#2721-private)
- [firstprivate](#2722-firstprivate)
- [lastprivate](#2723-lastprivate)
- [shared](#2724-shared)
- [default](#2725-default)
- [reduction](#2726-reduction)
- [copyin](#2727-copyin)
- [copyprivate](#2728-copyprivate)

#### <a name="2721-private"></a>2.7.2.1 private

Die `private` -Klausel deklariert, die Variablen im Variable-Liste für jeden Thread in einem Team privat sein. Die Syntax der `private` -Klausel ist wie folgt:

```cpp
private(variable-list)
```

Das Verhalten einer Variablen angegeben, die einem `private` -Klausel ist wie folgt. Für das Konstrukt wird ein neues Objekt mit automatischer Speicherdauer zugeordnet. Die Größe und Ausrichtung des neuen Objekts werden durch den Typ der Variablen bestimmt. Die Reservierung erfolgt einmal für jeden Thread im Team, und ein Standardkonstruktor wird aufgerufen, für ein Klassenobjekt bei Bedarf; Andernfalls ist der Anfangswert unbestimmt.  Das ursprüngliche Objekt, das die Variable verweist hat einen unbestimmten Wert beim Einstieg in das Konstrukt, darf nicht geändert werden, in der dynamischen Wertebereich des Konstrukts und verfügt über einen unbestimmten Wert nach dem Verlassen des Konstrukts.

Im lexikalischen Block des Konstrukts die Richtlinie verweist die Variable die neue private-Objekt, die vom Thread zugeordnet.

Die Einschränkungen fest, die `private` Klausel lauten wie folgt:

- Eine Variable mit einem Klassentyp, der im angegebenen ein `private` Klausel muss einen erreichbare, eindeutige Standardkonstruktor verfügen.

- Eine Variable, die im angegebenen ein `private` Klausel darf keine `const`-Typ qualifiziert, es sei denn, sie eine Klasse, und geben Sie einen `mutable` Member.

- Eine Variable, die im angegebenen ein `private` Klausel darf keinen, einen unvollständigen Typ oder ein Verweistyp.

- Variablen in der `reduction` -Klausel eine `parallel` Richtlinie kann nicht angegeben werden, einem `private` -Klausel für eine arbeitsteilungsanweisung, die an das parallele Konstrukt gebunden wird.

#### <a name="2722-firstprivate"></a>2.7.2.2 firstprivate

Die `firstprivate` -Klausel bietet eine Obermenge von der Funktionalität der `private` Klausel. Die Syntax der `firstprivate` -Klausel ist wie folgt:

```cpp
firstprivate(variable-list)
```

Variablen in *Variablenliste* haben `private` Klausel-Semantik, wie in beschrieben [Abschnitt 2.7.2.1](#2721-private). Die Initialisierung oder Erstellung des geschieht, als ob er einmal pro Thread, vor der Ausführung des Threads, der das Konstrukt ausgeführt wurden. Für eine `firstprivate` -Klausel für eine parallele Konstrukt, der Anfangswert des neuen private-Objekts ist der Wert des ursprünglichen Objekts, das unmittelbar vor das parallele Konstrukt für den Thread vorhanden ist, die es trifft. Für eine `firstprivate` -Klausel für ein Freigeben von Arbeitsaufgaben-Konstrukt, der Anfangswert des neuen Objekts private für jeden Thread, der die gemeinsame Verwendung von Arbeit Konstrukt ausgeführt wird. ist der Wert des ursprünglichen Objekts, das vor dem Zeitpunkt vorhanden ist, dass es sich bei dem gefundenen thread die Freigeben von Arbeitsaufgaben erstellen. Darüber hinaus wird für C++-Objekte, das neue private Objekt für jeden Thread Kopie aus dem ursprünglichen Objekt erstellt ist.

Die Einschränkungen fest, die `firstprivate` Klausel lauten wie folgt:

- Eine Variable, die im angegebenen ein `firstprivate` Klausel darf keinen, einen unvollständigen Typ oder ein Verweistyp.

- Eine Variable mit einem Klassentyp, der als angegeben wird `firstprivate` benötigen eine erreichbare, eindeutige Kopierkonstruktor.

- Variablen, die innerhalb eines parallelen Bereichs privat sind, bzw. die angezeigt werden, in, der `reduction` -Klausel einer `parallel` Richtlinie kann nicht angegeben werden, eine `firstprivate` -Klausel für eine arbeitsteilungsanweisung, die an das parallele Konstrukt gebunden wird.

#### <a name="2723-lastprivate"></a>2.7.2.3 lastprivate

Die `lastprivate` -Klausel bietet eine Obermenge von der Funktionalität der `private` Klausel. Die Syntax der `lastprivate` -Klausel ist wie folgt:

```cpp
lastprivate(variable-list)
```

Variablen in der *Variablenliste* haben `private` Klausel-Semantik. Wenn eine `lastprivate` -Klausel wird angezeigt, auf die Richtlinie, die eine gemeinsame Verwendung von Arbeit Konstrukt, den Wert für jeden identifiziert `lastprivate` Variable von der sequenziell letzte Iteration der Schleife zugeordnet ist, oder die lexikalisch letzten abschnittsdirektive, zugewiesen wird die Ursprüngliches Objekt der Variablen. Variablen, die von der letzten Iteration ein Wert zugewiesen werden nicht die `for` oder `parallel for`, oder durch den lexikalisch letzten Abschnitt des der `sections` oder `parallel sections` -Direktive haben unbestimmte Werte nach der Erstellung. Nicht zugewiesene Unterobjekte haben auch einen unbestimmten Wert nach der Erstellung.

Die Einschränkungen fest, die `lastprivate` Klausel lauten wie folgt:

- Alle Einschränkungen für `private` anwenden.

- Eine Variable mit einem Klassentyp, der als angegeben wird `lastprivate` muss eine erreichbare, eindeutige Kopierzuweisungsoperator verfügen.

- Variablen, die innerhalb eines parallelen Bereichs privat sind, bzw. die angezeigt werden, in, der `reduction` -Klausel einer `parallel` Richtlinie kann nicht angegeben werden, eine `lastprivate` -Klausel für eine arbeitsteilungsanweisung, die an das parallele Konstrukt gebunden wird.

#### <a name="2724-shared"></a>2.7.2.4 shared

Diese Klausel teilt Variablen in der *Variablenliste* auf allen Threads in einem Team. Alle Threads in einem Team Zugriff auf denselben Speicherbereich für `shared` Variablen.

Die Syntax der `shared` -Klausel ist wie folgt:

```cpp
shared(variable-list)
```

#### <a name="2725-default"></a>2.7.2.5 default

Die `default` Klausel ermöglicht dem Benutzer, die Datenfreigabe-Attribute von Variablen beeinflussen. Die Syntax der `default` -Klausel ist wie folgt:

```cpp
default(shared | none)
```

Angeben `default(shared)` ist gleichbedeutend mit einzelnen aktuell sichtbare Variablen im explizit Auflisten einer `shared` -Klausel, es sei denn, es ist `threadprivate` oder `const`-qualifizierten. In Abwesenheit einer expliziten `default` -Klausel, das Standardverhalten ist identisch mit If `default(shared)` wurden angegeben.

Angeben von `default(none)` erfordert, dass mindestens eine der folgenden für jeden Verweis auf eine Variable in der lexikalischen Wertebereich das parallele Konstrukt "true" sein muss:

- Die Variable wird explizit in einem Attribut Datenfreigabeklausel eines Konstrukts aufgeführt, die den Verweis enthält.

- Die Variable wird in das parallele Konstrukt deklariert.

- Die Variable ist `threadprivate`.

- Die Variable hat einen `const`-qualifizierten Typ.

- Die Variable ist die Schleifensteuerungsvariable für eine `for` Schleife, die unmittelbar folgt einem `for` oder `parallel for` Richtlinie, und den Variablen Verweis, die innerhalb der Schleife wird angezeigt.

Gibt eine Variable auf einen `firstprivate`, `lastprivate`, oder `reduction` -Klausel von einer eingeschlossenen-Direktive verwenden, einen impliziten Verweis auf die Variable im umschließenden Kontext. Solche impliziten verweisen, sind auch gemäß den oben aufgeführten Anforderungen.

Nur eine einzige `default` -Klausel angegeben werden kann, auf eine `parallel` Richtlinie.

Eine Variable des Standard-Datenfreigabe-Attribut werden, indem überschrieben kann die `private`, `firstprivate`, `lastprivate`, `reduction`, und `shared` -Klauseln, wie im folgenden Beispiel gezeigt:

```cpp
#pragma  omp  parallel  for  default(shared)  firstprivate(i)\
   private(x)  private(r)  lastprivate(i)
```

#### <a name="2726-reduction"></a>2.7.2.6 reduction

Diese Klausel führt eine Reduzierung der skalaren Variablen in *Variablenliste*, mit dem Operator *Op*. Die Syntax der `reduction` -Klausel ist wie folgt:

`reduction(` *op* `:` *variable-list* `)`

Eine Reduzierung wird in der Regel für eine Anweisung mit einem der folgenden Formate angegeben werden:

- *x* `=` *x* *op* *expr*
- *x* *binop* `=` *expr*
- *X* `=` *Expr* *Op* *x* (mit Ausnahme der Subtraktion)
- *x* `++`
- `++` *x*
- *x* `--`
- `--` *x*

Dabei gilt:

*w*<br/>
Einer der Reduction-Variablen, die in der Liste angegeben.

*variable-list*<br/>
Eine durch Trennzeichen getrennte Liste von skalaren Reduction-Variablen.

*expr*<br/>
Ein Ausdruck mit skalaren Typ, der nicht auf *x*.

*op*<br/>
Keines überladenen Operators, aber einer der `+`, `*`, `-`, `&`, `^`, `|`, `&&`, oder `||`.

*binop*<br/>
Keines überladenen Operators, aber einer der `+`, `*`, `-`, `&`, `^`, oder `|`.

Folgendes ist ein Beispiel für die `reduction` Klausel:

```cpp
#pragma omp parallel for reduction(+: a, y) reduction(||: am)
for (i=0; i<n; i++) {
   a += b[i];
   y = sum(y, c[i]);
   am = am || b[i] == c[i];
}
```

Wie im Beispiel gezeigt wird, kann ein Operator in einem Funktionsaufruf ausgeblendet werden. Der Benutzer sollte Achten Sie darauf, dass der Operator, in angegeben der `reduction` Klausel entspricht den Reduction-Vorgang.

Obwohl der Rechte Operand des der `||` Operator hat keine Nebenwirkungen in diesem Beispiel, sie sind zulässig, jedoch sollte mit Vorsicht verwendet werden. In diesem Kontext kann ein Nebeneffekt auslösen, der mit Sicherheit wurde nicht während der sequenziellen Ausführung der Schleife auftreten, während der parallelen Ausführung auftreten. Dieser Unterschied kann auftreten, da die Reihenfolge der Ausführung der Iterationen unbestimmt ist.

Der Operator wird den Anfangswert des vom Compiler verwendet wird, für die Verringerung der privaten Variablen zu bestimmen und um zu bestimmen, den Finalization-Operator verwendet werden. Explizites Angeben des Operators kann die Verringerung der Anweisung außerhalb der lexikalischen Umfang des Konstrukts. Eine beliebige Anzahl von `reduction` Klauseln können für die Direktive angegeben werden, aber eine Variable darf in nur einer `reduction` -Klausel für diese Anweisung.

Eine private Kopie der einzelnen Variablen im *Variablenliste* erstellt wird – einer für die einzelnen Threads, als ob die `private` Klausel verwendet worden. Die private Kopie gemäß dem Operator initialisiert wird (siehe die folgende Tabelle).

Am Ende des Bereichs für die die `reduction` -Klausel angegeben wurde, das ursprüngliche Objekt wird aktualisiert, und das Ergebnis der Kombination von des ursprünglichen Wert mit der endgültige Wert der jeder die private Kopien, die mithilfe des angegebenen Operators an. Die Verringerung der Operatoren sind alle assoziative (mit Ausnahme der Subtraktion), und der Compiler kann frei erneut zugeordnet werden, der Berechnung des endgültigen Werts. (Die partielle Ergebnisse einer Verringerung der Subtraktion werden hinzugefügt, um den endgültigen Wert zu erstellen.)

Der Wert des ursprünglichen Objekts wird unbestimmt, wenn der erste Thread die Klausel enthält erreicht, und so bleibt, bis die Verringerung der Berechnung abgeschlossen ist.  In der Regel wird die Berechnung abgeschlossen ist, am Ende des Konstrukts sein; aber wenn die `reduction` -Klausel wird verwendet, für ein Konstrukt, `nowait` ist auch angewendet, der Wert des ursprünglichen Objekts bleibt unbestimmten bis eine Barriere Synchronisierung durchgeführt wurde, um sicherzustellen, dass alle Threads den abgeschlossensind`reduction`Klausel.

Die folgende Tabelle enthält die Operatoren, die gültig sind und ihre kanonischen Initialisierungswerte. Der Wert für die eigentliche Initialisierung wird mit dem Datentyp der Reduction-Variable konsistent sein.

|Operator|Initialisierung|
|--------------|--------------------|
|`+`|0|
|`*`|1|
|`-`|0|
|`&`|~0|
|`|`|0|
|`^`|0|
|`&&`|1|
|`||`|0|

Die Einschränkungen fest, die `reduction` Klausel lauten wie folgt:

- Der Typ der Variablen in der `reduction` Klausel muss für die Reduction-Operator gültig sein, außer dass Zeiger und Verweistypen nicht zulässig sind.

- Eine Variable, die im angegebenen die `reduction` Klausel darf nicht sein `const`-qualifizierten.

- Variablen, die innerhalb eines parallelen Bereichs privat sind, bzw. die angezeigt werden, in, der `reduction` -Klausel einer `parallel` Richtlinie kann nicht angegeben werden, eine `reduction` -Klausel für eine arbeitsteilungsanweisung, die an das parallele Konstrukt gebunden wird.

   ```cpp
   #pragma omp parallel private(y)
   { /* ERROR - private variable y cannot be specified
                in a reduction clause */
      #pragma omp for reduction(+: y)
      for (i=0; i<n; i++)
         y += b[i];
   }

   /* ERROR - variable x cannot be specified in both
              a shared and a reduction clause */
   #pragma omp parallel for shared(x) reduction(+: x)
   ```

#### <a name="2727-copyin"></a>2.7.2.7 copyin

Die `copyin` -Klausel bietet einen Mechanismus, um den gleichen Wert zuweisen `threadprivate` Variablen für jeden Thread im Team, das Ausführen des parallelen Bereichs. Für jede Variable, die im angegebenen ein `copyin` -Klausel, die den Wert der Variablen in der master-Thread des Teams kopiert wurde, als ob durch eine Zuweisung der privaten Kopien am Anfang des parallelen Bereichs. Die Syntax der `copyin` -Klausel ist wie folgt:

```cpp

copyin(
variable-list
)
```

Die Einschränkungen fest, die `copyin` Klausel lauten wie folgt:

- Eine Variable, die im angegebenen die `copyin` -Klausel muss eine erreichbare, eindeutige Kopierzuweisungsoperator aufweisen.

- Eine Variable, die im angegebenen die `copyin` Klausel muss ein `threadprivate` Variable.

#### <a name="2728-copyprivate"></a>2.7.2.8 copyprivate

Die `copyprivate` -Klausel bietet einen Mechanismus, um eine private Variable zu verwenden, um einen Wert von einem Mitglied eines Teams an den anderen Elementen zu übertragen. Es ist eine Alternative zur Verwendung von einer freigegebenen Variable für den Wert, wenn diese eine freigegebene Variable bereitstellen (z. B. in eine Rekursion, erfordern eine andere Variable auf jeder Ebene) schwierig wäre. Die `copyprivate` Klausel kann nur verwendet werden, auf die `single` Richtlinie.

Die Syntax der `copyprivate` -Klausel ist wie folgt:

```cpp

copyprivate(
variable-list
)
```

Die Auswirkungen der `copyprivate` -Klausel für die Variablen in die Variablenliste tritt ein, nach der Ausführung von einem strukturierten Block zugeordnete der `single` zu erstellen, und vor Threads im Team, das die Grenze am Ende des Konstrukts verlassen haben. Klicken Sie auf alle anderen Threads im Team für jede Variable im der *Variablenliste*, diese Variable wird (wie durch Zuweisung) definiert, mit dem Wert der entsprechenden Variable in der der Thread, der das Konstrukt ausgeführt des strukturiert. Block.

Einschränkungen für die `copyprivate` Klausel lauten wie folgt:

- Eine Variable, die im angegebenen der `copyprivate` Klausel darf nicht erscheinen, einem `private` oder `firstprivate` Klausel für den gleichen `single` Richtlinie.

- Wenn eine `single` -Direktive zusammen mit einem `copyprivate` Klausel in der dynamischen Wertebereich eines parallelen Bereichs festgestellt wird, alle Variablen, die im angegebenen die `copyprivate` Klausel muss im umschließenden Kontext privat sein.

- Eine Variable, die im angegebenen die `copyprivate` -Klausel muss ein zugänglich eindeutig Kopierzuweisungsoperator aufweisen.

## <a name="28-directive-binding"></a>2.8 direktivenbindung

Dynamische Bindung von Direktiven, muss die folgenden Regeln einhalten:

- Die `for`, `sections`, `single`, `master`, und `barrier` Direktiven binden, die dynamisch einschließende `parallel`, sofern eine vorhanden, unabhängig vom Wert eines beliebigen ist `if` -Klausel, die auf diesem vorhanden sein kann Direktive. Wenn keine parallelen Bereichs derzeit ausgeführt wird, werden die Anweisungen von einem Team besteht aus nur die master-Thread ausgeführt.

- Die `ordered` Richtlinie gebunden wird, die dynamisch einschließende `for`.

- Die `atomic` Richtlinie gewährt exklusiven Zugriff in Bezug auf `atomic` Direktiven in allen Threads, nicht nur das aktuelle Teamprojekt.

- Die `critical` Richtlinie gewährt exklusiven Zugriff in Bezug auf `critical` Direktiven in allen Threads, nicht nur das aktuelle Teamprojekt.

- Eine Anweisung kann nie dynamisch für jede Anweisung außerhalb der nächsten binden einschließenden `parallel`.

## <a name="29-directive-nesting"></a>2.9 Schachtelung von

Dynamische Schachtelung von Anweisungen muss die folgenden Regeln beachtet werden:

- Ein `parallel` dynamisch in einer anderen Richtlinie `parallel` logisch richtet ein neues Team, das nur den aktuellen Thread besteht, es sei denn, die Parallelität geschachtelt ist aktiviert.

- `for`, `sections`, und `single` Direktiven, die auf die gleiche Bindung `parallel` dürfen nicht ineinander geschachtelt werden.

- `critical` Anweisungen mit dem gleichen Namen dürfen nicht ineinander geschachtelt werden. Beachten Sie, dass diese Einschränkung nicht ausreicht, um Deadlocks zu vermeiden.

- `for`, `sections`, und `single` Anweisungen sind nicht zulässig, in der dynamischen Wertebereich `critical`, `ordered`, und `master` Regionen aus, wenn die Anweisungen auf die gleiche Bindung `parallel` als Regionen.

- `barrier` Anweisungen sind nicht zulässig, in der dynamischen Wertebereich `for`, `ordered`, `sections`, `single`, `master`, und `critical` Regionen aus, wenn die Anweisungen auf die gleiche Bindung `parallel` als Regionen.

- `master` Anweisungen sind nicht zulässig, in der dynamischen Wertebereich `for`, `sections`, und `single` Direktiven Wenn die `master` Anweisungen zu binden, auf die gleiche `parallel` als die gemeinsame Verwendung von Work-Anweisungen.

- `ordered` Anweisungen sind nicht zulässig, in der dynamischen Wertebereich `critical` Regionen aus, wenn die Anweisungen auf die gleiche Bindung `parallel` als Regionen.

- Jede Richtlinie, die zulässig ist, wenn dynamisch innerhalb eines parallelen Bereichs ausgeführt ist auch zulässig, wenn außerhalb eines parallelen Bereichs ausgeführt. Wenn außerhalb eines parallelen Bereichs von benutzerdefinierten dynamisch ausgeführt wird, wird die Richtlinie von einem Team besteht aus nur die master-Thread ausgeführt.
