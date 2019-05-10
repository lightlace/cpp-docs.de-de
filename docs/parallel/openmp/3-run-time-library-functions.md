---
title: 3. Funktionen der Laufzeitbibliothek
ms.date: 01/17/2019
ms.assetid: b226e512-6822-4cbe-a2ca-74cc2bb7e880
ms.openlocfilehash: 3eb6dc4110145a6c45dbdd772deaee3023e68e9d
ms.sourcegitcommit: 00e26915924869cd7eb3c971a7d0604388abd316
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2019
ms.locfileid: "65525035"
---
# <a name="3-run-time-library-functions"></a>3. Funktionen der Laufzeitbibliothek

Dieser Abschnitt beschreibt die Funktionen für OpenMP-C- und C++-Laufzeitbibliothek. Der Header  **\<comp.h >** deklariert zwei Typen, die mehrere Funktionen, die verwendet werden können, zur Steuerung und die Umgebung für die Ausführung paralleler Abfragen und Sperren von Funktionen, die zum Synchronisieren des Zugriffs auf Daten verwendet werden können.

Der Typ `omp_lock_t` ein Objekttyp ausgedrückt werden können, dass eine Sperre verfügbar ist, oder für den Besitz eines Threads ist eine Sperre. Diese Sperren werden als bezeichnet *einfache Sperren*.

Der Typ `omp_nest_lock_t` ist ein Objekttyp kann darstellt, entweder, dass eine Sperre verfügbar ist oder sowohl die Identität des Threads, die die Sperre besitzt und eine *schachteln Anzahl* (siehe unten). Diese Sperren werden als bezeichnet *schachtelbaren Sperren*.

Die Bibliotheksfunktionen weisen externe Funktionen mit "C"-Verknüpfung.

Die Beschreibungen in diesem Kapitel sind in den folgenden Themen unterteilt:

