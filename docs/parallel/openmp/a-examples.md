---
title: A. Beispiele
ms.date: 01/18/2019
ms.assetid: c0f6192f-a205-449b-b84c-cb30dbcc8b8f
ms.openlocfilehash: 061490d34829175bfbdcd84d6208aa396bb19671
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62362971"
---
# <a name="a-examples"></a>A. Beispiele

Im folgenden sind Beispiele für die Konstrukte, die in diesem Dokument definiert. Eine Anweisung nach einer Direktive ist zusammengesetzten nur bei Bedarf, und ist eine nicht zusammengesetzte Anweisung aus einer vorhergehenden Anweisung eingerückt.

## <a name="a1-a-simple-loop-in-parallel"></a>A. 1 eine einfache Schleife parallel

Im folgende Beispiel wird veranschaulicht, wie eine Schleife verwenden, die parallelisiert werden die [für parallele](2-directives.md#251-parallel-for-construct) Richtlinie. Die Schleifeniterationsvariable ist standardmäßig privat, damit es nicht erforderlich, explizit in einer private-Klausel angegeben ist.

```cpp
#pragma omp parallel for
    for (i=1; i<n; i++)
        b[i] = (a[i] + a[i-1]) / 2.0;
```

## <a name="a2-conditional-compilation"></a>A. 2 für die bedingte Kompilierung

Die folgenden Beispiele veranschaulichen die Verwendung des für die bedingte Kompilierung, die mit dem Makro OpenMP [_OPENMP](2-directives.md#22-conditional-compilation). Bei der OpenMP-Kompilierung die `_OPENMP` Makro definiert wird.

```cpp
# ifdef _OPENMP
    printf_s("Compiled by an OpenMP-compliant implementation.\n");
# endif
```

Der definierte Präprozessoroperator kann mehr als ein Makro in einer einzelnen Richtlinie getestet werden.

```cpp
# if defined(_OPENMP) && defined(VERBOSE)
    printf_s("Compiled by an OpenMP-compliant implementation.\n");
# endif
```

## <a name="a3-parallel-regions"></a>A. 3 parallelen Bereichen

Die [parallele](2-directives.md#23-parallel-construct) -Direktive kann verwendet werden, in parallelen Programmen gröbere. Im folgenden Beispiel ist jeder Thread in den parallelen Bereich entscheidet, welcher Teil der globalen Array `x` zum abarbeiten, basierend auf der Thread-Anzahl:

```cpp
#pragma omp parallel shared(x, npoints) private(iam, np, ipoints)
{
    iam = omp_get_thread_num();
    np =  omp_get_num_threads();
    ipoints = npoints / np;
    subdomain(x, iam, ipoints);
}
```

## <a name="a4-the-nowait-clause"></a>A. 4 der Nowait-Klausel

Wenn viele unabhängige Schleifen innerhalb eines parallelen Bereichs vorhanden sind, können Sie mithilfe der [Nowait](2-directives.md#241-for-construct) Klausel, die die implizite Grenze am Ende der `for` Anweisung wie folgt:

```cpp
#pragma omp parallel
{
    #pragma omp for nowait
        for (i=1; i<n; i++)
             b[i] = (a[i] + a[i-1]) / 2.0;
    #pragma omp for nowait
        for (i=0; i<m; i++)
            y[i] = sqrt(z[i]);
}
```

## <a name="a5-the-critical-directive"></a>A. 5 der critical-Direktive

Das folgende Beispiel schließt mehrere [kritische](2-directives.md#262-critical-construct) Anweisungen. Das Beispiel veranschaulicht ein Warteschlangen-Modell, bei der eine Aufgabe aus der Warteschlange entfernt und bearbeitet, werden. Zum Schutz gegen viele Threads, die die gleiche Aufgabe entfernen aus der Warteschlange muss sich der entfernen-Vorgang einem `critical` Abschnitt. Da die zwei Warteschlangen in diesem Beispiel unabhängig sind, werden sie durch geschützt `critical` Anweisungen mit unterschiedlichen Namen *x-Achse enthält* und *Yaxis*.

```cpp
#pragma omp parallel shared(x, y) private(x_next, y_next)
{
    #pragma omp critical ( xaxis )
        x_next = dequeue(x);
    work(x_next);
    #pragma omp critical ( yaxis )
        y_next = dequeue(y);
    work(y_next);
}
```

## <a name="a6-the-lastprivate-clause"></a>A. 6 der Lastprivate-Klausel

Manchmal die richtige Ausführung hängt von der Wert, den die letzte Iteration einer Schleife zu einer Variablen zugewiesen. Diese Programme sind, müssen alle diese Variablen als Argumente für Auflisten einer [Lastprivate](2-directives.md#2723-lastprivate) Klausel so, dass die Werte der Variablen bei Ausführung der Schleife sequenziell ist identisch.

```cpp
#pragma omp parallel
{
   #pragma omp for lastprivate(i)
      for (i=0; i<n-1; i++)
         a[i] = b[i] + b[i+1];
}
a[i]=b[i];
```

Im vorherigen Beispiel den Wert der `i` am Ende des parallelen Bereichs ist gleich `n-1`, wie im sequentiell.

## <a name="a7-the-reduction-clause"></a>A. 7 der Reduction-Klausel

Das folgende Beispiel zeigt die [Verringerung](2-directives.md#2726-reduction) Klausel:

```cpp
#pragma omp parallel for private(i) shared(x, y, n) \
                         reduction(+: a, b)
    for (i=0; i<n; i++) {
        a = a + x[i];
        b = b + y[i];
    }
```

## <a name="a8-parallel-sections"></a>A. 8 parallelen Abschnitten

Im folgenden Beispiel (für [Abschnitt 2.4.2](2-directives.md#242-sections-construct)), Funktionen *x-Achse enthält*, *Yaxis*, und *Zaxis* gleichzeitig ausgeführt werden können. Die erste `section` Richtlinie ist optional.  Alle `section` Anweisungen müssen in der lexikalischen Wertebereich angezeigt werden die `parallel sections` zu erstellen.

```cpp
#pragma omp parallel sections
{
    #pragma omp section
        xaxis();
    #pragma omp section
        yaxis();
    #pragma omp section
        zaxis();
}
```

## <a name="a9-single-directives"></a>A. 9 einzelner Direktiven

Das folgende Beispiel zeigt die [einzelne](2-directives.md#243-single-construct) Richtlinie. Im Beispiel ist nur ein Thread (normalerweise der erste Thread, der erkennt die `single` Richtlinie) gibt die Meldung von Fortschritt. Der Benutzer muss keine Annahmen zu welchem Thread ausgeführt, wird die `single` Abschnitt. Alle anderen Threads werden übersprungen. die `single` aus, und beenden Sie die Barriere am Ende der `single` zu erstellen. Wenn andere Threads fortgesetzt werden können, ohne zu warten, für die Threadausführung den `single` Abschnitt eine `nowait` Klausel kann angegeben werden, auf die `single` Richtlinie.

```cpp
#pragma omp parallel
{
    #pragma omp single
        printf_s("Beginning work1.\n");
    work1();
    #pragma omp single
        printf_s("Finishing work1.\n");
    #pragma omp single nowait
        printf_s("Finished work1 and beginning work2.\n");
    work2();
}
```

## <a name="a10-sequential-ordering"></a>A. 10 sequenziellen Reihenfolge

[Sortiert die Abschnitte](2-directives.md#266-ordered-construct) eignen sich für weitere Anordnung der Ausgabe von Arbeit, die parallel ausgeführt wurde. Das folgende Programm druckt die Indizes in sequenzieller Reihenfolge aus:

```cpp
#pragma omp for ordered schedule(dynamic)
    for (i=lb; i<ub; i+=st)
        work(i);
void work(int k)
{
    #pragma omp ordered
        printf_s(" %d", k);
}
```

## <a name="a11-a-fixed-number-of-threads"></a>A. 11 eine feste Anzahl von threads

Einige Programme sind abhängig von einer festen, vordefinierten Anzahl von Threads ordnungsgemäß ausgeführt wird.  Da die Standardeinstellung für die dynamische Anpassung der Anzahl von Threads Implementierung definiert ist, können diese Programme deaktivieren Sie die dynamische Threads-Funktion, und legen Sie die Anzahl der Threads explizit auf die Portabilität zu halten. Das folgende Beispiel zeigt, wie Sie dazu [Omp_set_dynamic](3-run-time-library-functions.md#317-omp_set_dynamic-function), und [Omp_set_num_threads](3-run-time-library-functions.md#311-omp_set_num_threads-function):

```cpp
omp_set_dynamic(0);
omp_set_num_threads(16);
#pragma omp parallel shared(x, npoints) private(iam, ipoints)
{
    if (omp_get_num_threads() != 16)
      abort();
    iam = omp_get_thread_num();
    ipoints = npoints/16;
    do_by_16(x, iam, ipoints);
}
```

In diesem Beispiel führt das Programm ordnungsgemäß nur dann, wenn es von 16 Threads ausgeführt wird. Wenn die Implementierung nicht unterstützen 16 Threads ist, wird das Verhalten dieses Beispiels Implementierung definiert.

Die Anzahl der Threads, die Ausführung eines parallelen Bereichs bleibt während eines parallelen Bereichs ist, unabhängig von der Einstellung "Threads" dynamische konstant. Der Mechanismus für die dynamische Threads bestimmt die Anzahl der Threads an, zu Beginn des parallelen Bereichs verwendet und für die Dauer des Bereichs konstant bleibt.

## <a name="a12-the-atomic-directive"></a>A. 12 der atomic-Direktive

Im folgende Beispiel vermeidet Racebedingungen (gleichzeitige Aktualisierungen eines Elements von *x* von vielen Threads) mithilfe der [atomic](2-directives.md#264-atomic-construct) Richtlinie:

```cpp
#pragma omp parallel for shared(x, y, index, n)
    for (i=0; i<n; i++)
    {
        #pragma omp atomic
            x[index[i]] += work1(i);
        y[i] += work2(i);
    }
```

Der Vorteil der Verwendung der `atomic` -Anweisung in diesem Beispiel ist, dass es ermöglicht, dass Updates von zwei verschiedenen Elementen von x parallel ausgeführt. Wenn eine [kritische](2-directives.md#262-critical-construct) -Direktive wird stattdessen verwendet, und klicken Sie dann alle updates auf Elemente des *x* seriell (jedoch nicht in einer Reihenfolge garantiert) ausgeführt werden.

Die `atomic` Richtlinie gilt nur für die C- oder C++-Anweisung, die unmittelbar folgt.  Als Ergebnis Elemente *y* in diesem Beispiel nicht automatisch aktualisiert werden.

## <a name="a13-a-flush-directive-with-a-list"></a>A. 13 ein flush-Direktive mit einer Liste

Im folgenden Beispiel wird die `flush` -Direktive für den Punkt zu Punkt-Synchronisierung von bestimmten Objekten zwischen Paaren von Threads:

```cpp
int   sync[NUMBER_OF_THREADS];
float work[NUMBER_OF_THREADS];
#pragma omp parallel private(iam,neighbor) shared(work,sync)
{
    iam = omp_get_thread_num();
    sync[iam] = 0;
    #pragma omp barrier

    // Do computation into my portion of work array
    work[iam] = ...;

    //  Announce that I am done with my work
    // The first flush ensures that my work is
    // made visible before sync.
    // The second flush ensures that sync is made visible.
    #pragma omp flush(work)
    sync[iam] = 1;
    #pragma omp flush(sync)

    // Wait for neighbor
    neighbor = (iam>0 ? iam : omp_get_num_threads()) - 1;
    while (sync[neighbor]==0)
    {
        #pragma omp flush(sync)
    }

    // Read neighbor's values of work array
    ... = work[neighbor];
}
```

## <a name="a14-a-flush-directive-without-a-list"></a>A. 14 ein flush-Direktive ohne eine Liste

Im folgenden Beispiel wird (für [Abschnitt 2.6.5](2-directives.md#265-flush-directive)) unterscheidet die gemeinsam genutzten Objekte betroffen eine `flush` -Direktive zusammen mit keine Liste der gemeinsam genutzten Objekte, die nicht negativ beeinflusst:

```cpp
// omp_flush_without_list.c
#include <omp.h>

int x, *p = &x;

void f1(int *q)
{
    *q = 1;
    #pragma omp flush
    // x, p, and *q are flushed
    //   because they are shared and accessible
    // q is not flushed because it is not shared.
}

void f2(int *q)
{
    #pragma omp barrier
    *q = 2;

    #pragma omp barrier
    // a barrier implies a flush
    // x, p, and *q are flushed
    //   because they are shared and accessible
    // q is not flushed because it is not shared.
}

int g(int n)
{
    int i = 1, j, sum = 0;
    *p = 1;

    #pragma omp parallel reduction(+: sum) num_threads(10)
    {
        f1(&j);
        // i, n and sum were not flushed
        //   because they were not accessible in f1
        // j was flushed because it was accessible
        sum += j;
        f2(&j);
        // i, n, and sum were not flushed
        //   because they were not accessible in f2
        // j was flushed because it was accessible
        sum += i + j + *p + n;
    }
    return sum;
}

int main()
{
}
```

## <a name="a15-the-number-of-threads-used"></a>A. 15 die Anzahl der verwendeten threads

Betrachten Sie die folgende falsche Beispiel (für [Abschnitt 3.1.2](3-run-time-library-functions.md#312-omp_get_num_threads-function)):

```cpp
np = omp_get_num_threads(); // misplaced
#pragma omp parallel for schedule(static)
    for (i=0; i<np; i++)
        work(i);
```

Die `omp_get_num_threads()` aufrufen, gibt 1 zurück im seriellen Abschnitt des Codes, also *Np* wird immer im vorherigen Beispiel gleich 1 sein. Um die Anzahl der Threads zu bestimmen, die für den parallelen Bereich bereitgestellt werden, sollte der Aufruf in den parallelen Bereich sein.

Das folgende Beispiel zeigt, wie Sie dieses Programm zu schreiben, ohne dass eine Abfrage für die Anzahl der Threads:

```cpp
#pragma omp parallel private(i)
{
    i = omp_get_thread_num();
    work(i);
}
```

## <a name="a16-locks"></a>A. 16 Sperren

Im folgenden Beispiel (für [Abschnitt 3.2](3-run-time-library-functions.md#32-lock-functions)), das Argument für die Lock-Funktionen müssen Typ `omp_lock_t`, und dass keine Notwendigkeit besteht, sie zu leeren.  Die Lock-Funktionen dazu führen, dass die Threads im Leerlauf ist beim Warten auf einen Eintrag in den ersten kritischen Abschnitt, aber eine andere Aktion beim Warten auf einen Eintrag in der zweiten ausführen.  Die `omp_set_lock` Funktion-Blöcken, aber die `omp_test_lock` Funktion nicht, sodass die Arbeit in `skip()` durchgeführt werden.

```cpp
// omp_using_locks.c
// compile with: /openmp /c
#include <stdio.h>
#include <omp.h>

void work(int);
void skip(int);

int main() {
   omp_lock_t lck;
   int id;

   omp_init_lock(&lck);
   #pragma omp parallel shared(lck) private(id)
   {
      id = omp_get_thread_num();

      omp_set_lock(&lck);
      printf_s("My thread id is %d.\n", id);

      // only one thread at a time can execute this printf
      omp_unset_lock(&lck);

      while (! omp_test_lock(&lck)) {
         skip(id);   // we do not yet have the lock,
                     // so we must do something else
      }
      work(id);     // we now have the lock
                    // and can do the work
      omp_unset_lock(&lck);
   }
   omp_destroy_lock(&lck);
}
```

## <a name="a17-nestable-locks"></a>A. 17 schachtelbaren Sperren

Im folgenden Beispiel wird (für [Abschnitt 3.2](3-run-time-library-functions.md#32-lock-functions)) wird veranschaulicht, wie eine omp_nest_lock_t-Sperre zum Synchronisieren von Updates sowohl für eine gesamte Struktur und eines seiner Elemente verwendet werden kann.

```cpp
#include <omp.h>
typedef struct {int a,b; omp_nest_lock_t lck;} pair;

void incr_a(pair *p, int a)
{
    // Called only from incr_pair, no need to lock.
    p->a += a;
}

void incr_b(pair *p, int b)
{
    // Called both from incr_pair and elsewhere,
    // so need a nestable lock.

    omp_set_nest_lock(&p->lck);
    p->b += b;
    omp_unset_nest_lock(&p->lck);
}

void incr_pair(pair *p, int a, int b)
{
    omp_set_nest_lock(&p->lck);
    incr_a(p, a);
    incr_b(p, b);
    omp_unset_nest_lock(&p->lck);
}

void f(pair *p)
{
    extern int work1(), work2(), work3();
    #pragma omp parallel sections
    {
        #pragma omp section
            incr_pair(p, work1(), work2());
        #pragma omp section
            incr_b(p, work3());
    }
}
```

## <a name="a18-nested-for-directives"></a>A. 18 geschachtelte for-Direktiven

Im folgenden Beispiel `for` [-Direktive Schachtelung](2-directives.md#29-directive-nesting) ist kompatibel, da die inneren und äußeren `for` Direktiven an verschiedenen parallelen Bereichen zu binden:

```cpp
#pragma omp parallel default(shared)
{
    #pragma omp for
        for (i=0; i<n; i++)
        {
            #pragma omp parallel shared(i, n)
            {
                #pragma omp for
                    for (j=0; j<n; j++)
                        work(i, j);
            }
        }
}
```

Es ist auch ein folgende Abwandlung des vorherigen Beispiels kompatibel:

```cpp
#pragma omp parallel default(shared)
{
    #pragma omp for
        for (i=0; i<n; i++)
            work1(i, n);
}

void work1(int i, int n)
{
    int j;
    #pragma omp parallel default(shared)
    {
        #pragma omp for
            for (j=0; j<n; j++)
                work2(i, j);
    }
    return;
}
```

## <a name="a19-examples-showing-incorrect-nesting-of-work-sharing-directives"></a>19 Beispiele für falsche Verschachtelung von Arbeit sharing-arbeitsteilungsdirektiven Direktiven

Die Beispiele in diesem Abschnitt veranschaulichen die [-Direktive Schachtelung](2-directives.md#29-directive-nesting) Regeln.

Im folgende Beispiel nicht konform ist. da die inneren und äußeren `for` Anweisungen geschachtelt sind und auf die gleiche Bindung `parallel` Richtlinie:

```cpp
void wrong1(int n)
{
  #pragma omp parallel default(shared)
  {
      int i, j;
      #pragma omp for
      for (i=0; i<n; i++) {
          #pragma omp for
              for (j=0; j<n; j++)
                 work(i, j);
     }
   }
}
```

Die folgende dynamisch geschachtelte Version des obigen Beispiels ist auch nicht kompatibel:

```cpp
void wrong2(int n)
{
  #pragma omp parallel default(shared)
  {
    int i;
    #pragma omp for
      for (i=0; i<n; i++)
        work1(i, n);
  }
}

void work1(int i, int n)
{
  int j;
  #pragma omp for
    for (j=0; j<n; j++)
      work2(i, j);
}
```

Im folgende Beispiel nicht konform ist da die `for` und `single` Anweisungen geschachtelt sind und sie an der gleichen Region für die parallele binden:

```cpp
void wrong3(int n)
{
  #pragma omp parallel default(shared)
  {
    int i;
    #pragma omp for
      for (i=0; i<n; i++) {
        #pragma omp single
          work(i);
      }
  }
}
```

Im folgende Beispiel nicht konform ist. da eine `barrier` -Direktive innerhalb einer `for` kann zu Deadlocks führen:

```cpp
void wrong4(int n)
{
  #pragma omp parallel default(shared)
  {
    int i;
    #pragma omp for
      for (i=0; i<n; i++) {
        work1(i);
        #pragma omp barrier
        work2(i);
      }
  }
}
```

Im folgende Beispiel nicht konform ist. da der `barrier` Deadlock führt aufgrund der Tatsache, dass jeweils nur ein Thread den kritischen Abschnitt eingegeben werden kann:

```cpp
void wrong5()
{
  #pragma omp parallel
  {
    #pragma omp critical
    {
       work1();
       #pragma omp barrier
       work2();
    }
  }
}
```

Im folgende Beispiel nicht konform ist. da die `barrier` Deadlock führt aufgrund der Tatsache, dass nur ein Thread ausgeführt wird die `single` Abschnitt:

```cpp
void wrong6()
{
  #pragma omp parallel
  {
    setup();
    #pragma omp single
    {
      work1();
      #pragma omp barrier
      work2();
    }
    finish();
  }
}
```

## <a name="a20-bind-barrier-directives"></a>A. 20 Bindung Barrier-Direktiven

Die direktivenbindung Regeln-Aufruf für eine `barrier` Richtlinie zum Binden an die nächste einschließende `parallel` Richtlinie. Weitere Informationen zu direktivenbindung, finden Sie unter [Abschnitt 2.8](2-directives.md#28-directive-binding).

Im folgenden Beispiel den Aufruf von *main* zu *sub2* ist kompatibel, da die `barrier` (in *sub3*) bindet an den parallelen Bereich im *sub2* . Den Aufruf von *main* zu *sub1* ist kompatibel, da die `barrier` bindet an die parallelen Bereichs in der Unterroutine *sub2*.  Den Aufruf von *main* zu *sub3* ist kompatibel, da die `barrier` nicht in einer beliebigen parallel Region gebunden und wird ignoriert. Darüber hinaus die `barrier` synchronisiert nur das Team von Threads in der einschließenden parallelen Bereich und nicht alle Threads in erstellten *sub1*.

```cpp
int main()
{
    sub1(2);
    sub2(2);
    sub3(2);
}

void sub1(int n)
{
    int i;
    #pragma omp parallel private(i) shared(n)
    {
        #pragma omp for
        for (i=0; i<n; i++)
            sub2(i);
    }
}

void sub2(int k)
{
     #pragma omp parallel shared(k)
     sub3(k);
}

void sub3(int n)
{
    work(n);
    #pragma omp barrier
    work(n);
}
```

## <a name="a21-scope-variables-with-the-private-clause"></a>A. 21 Variablen im Bereich mit der private-Klausel

Die Werte der `i` und `j` im folgenden Beispiel sind nicht beim Beenden des parallelen Bereichs definiert:

```cpp
int i, j;
i = 1;
j = 2;
#pragma omp parallel private(i) firstprivate(j)
{
  i = 3;
  j = j + 2;
}
printf_s("%d %d\n", i, j);
```

Weitere Informationen zu den `private` -Klausel finden Sie unter [Abschnitt 2.7.2.1](2-directives.md#2721-private).

## <a name="a22-the-defaultnone-clause"></a>A. 22 der default(None)-Klausel

Das folgende Beispiel unterscheidet, die Variablen, die betroffen sind der `default(none)` -Klausel aus der Variablen, die nicht:

```cpp
// openmp_using_clausedefault.c
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int x, y, z[1000];
#pragma omp threadprivate(x)

void fun(int a) {
   const int c = 1;
   int i = 0;

   #pragma omp parallel default(none) private(a) shared(z)
   {
      int j = omp_get_num_thread();
             //O.K.  - j is declared within parallel region
      a = z[j];       // O.K.  - a is listed in private clause
                      //      - z is listed in shared clause
      x = c;          // O.K.  - x is threadprivate
                      //      - c has const-qualified type
      z[i] = y;       // C3052 error - cannot reference i or y here

      #pragma omp for firstprivate(y)
         for (i=0; i<10 ; i++) {
            z[i] = y;  // O.K. - i is the loop control variable
                       // - y is listed in firstprivate clause
          }
       z[i] = y;   // Error - cannot reference i or y here
   }
}
```

Weitere Informationen zu den `default` -Klausel finden Sie unter [Abschnitt 2.7.2.5](2-directives.md#2725-default).

## <a name="a23-examples-of-the-ordered-directive"></a>A. 23 Beispiele für die ordered-Direktive

Es ist möglich, dass viele geordnete Abschnitte mit einer `for` angegeben mit der `ordered` Klausel. Im erste Beispiel ist nicht kompatibel, da die API gibt an, die folgende Regel:

"Eine Iteration einer Schleife mit einer `for` Konstrukt muss nicht ausgeführt, die gleiche `ordered` Direktive mehr als einmal, und es muss nicht ausgeführt, mehr als eine `ordered` Richtlinie." (Finden Sie unter [Abschnitt 2.6.6](2-directives.md#266-ordered-construct).)

Führen Sie alle Iterationen zu zwei sortierte Abschnitte in diesem Beispiel nicht kompatibel:

```cpp
#pragma omp for ordered
for (i=0; i<n; i++)
{
    ...
    #pragma omp ordered
    { ... }
    ...
    #pragma omp ordered
    { ... }
    ...
}
```

Im folgenden Beispiel von kompatiblen eine `for` mit mehr als einem sortiert Abschnitt:

```cpp
#pragma omp for ordered
for (i=0; i<n; i++)
{
    ...
    if (i <= 10)
    {
        ...
        #pragma omp ordered
        { ... }
    }
    ...
    (i > 10)
    {
        ...
        #pragma omp ordered
        { ... }
    }
    ...
}
```

## <a name="a24-example-of-the-private-clause"></a>A. 24 Beispiel für die private-Klausel

Die [private](2-directives.md#2721-private) -Klausel eines parallelen Bereichs ist nur wirksam, die für den lexikalischen Wertebereich des Bereichs, nicht für den dynamischen Wertebereich des Bereichs.  Aus diesem Grund in der folgenden, jede Verwendung der Variablen Beispiel *eine* innerhalb der `for` Schleife in der Routine *f* bezieht sich auf eine private Kopie des *eine*, zwar eine Verwendung in Routine *g* verweist auf die globale *eine*.

```cpp
int a;

void f(int n)
{
    a = 0;

    #pragma omp parallel for private(a)
    for (int i=1; i<n; i++)
    {
        a = i;
        g(i, n);
        d(a);     // Private copy of "a"
        ...
    }
    ...

void g(int k, int n)
{
    h(k,a); // The global "a", not the private "a" in f
}
```

## <a name="a25-examples-of-the-copyprivate-data-attribute-clause"></a>25 Beispiele der Copyprivate-Klausel für die Data-Attribut-datenattributklausel

**Beispiel 1:** Die [Copyprivate](2-directives.md#2728-copyprivate) -Klausel kann verwendet werden, senden, die Werte, die von einem einzelnen Thread direkt für alle Instanzen der privaten Variablen in anderen Threads abgerufen.

```cpp
float x, y;
#pragma omp threadprivate(x, y)

void init( )
{
    float a;
    float b;

    #pragma omp single copyprivate(a,b,x,y)
    {
        get_values(a,b,x,y);
    }

    use_values(a, b, x, y);
}
```

Wenn Sie routinemäßige *Init* heißt aus einer seriellen Region, ihr Verhalten wirkt sich nicht aus durch das Vorhandensein der Richtlinien. Nach dem Aufruf der *Get_values* Routine von einem Thread ausgeführt wurde, kein Thread das Konstrukt verlässt, bis die private Objekte, die vom angegebenen *eine*, *b*, *x*, und *y* in allen Threads haben mit den Werten lesen definiert werden.

**Beispiel 2:** Im Gegensatz zum vorherigen Beispiel nehmen wir an, dass der Lesevorgang von einem bestimmten Thread, z. B. die master-Thread ausgeführt werden muss. In diesem Fall die `copyprivate` Klausel nicht verwendet werden, die Übertragung direkt zu tun, aber es kann verwendet werden, um den Zugriff auf ein temporäres Objekt des freigegebenen ermöglichen.

```cpp
float read_next( )
{
    float * tmp;
    float return_val;

    #pragma omp single copyprivate(tmp)
    {
        tmp = (float *) malloc(sizeof(float));
    }

    #pragma omp master
    {
        get_float( tmp );
    }

    #pragma omp barrier
    return_val = *tmp;
    #pragma omp barrier

    #pragma omp single
    {
       free(tmp);
    }

    return return_val;
}
```

**Beispiel 3:** Nehmen wir an, dass die Anzahl der Sperrobjekte, die erforderlich sind, innerhalb eines parallelen Bereichs problemlos bestimmt werden kann, bevor Sie eingeben. Die `copyprivate` -Klausel kann verwendet werden, um den Zugriff auf freigegebene Sperrobjekte bereitzustellen, die innerhalb dieser parallelen Bereichs zugeordnet werden.

```cpp
#include <omp.h>

omp_lock_t *new_lock()
{
    omp_lock_t *lock_ptr;

    #pragma omp single copyprivate(lock_ptr)
    {
        lock_ptr = (omp_lock_t *) malloc(sizeof(omp_lock_t));
        omp_init_lock( lock_ptr );
    }

    return lock_ptr;
}
```

## <a name="a26-the-threadprivate-directive"></a>A. 26 der Threadprivate-Direktive

Die folgenden Beispiele veranschaulichen, wie Sie mit der [Threadprivate](2-directives.md#271-threadprivate-directive) Richtlinie jeder Thread über einen separaten Zähler gewähren.

### <a name="example-1"></a>Beispiel 1

```cpp
int counter = 0;
#pragma omp threadprivate(counter)

int sub()
{
    counter++;
    return(counter);
}
```

### <a name="example-2"></a>Beispiel 2

```cpp
int sub()
{
    static int counter = 0;
    #pragma omp threadprivate(counter)
    counter++;
    return(counter);
}
```

## <a name="a27-c99-variable-length-arrays"></a>A. 27 C99-Arrays mit variabler Länge

Im folgende Beispiel wird veranschaulicht, wie mit variabler Länge Arrays C99 (VLAs) in einem [Firstprivate](2-directives.md#2722-firstprivate) Richtlinie.

> [!NOTE]
> In Visual C++-Arrays variabler Länge werden derzeit nicht unterstützt.

```cpp
void f(int m, int C[m][m])
{
    double v1[m];
    ...
    #pragma omp parallel firstprivate(C, v1)
    ...
}
```

## <a name="a28-the-numthreads-clause"></a>A. 28 der Num_threads-Klausel

Das folgende Beispiel zeigt die [Num_threads](2-directives.md#23-parallel-construct) Klausel. Die parallelen Bereichs ist mit einem Maximum von 10 Threads ausgeführt.

```cpp
#include <omp.h>
main()
{
    omp_set_dynamic(1);
    ...
    #pragma omp parallel num_threads(10)
    {
        ... parallel region ...
    }
}
```

## <a name="a29-work-sharing-constructs-inside-a-critical-construct"></a>A.29 Arbeitsteilungskonstrukte innerhalb eines critical-Konstrukts

Im folgende Beispiel wird veranschaulicht, mit einem Konstrukt Freigabe von Arbeit in einem `critical` zu erstellen. In diesem Beispiel ist kompatibel, da die Arbeit-Freigabe zu erstellen und die `critical` Konstrukt nicht auf den parallelen Bereich binden.

```cpp
void f()
{
  int i = 1;
  #pragma omp parallel sections
  {
    #pragma omp section
    {
      #pragma omp critical (name)
      {
        #pragma omp parallel
        {
          #pragma omp single
          {
            i++;
          }
        }
      }
    }
  }
}
```

## <a name="a30-reprivatization"></a>A. 30 erneuten Privatisierung

Das folgende Beispiel zeigt der erneuten Privatisierung von Variablen. Private Variablen können markiert werden `private` erneut in einer geschachtelten-Direktive. Sie müssen diese Variablen in der einschließenden parallelen Bereich gemeinsam nutzen.

```cpp
int i, a;
...
#pragma omp parallel private(a)
{
  ...
  #pragma omp parallel for private(a)
  for (i=0; i<10; i++)
     {
       ...
     }
}
```

## <a name="a31-thread-safe-lock-functions"></a>A. 31 threadsichere Lock-Funktionen

Die folgenden C++ wird veranschaulicht, wie ein Array von Sperren in einem parallelen Bereich zu initialisieren, indem Sie mithilfe von [Omp_init_lock](3-run-time-library-functions.md#321-omp_init_lock-and-omp_init_nest_lock-functions).

```cpp
// A_13_omp_init_lock.cpp
// compile with: /openmp
#include <omp.h>

omp_lock_t *new_locks() {
   int i;
   omp_lock_t *lock = new omp_lock_t[1000];
   #pragma omp parallel for private(i)
   for (i = 0 ; i < 1000 ; i++)
      omp_init_lock(&lock[i]);

   return lock;
}

int main () {}
```