- [Ausführungsumgebungsfunktionen](#31-execution-environment-functions)
- [Lock-Funktionen](#32-lock-functions)
- [Routinen zur zeitlichen Steuerung](#33-timing-routines)

## <a name="31-execution-environment-functions"></a>3.1 ausführungsumgebungsfunktionen

In diesem Abschnitt beschriebenen Funktionen auswirken, und Überwachen von Threads, Prozessoren und der parallelen Umgebung:

- [omp_set_num_threads](#311-omp_set_num_threads-function)
- [omp_get_num_threads](#312-omp_get_num_threads-function)
- [omp_get_max_threads](#313-omp_get_max_threads-function)
- [omp_get_thread_num](#314-omp_get_thread_num-function)
- [omp_get_num_procs](#315-omp_get_num_procs-function)
- [omp_in_parallel](#316-omp_in_parallel-function)
- [omp_set_dynamic](#317-omp_set_dynamic-function)
- [omp_get_dynamic](#318-omp_get_dynamic-function)
- [omp_set_nested](#319-omp_set_nested-function)
- [omp_get_nested](#3110-omp_get_nested-function)

### <a name="311-omp_set_num_threads-function"></a>3.1.1 Omp_set_num_threads-Funktion

Die `omp_set_num_threads` -Funktion legt fest, die Standardanzahl von Threads an, für die später von parallelen Bereichen verwendet, die angeben, keine `num_threads` Klausel. Es wird folgendes Format verwendet:

```cpp
#include <omp.h>
void omp_set_num_threads(int num_threads);
```

Der Wert des Parameters *Num_threads* muss eine positive ganze Zahl sein. Die Auswirkungen hängt davon ab, ob die dynamische Anpassung der Anzahl der Threads aktiviert ist. Für einen umfassenden Satz von Regeln über die Interaktion zwischen der `omp_set_num_threads` -Funktion und die dynamische Anpassung der Threads finden Sie unter [Abschnitt 2.3](2-directives.md#23-parallel-construct).

Diese Funktion hat die Auswirkungen, die oben beschriebenen, beim Aufrufen durch einen Teil des Programms, in denen die `omp_in_parallel` Funktion gibt 0 (null) zurück. Wenn sie über einen Teil des Programms aufgerufen wird, in denen die `omp_in_parallel` Funktion gibt einen Wert ungleich NULL zurück, das Verhalten dieser Funktion ist nicht definiert.

Dieser Aufruf hat Vorrang vor den `OMP_NUM_THREADS` -Umgebungsvariablen angegeben. Der Standardwert für die Anzahl der Threads, die durch den Aufruf festgelegt werden kann `omp_set_num_threads` oder durch Festlegen der `OMP_NUM_THREADS` Umgebungsvariable kann explizit überschrieben werden, auf einem einzelnen `parallel` -Anweisung durch Angabe der `num_threads` Klausel.

#### <a name="cross-references"></a>Querverweise

- [omp_set_dynamic](#317-omp_set_dynamic-function) function
- [omp_get_dynamic](#318-omp_get_dynamic-function) function
- [OMP_NUM_THREADS](4-environment-variables.md#42-omp_num_threads) -Umgebungsvariable
- [Num_threads](2-directives.md#23-parallel-construct) Klausel

### <a name="312-omp_get_num_threads-function"></a>3.1.2 Omp_get_num_threads-Funktion

Die `omp_get_num_threads` Funktion gibt die Anzahl der Threads derzeit im Team, das Ausführen des parallelen Bereichs, der von dem es aufgerufen wird. Es wird folgendes Format verwendet:

```cpp
#include <omp.h>
int omp_get_num_threads(void);
```

Die `num_threads` -Klausel, die `omp_set_num_threads` -Funktion, und die `OMP_NUM_THREADS` Umgebungsvariable steuern die Anzahl der Threads in einem Team.

Wenn die Anzahl der Threads nicht explizit vom Benutzer festgelegt wurde, ist die Standardeinstellung Implementierung definiert. Diese Funktion für die nächste einschließende bindet `parallel` Richtlinie. Wenn Sie aufgerufen wird, über einen seriellen Teil eines Programms oder eines geschachtelten parallelen Bereichs, das serialisiert wird, gibt diese Funktion 1 zurück.

#### <a name="cross-references"></a>Querverweise

- [OMP_NUM_THREADS](4-environment-variables.md#42-omp_num_threads)
- [num_threads](2-directives.md#23-parallel-construct)
- [parallel](2-directives.md#23-parallel-construct)

### <a name="313-omp_get_max_threads-function"></a>3.1.3 Omp_get_max_threads-Funktion

Die `omp_get_max_threads` Funktionsergebnis ist eine ganze Zahl, die als die Anzahl der Threads mindestens so groß sein, der verwendet wird, um ein Team zu bilden, wenn einem parallelen Bereich ohne garantiert verfügt über eine `num_threads` Klausel würde an dieser Stelle im Code angezeigt werden. Es wird folgendes Format verwendet:

```cpp
#include <omp.h>
int omp_get_max_threads(void);
```

Die folgenden drückt eine untere Grenze aus, auf dem Wert des `omp_get_max_threads`:

```

threads-used-for-next-team
<= omp_get_max_threads
```

Beachten Sie, dass wenn eine andere parallele Region verwendet die `num_threads` -Klausel, um eine bestimmte Anzahl von Threads, die Garantie für die untere Grenze des Ergebnisses der Anforderung `omp_get_max_threads` keine langen enthält.

Die `omp_get_max_threads` Rückgabewert der Funktion zum dynamischen Zuweisen von ausreichend Speicherplatz für alle Threads im Team gebildet werden, auf die nächste parallele Region verwendet werden kann.

#### <a name="cross-references"></a>Querverweise

- [omp_get_num_threads](#312-omp_get_num_threads-function)
- [omp_set_num_threads](#311-omp_set_num_threads-function)
- [omp_set_dynamic](#317-omp_set_dynamic-function)
- [num_threads](2-directives.md#23-parallel-construct)

### <a name="314-omp_get_thread_num-function"></a>3.1.4 Omp_get_thread_num-Funktion

Die `omp_get_thread_num` Funktion gibt die Thread-Anzahl, innerhalb der Teams, die Threads, die Ausführung der Funktion. Die Thread-Anzahl liegt zwischen 0 und `omp_get_num_threads()`-1 (einschließlich). Die master-Thread des Teams ist Thread 0.

Es wird folgendes Format verwendet:

```cpp
#include <omp.h>
int omp_get_thread_num(void);
```

Wenn über eine serielle Region aufgerufen `omp_get_thread_num` gibt 0 zurück. Wenn Sie von innerhalb eines geschachtelten parallelen Bereichs aufgerufen, die serialisiert wird, gibt diese Funktion 0 zurück.

#### <a name="cross-references"></a>Querverweise

- [Omp_get_num_threads](#312-omp_get_num_threads-function) Funktion

### <a name="315-omp_get_num_procs-function"></a>3.1.5 Omp_get_num_procs-Funktion

Die `omp_get_num_procs` Funktion gibt die Anzahl der Prozessoren, die zum Zeitpunkt für die Anwendung verfügbar sind die Funktion wird aufgerufen. Es wird folgendes Format verwendet:

```cpp
#include <omp.h>
int omp_get_num_procs(void);
```

### <a name="316-omp_in_parallel-function"></a>3.1.6 Omp_in_parallel-Funktion

Die `omp_in_parallel` Funktion gibt einen Wert ungleich NULL zurück, wenn sie in der dynamischen Wertebereich, einen parallel ausgeführten parallelen Bereichs aufgerufen wird; andernfalls wird 0 zurückgegeben. Es wird folgendes Format verwendet:

```cpp
#include <omp.h>
int omp_in_parallel(void);
```

Diese Funktion gibt einen Wert ungleich NULL, wenn der erfolgt innerhalb einer Region parallele Ausführung, einschließlich der verschachtelten Bereiche, die serialisiert werden.

### <a name="317-omp_set_dynamic-function"></a>3.1.7 Omp_set_dynamic-Funktion

Die `omp_set_dynamic` Funktion aktiviert oder deaktiviert die dynamische Anpassung der Anzahl der Threads, die für die Ausführung von parallelen Bereichen verfügbar. Es wird folgendes Format verwendet:

```cpp
#include <omp.h>
void omp_set_dynamic(int dynamic_threads);
```

Wenn *Dynamic_threads* ergibt einen Wert ungleich NULL, die Anzahl der Threads, die verwendet werden, für die Ausführung anstehender paralleler Bereichen kann angepasst werden automatisch von der Runtime-Umgebung zur optimalen Verwendung der Systemressourcen. Daher ist die Anzahl der Threads, die vom Benutzer angegebenen die maximale Threadanzahl beträgt. Die Anzahl der Threads im Team, das Ausführen eines parallelen Bereichs bleiben für die Dauer der parallelen Region bestehen und wird gemeldet, indem die `omp_get_num_threads` Funktion.

Wenn *Dynamic_threads* ergibt 0 ist, wird der dynamische Anpassung ist deaktiviert.

Diese Funktion hat die Auswirkungen, die oben beschriebenen, beim Aufrufen durch einen Teil des Programms, in denen die `omp_in_parallel` Funktion gibt 0 (null) zurück. Wenn sie über einen Teil des Programms aufgerufen wird, in denen die `omp_in_parallel` Funktion gibt einen Wert ungleich NULL zurück, das Verhalten dieser Funktion ist nicht definiert.

Ein Aufruf von `omp_set_dynamic` hat Vorrang vor den `OMP_DYNAMIC` -Umgebungsvariablen angegeben.

Der Standardwert für die dynamische Anpassung des Threads wird die Implementierung definiert. Daher sollten Benutzer-Codes, die abhängig von einer bestimmten Anzahl von Threads zur richtigen Ausführung explizit deaktivieren, dynamische Threads. Implementierungen müssen nicht die Möglichkeit bieten, die Anzahl der Threads dynamisch anpassen, aber sie müssen die Schnittstelle für Portabilität auf allen Plattformen unterstützt.

#### <a name="cross-references"></a>Querverweise

- [omp_get_num_threads](#312-omp_get_num_threads-function)
- [OMP_DYNAMIC](4-environment-variables.md#43-omp_dynamic)
- [omp_in_parallel](#316-omp_in_parallel-function)

### <a name="318-omp_get_dynamic-function"></a>3.1.8 Omp_get_dynamic-Funktion

Die `omp_get_dynamic` Funktion gibt einen Wert ungleich NULL zurück, wenn die dynamische Anpassung des Threads ist aktiviert, und andernfalls wird 0 zurückgegeben. Es wird folgendes Format verwendet:

```cpp
#include <omp.h>
int omp_get_dynamic(void);
```

Wenn die dynamische Anpassung der Anzahl der Threads von die Implementierung nicht implementiert wird, gibt diese Funktion immer 0 zurück.

#### <a name="cross-references"></a>Querverweise

- Eine Beschreibung der dynamischen Thread Anpassung, finden Sie unter [Omp_set_dynamic](#317-omp_set_dynamic-function).

### <a name="319-omp_set_nested-function"></a>3.1.9 Omp_set_nested-Funktion

Die `omp_set_nested` Funktion aktiviert oder deaktiviert den geschachtelten Parallelität. Es wird folgendes Format verwendet:

```cpp
#include <omp.h>
void omp_set_nested(int nested);
```

Wenn *geschachtelte* auf 0 (null) und geschachtelten wertet Parallelität deaktiviert ist, dies ist die Standardeinstellung und geschachtelten parallele Bereichen werden serialisiert und von den aktuellen Thread ausgeführt werden. Andernfalls geschachtelte Parallelität aktiviert ist und parallele Bereichen, die geschachtelt sind möglicherweise zusätzliche Threads um geschachtelte Teams zu bilden bereitstellen.

Diese Funktion hat die Auswirkungen, die oben beschriebenen, beim Aufrufen durch einen Teil des Programms, in denen die `omp_in_parallel` Funktion gibt 0 (null) zurück. Wenn sie über einen Teil des Programms aufgerufen wird, in denen die `omp_in_parallel` Funktion gibt einen Wert ungleich NULL zurück, das Verhalten dieser Funktion ist nicht definiert.

Dieser Aufruf hat Vorrang vor den `OMP_NESTED` -Umgebungsvariablen angegeben.

Wenn geschachtelte Parallelität aktiviert ist, wird die Anzahl der Threads, die zum Ausführen von geschachtelten paralleler Bereichen verwendet die Implementierung definiert. Daher dürfen OpenMP konforme Implementierungen geschachtelten parallele Bereichen zu serialisieren, auch wenn geschachtelte Parallelität aktiviert ist.

#### <a name="cross-references"></a>Querverweise

- [OMP_NESTED](4-environment-variables.md#44-omp_nested)
- [omp_in_parallel](#316-omp_in_parallel-function)

### <a name="3110-omp_get_nested-function"></a>3.1.10 Omp_get_nested-Funktion

Die `omp_get_nested` Funktion gibt einen Wert ungleich NULL, wenn die geschachtelten Parallelität aktiviert ist und 0 zurück, wenn er deaktiviert ist. Weitere Informationen zu geschachtelten Parallelität, finden Sie unter [Omp_set_nested](#319-omp_set_nested-function). Es wird folgendes Format verwendet:

```cpp
#include <omp.h>
int omp_get_nested(void);
```

Wenn eine Implementierung nicht geschachtelten Parallelität implementiert, gibt diese Funktion immer 0 zurück.

## <a name="32-lock-functions"></a>3.2 Lock-Funktionen

Die Funktionen, die in diesem Abschnitt beschriebenen bearbeiten, sperren, die für die Synchronisierung verwendet wird.

Für die folgenden Funktionen, die Sperren der Variable muss einen Typ aufweisen `omp_lock_t`. Diese Variable muss nur über diese Funktionen zugegriffen werden. Alle Lock-Funktionen erfordern ein Argument, das einen Zeiger auf hat `omp_lock_t` Typ.

- Die [Omp_init_lock](#321-omp_init_lock-and-omp_init_nest_lock-functions) Funktion initialisiert, eine einfache Sperre.
- Die [Omp_destroy_lock](#322-omp_destroy_lock-and-omp_destroy_nest_lock-functions) -Funktion entfernt eine einfache Sperre.
- Die [Omp_set_lock](#323-omp_set_lock-and-omp_set_nest_lock-functions) Funktion wartet, bis eine einfache Sperre verfügbar ist.
- Die [Omp_unset_lock](#324-omp_unset_lock-and-omp_unset_nest_lock-functions) Funktion gibt eine einfache Sperre frei.
- Die [Omp_test_lock](#325-omp_test_lock-and-omp_test_nest_lock-functions) Funktion testet eine einfache Sperre.

Für die folgenden Funktionen, die Sperren der Variable muss einen Typ aufweisen `omp_nest_lock_t`.  Diese Variable muss nur über diese Funktionen zugegriffen werden. Alle Funktionen der omp_nest_lock_t-Sperre erfordern ein Argument, das ist einen Zeiger auf `omp_nest_lock_t` Typ.

- Die [Omp_init_nest_lock](#321-omp_init_lock-and-omp_init_nest_lock-functions) Funktion initialisiert den omp_nest_lock_t-Sperre.
- Die [Omp_destroy_nest_lock](#322-omp_destroy_lock-and-omp_destroy_nest_lock-functions) -Funktion entfernt eine omp_nest_lock_t-Sperre.
- Die [Omp_set_nest_lock](#323-omp_set_lock-and-omp_set_nest_lock-functions) Funktion wartet, bis eine omp_nest_lock_t-Sperre verfügbar ist.
- Die [Omp_unset_nest_lock](#324-omp_unset_lock-and-omp_unset_nest_lock-functions) Funktion gibt eine omp_nest_lock_t-Sperre frei.
- Die [Omp_test_nest_lock](#325-omp_test_lock-and-omp_test_nest_lock-functions) Funktion testet eine omp_nest_lock_t-Sperre.

Die OpenMP-Lock-Funktionen auf die Sperren der Variable so, dass sie immer lesen und aktualisieren Sie den aktuellen Wert der Sperre Variablen zugreifen. Aus diesem Grund nicht erforderlich, um eine OpenMP-Programm, eine explizite enthalten `flush` Anweisungen, um sicherzustellen, dass die Sperre der Variablen in verschiedenen Threads konsistent ist. (Es kann beispielsweise erforderlich sein `flush` Anweisungen, um die Werte der anderen Variablen konsistent zu machen.)

### <a name="321-omp_init_lock-and-omp_init_nest_lock-functions"></a>3.2.1 Omp_init_lock and Omp_init_nest_lock-Funktionen

Diese Funktionen geben die einzige Möglichkeit zur Initialisierung einer Sperre. Jede Funktion initialisiert, die Sperre, die mit dem Parameter verbundenen *Sperre* für die Verwendung in zukünftigen aufrufen. Es wird folgendes Format verwendet:

```cpp
#include <omp.h>
void omp_init_lock(omp_lock_t *lock);
void omp_init_nest_lock(omp_nest_lock_t *lock);
```

Der anfängliche Zustand entsperrt wird (d. h. kein Thread die Sperre besitzt). Für eine omp_nest_lock_t-Sperre ist die Anzahl die ersten Schachtelungsebene 0 (null). Es ist nicht kompatibel, um eine dieser Routinen mit einer Sperre-Variablen aufzurufen, die bereits initialisiert wurde.

### <a name="322-omp_destroy_lock-and-omp_destroy_nest_lock-functions"></a>3.2.2 Omp_destroy_lock- und Omp_destroy_nest_lock-Funktionen

Diese Funktionen stellen sicher, dass die Spitzen beim Sperren der Variablen *Sperre* ist nicht initialisiert. Es wird folgendes Format verwendet:

```cpp
#include <omp.h>
void omp_destroy_lock(omp_lock_t *lock);
void omp_destroy_nest_lock(omp_nest_lock_t *lock);
```

Es ist nicht kompatibel, entweder diese Routinen mit einer Sperre-Variable aufrufen, die nicht initialisiert wurde oder nicht gesperrt.

### <a name="323-omp_set_lock-and-omp_set_nest_lock-functions"></a>3.2.3 Omp_set_lock- und Omp_set_nest_lock-Funktionen

Jede dieser Funktionen blockiert den Thread, die Funktion ausgeführt, bis die angegebene Sperre verfügbar ist, und dann die Sperre legt. Eine einfache Sperre ist verfügbar, wenn es nicht gesperrt. Omp_nest_lock_t-Sperre ist verfügbar, wenn es nicht gesperrt, oder wenn sie bereits den Thread, die Ausführung der Funktion gehört. Es wird folgendes Format verwendet:

```cpp
#include <omp.h>
void omp_set_lock(omp_lock_t *lock);
void omp_set_nest_lock(omp_nest_lock_t *lock);
```

Für eine einfache Sperre, die das Argument für die `omp_set_lock` Funktion muss auf ein initialisiertes Sperren der Variable verweisen. Der Thread, die Ausführung der Funktion wird den Besitz der Sperre gewährt.

Für eine omp_nest_lock_t-Sperre, das Argument für die `omp_set_nest_lock` Funktion muss auf ein initialisiertes Sperren der Variable verweisen. Die Anzahl die Schachtelungsebene wird erhöht, und der Thread erhält, oder beibehält, den Besitz der Sperre.

### <a name="324-omp_unset_lock-and-omp_unset_nest_lock-functions"></a>3.2.4 Omp_unset_lock and Omp_unset_nest_lock-Funktionen

Diese Funktionen bieten die Möglichkeit des Freigebens von den Besitz einer Sperre. Es wird folgendes Format verwendet:

```cpp
#include <omp.h>
void omp_unset_lock(omp_lock_t *lock);
void omp_unset_nest_lock(omp_nest_lock_t *lock);
```

Das Argument für jede dieser Funktionen muss auf ein initialisiertes Sperren der Variable im Besitz der Threads, die Ausführung der Funktion verweisen. Das Verhalten ist nicht definiert, wenn der Thread diese Sperre nicht besitzt.

Für eine einfache Sperre die `omp_unset_lock` Funktion gibt den Thread, die Ausführung der Funktion aus den Besitz der Sperre frei.

Für eine omp_nest_lock_t-Sperre die `omp_unset_nest_lock` Funktion verringert die Anzahl der Schachtelungsebenen und Versionen der Thread, die Ausführung der Funktion aus den Besitz der Sperre, wenn das Rekursionsergebnis 0 (null) ist.

### <a name="325-omp_test_lock-and-omp_test_nest_lock-functions"></a>3.2.5 Omp_test_lock and Omp_test_nest_lock-Funktionen

Diese Funktionen versuchen, eine Sperre festzulegen, aber nicht die Ausführung des Threads blockieren. Es wird folgendes Format verwendet:

```cpp
#include <omp.h>
int omp_test_lock(omp_lock_t *lock);
int omp_test_nest_lock(omp_nest_lock_t *lock);
```

Das Argument muss auf ein initialisiertes Sperren der Variable verweisen. Diese Funktionen versuchen, eine Sperre auf die gleiche Weise wie festgelegt `omp_set_lock` und `omp_set_nest_lock`, außer dass sie die Ausführung des Threads nicht blockieren.

Für eine einfache Sperre die `omp_test_lock` Funktion gibt einen Wert ungleich NULL zurück, wenn die Sperre erfolgreich festgelegt wurde; andernfalls wird 0 (null) zurückgegeben.

Für eine omp_nest_lock_t-Sperre die `omp_test_nest_lock` Funktion gibt die Anzahl die neue schachteln zurück, wenn die Sperre erfolgreich festgelegt wurde; andernfalls wird 0 (null) zurückgegeben.

## <a name="33-timing-routines"></a>3.3 Routinen zur zeitlichen Steuerung die

In diesem Abschnitt beschriebenen Funktionen unterstützen einen Timer portable Wall-Clock:

- Die [Omp_get_wtime](#331-omp_get_wtime-function) Funktion gibt die verstrichene wanduhrzeit zurück.
- Die [Omp_get_wtick](#332-omp_get_wtick-function) Funktionsergebnis Sekunden zwischen den Teilstrichen aufeinander folgenden.

### <a name="331-omp_get_wtime-function"></a>3.3.1 Omp_get_wtime-Funktion

Die `omp_get_wtime` Funktion gibt einen Gleitkommawert mit doppelter Genauigkeit in Sekunden seit einigen"in der Vergangenheit" die verstrichene wanduhrzeit gleich.  Die tatsächliche "Zeit in der Vergangenheit" ist ein beliebiger, aber es ist definitiv nicht ändern, während der Ausführung des Anwendungsprogramms. Es wird folgendes Format verwendet:

```cpp
#include <omp.h>
double omp_get_wtime(void);
```

Es ist davon auszugehen, dass die Funktion zum Messen der verstrichenen Zeit, wie im folgenden Beispiel gezeigt verwendet wird:

```cpp
double start;
double end;
start = omp_get_wtime();
... work to be timed ...
end = omp_get_wtime();
printf_s("Work took %f sec. time.\n", end-start);
```

Die zurückgegebenen Uhrzeiten sind "pro-Thread Zeit", indem Sie die vorgesehen ist, dass sie erforderlich sind nicht global auf alle Threads, die Teilnahme an einer Anwendungs übereinstimmen.

### <a name="332-omp_get_wtick-function"></a>3.3.2 Omp_get_wtick-Funktion

Die `omp_get_wtick` Funktion gibt einen Gleitkommawert mit doppelter Genauigkeit zwischen aufeinander folgenden Zeiteinheiten gleich der Anzahl von Sekunden. Es wird folgendes Format verwendet:

```cpp
#include <omp.h>
double omp_get_wtick(void);
```
