---
title: OpenMP-Anweisungen
ms.date: 03/20/2019
f1_keywords:
- OpenMP directives
- atomic
- barrier
- critical
- flush
- for
- master
- ordered
- parallel
- section
- SECTIONS
- single
- threadprivate
helpviewer_keywords:
- OpenMP directives
- atomic OpenMP directive
- barrier OpenMP directive
- critical OpenMP directive
- flush OpenMP directive
- for OpenMP directive
- master OpenMP directive
- ordered OpenMP directive
- parallel OpenMP directive
- sections OpenMP directive
- single OpenMP directive
- threadprivate OpenMP directive
ms.assetid: 0562c263-344c-466d-843e-de830d918940
ms.openlocfilehash: d644b612c0c326692786c94046d799163dfbce8d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62362685"
---
# <a name="openmp-directives"></a>OpenMP-Anweisungen

Enthält Links zu Anweisungen, die in der OpenMP-API verwendet.

Visual C++ unterstützt die folgenden OpenMP-Anweisungen.

Für die parallele Arbeit-Freigabe:

|Direktive|Beschreibung|
|---------|-----------|
|[parallel](#parallel)|Definiert einen parallelen Bereich, also Code, die von mehreren Threads gleichzeitig ausgeführt werden.|
|[for](#for-openmp)|Bewirkt, dass die Arbeit einem `for` Schleife innerhalb eines parallelen Bereichs zwischen Threads aufgeteilt werden.|
|[Abschnitte](#sections-openmp)|Identifiziert die Codeabschnitte, die auf allen Threads aufgeteilt werden.|
|[single](#single)|Sie können angeben, dass ein Abschnitt des Codes in einem einzelnen Thread, der nicht unbedingt die master-Thread ausgeführt werden soll.|

Für Master und -Synchronisierung:

|Direktive|Beschreibung|
|---------|-----------|
|[master](#master)|Gibt an, dass nur die master-Thread einen Abschnitt des Programms ausgeführt werden soll.|
|[critical](#critical)|Gibt an, dass Code nur in einem Thread zu einem Zeitpunkt ausgeführt wird.|
|[barrier](#barrier)|Synchronisiert alle Threads in einem Team. Alle Threads anhalten die Barriere, bis alle Threads die Barriere ausführen.|
|[atomic](#atomic)|Gibt an, dass eine Speicheradresse, die automatisch aktualisiert werden.|
|[flush](#flush-openmp)|Gibt an, dass alle Threads die gleiche Ansicht der Arbeitsspeicher für alle freigegebenen Objekte.|
|[ordered](#ordered-openmp-directives)|Gibt an, diesen Code unter einem parallelisierten `for` Schleife ausgeführt werden soll, wie eine sequenzielle Schleife.|

Für Data-Umgebung:

|Direktive|Beschreibung|
|---------|-----------|
|[threadprivate](#threadprivate)|Gibt an, dass eine Variable einem Thread zugehörig ist.|

## <a name="atomic"></a>atomic

Gibt an, dass eine Speicheradresse, die automatisch aktualisiert werden.

```
#pragma omp atomic
   expression
```

### <a name="parameters"></a>Parameter

*expression*<br/>
Die Anweisung, die die *Lvalue*, deren Speicheradresse, die Sie für mehrere Schreibvorgänge schützen möchten.

### <a name="remarks"></a>Hinweise

Die `atomic` -Anweisung unterstützt keine Klauseln.

Weitere Informationen finden Sie unter [2.6.4 atomic erstellen](../../../parallel/openmp/2-6-4-atomic-construct.md).

### <a name="example"></a>Beispiel

```cpp
// omp_atomic.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

#define MAX 10

int main() {
   int count = 0;
   #pragma omp parallel num_threads(MAX)
   {
      #pragma omp atomic
      count++;
   }
   printf_s("Number of threads: %d\n", count);
}
```

```Output
Number of threads: 10
```

## <a name="barrier"></a>Barriere

Synchronisiert alle Threads in einem Team. Alle Threads anhalten die Barriere, bis alle Threads die Barriere ausführen.

```
#pragma omp barrier
```

### <a name="remarks"></a>Hinweise

Die `barrier` -Anweisung unterstützt keine Klauseln.

Weitere Informationen finden Sie unter [2.6.3 Barrier-Direktive](../../../parallel/openmp/2-6-3-barrier-directive.md).

### <a name="example"></a>Beispiel

Ein Beispiel zur Verwendung `barrier`, finden Sie unter [master](#master).

## <a name="critical"></a>Kritisch

Gibt an, dass der Code ist nur in einem Thread zu einem Zeitpunkt ausgeführt werden.

```
#pragma omp critical [(name)]
{
   code_block
}
```

### <a name="parameters"></a>Parameter

*name*<br/>
(Optional) Ein Name zur Identifizierung des kritischen Codes. Der Name muss in Klammern eingeschlossen werden.

### <a name="remarks"></a>Hinweise

Die `critical` -Anweisung unterstützt keine Klauseln.

Weitere Informationen finden Sie unter [2.6.2 kritische erstellen](../../../parallel/openmp/2-6-2-critical-construct.md).

### <a name="example"></a>Beispiel

```cpp
// omp_critical.cpp
// compile with: /openmp
#include <omp.h>
#include <stdio.h>
#include <stdlib.h>

#define SIZE 10

int main()
{
    int i;
    int max;
    int a[SIZE];

    for (i = 0; i < SIZE; i++)
    {
        a[i] = rand();
        printf_s("%d\n", a[i]);
    }

    max = a[0];
    #pragma omp parallel for num_threads(4)
        for (i = 1; i < SIZE; i++)
        {
            if (a[i] > max)
            {
                #pragma omp critical
                {
                    // compare a[i] and max again because max
                    // could have been changed by another thread after
                    // the comparison outside the critical section
                    if (a[i] > max)
                        max = a[i];
                }
            }
        }

    printf_s("max = %d\n", max);
}
```

```Output
41
18467
6334
26500
19169
15724
11478
29358
26962
24464
max = 29358
```

## <a name="flush-openmp"></a>flush

Gibt an, dass alle Threads die gleiche Ansicht der Arbeitsspeicher für alle freigegebenen Objekte.

```
#pragma omp flush [(var)]
```

### <a name="parameters"></a>Parameter

*var*<br/>
(Optional) Eine durch Trennzeichen getrennte Liste von Variablen, die Objekte darstellen, die Sie synchronisieren möchten. Wenn *Var* nicht angegeben ist, alle Arbeitsspeicher wird geleert.

### <a name="remarks"></a>Hinweise

Die `flush` -Anweisung unterstützt keine Klauseln.

Weitere Informationen finden Sie unter [2.6.5 flush-Direktive](../../../parallel/openmp/2-6-5-flush-directive.md).

### <a name="example"></a>Beispiel

```cpp
// omp_flush.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

void read(int *data) {
   printf_s("read data\n");
   *data = 1;
}

void process(int *data) {
   printf_s("process data\n");
   (*data)++;
}

int main() {
   int data;
   int flag;

   flag = 0;

   #pragma omp parallel sections num_threads(2)
   {
      #pragma omp section
      {
         printf_s("Thread %d: ", omp_get_thread_num( ));
         read(&data);
         #pragma omp flush(data)
         flag = 1;
         #pragma omp flush(flag)
         // Do more work.
      }

      #pragma omp section
      {
         while (!flag) {
            #pragma omp flush(flag)
         }
         #pragma omp flush(data)

         printf_s("Thread %d: ", omp_get_thread_num( ));
         process(&data);
         printf_s("data = %d\n", data);
      }
   }
}
```

```Output
Thread 0: read data
Thread 1: process data
data = 2
```

## <a name="for-openmp"></a>für

Bewirkt, dass die Arbeit einem `for` Schleife innerhalb eines parallelen Bereichs zwischen Threads aufgeteilt werden.

```
#pragma omp [parallel] for [clauses]
   for_statement
```

### <a name="parameters"></a>Parameter

*clauses*<br/>
(Optional) NULL oder mehr Klauseln, finden Sie unter den **"Hinweise"** Abschnitt.

*for_statement*<br/>
Ein `for` Schleife. Nicht definiertem Verhalten führt, wenn Benutzer im code die `for` Schleife ändert die Indexvariable.

### <a name="remarks"></a>Hinweise

Die `for` -Anweisung unterstützt die folgenden Klauseln:

- [private](openmp-clauses.md#private-openmp)
- [firstprivate](openmp-clauses.md#firstprivate)
- [lastprivate](openmp-clauses.md#lastprivate)
- [reduction](openmp-clauses.md#reduction)
- [ordered](openmp-clauses.md#ordered-openmp-clauses)
- [schedule](openmp-clauses.md#schedule)
- [nowait](openmp-clauses.md#nowait)

Wenn `parallel` ebenfalls angegeben wird, `clauses` kann jede beliebige Klausel von akzeptiert die `parallel` oder `for` Anweisungen, mit Ausnahme von `nowait`.

Weitere Informationen finden Sie unter [2.4.1 for-Konstrukt](../../../parallel/openmp/2-4-1-for-construct.md).

### <a name="example"></a>Beispiel

```cpp
// omp_for.cpp
// compile with: /openmp
#include <stdio.h>
#include <math.h>
#include <omp.h>

#define NUM_THREADS 4
#define NUM_START 1
#define NUM_END 10

int main() {
   int i, nRet = 0, nSum = 0, nStart = NUM_START, nEnd = NUM_END;
   int nThreads = 0, nTmp = nStart + nEnd;
   unsigned uTmp = (unsigned((abs(nStart - nEnd) + 1)) *
                               unsigned(abs(nTmp))) / 2;
   int nSumCalc = uTmp;

   if (nTmp < 0)
      nSumCalc = -nSumCalc;

   omp_set_num_threads(NUM_THREADS);

   #pragma omp parallel default(none) private(i) shared(nSum, nThreads, nStart, nEnd)
   {
      #pragma omp master
      nThreads = omp_get_num_threads();

      #pragma omp for
      for (i=nStart; i<=nEnd; ++i) {
            #pragma omp atomic
            nSum += i;
      }
   }

   if  (nThreads == NUM_THREADS) {
      printf_s("%d OpenMP threads were used.\n", NUM_THREADS);
      nRet = 0;
   }
   else {
      printf_s("Expected %d OpenMP threads, but %d were used.\n",
               NUM_THREADS, nThreads);
      nRet = 1;
   }

   if (nSum != nSumCalc) {
      printf_s("The sum of %d through %d should be %d, "
               "but %d was reported!\n",
               NUM_START, NUM_END, nSumCalc, nSum);
      nRet = 1;
   }
   else
      printf_s("The sum of %d through %d is %d\n",
               NUM_START, NUM_END, nSum);
}
```

```Output
4 OpenMP threads were used.
The sum of 1 through 10 is 55
```

## <a name="master"></a>Master

Gibt an, dass nur die master-Thread einen Abschnitt des Programms ausgeführt werden soll.

```
#pragma omp master
{
   code_block
}
```

### <a name="remarks"></a>Hinweise

Die `master` -Anweisung unterstützt keine Klauseln.

Die [einzelne](#single) -Direktive können Sie angeben, dass ein Abschnitt des Codes in einem einzelnen Thread, der nicht unbedingt die master-Thread ausgeführt werden soll.

Weitere Informationen finden Sie unter [2.6.1 master-Konstrukt](../../../parallel/openmp/2-6-1-master-construct.md).

### <a name="example"></a>Beispiel

```cpp
// omp_master.cpp
// compile with: /openmp
#include <omp.h>
#include <stdio.h>

int main( )
{
    int a[5], i;

    #pragma omp parallel
    {
        // Perform some computation.
        #pragma omp for
        for (i = 0; i < 5; i++)
            a[i] = i * i;

        // Print intermediate results.
        #pragma omp master
            for (i = 0; i < 5; i++)
                printf_s("a[%d] = %d\n", i, a[i]);

        // Wait.
        #pragma omp barrier

        // Continue with the computation.
        #pragma omp for
        for (i = 0; i < 5; i++)
            a[i] += i;
    }
}
```

```Output
a[0] = 0
a[1] = 1
a[2] = 4
a[3] = 9
a[4] = 16
```

## <a name="ordered-openmp-directives"></a>Sortiert

Gibt an, diesen Code unter einem parallelisierten `for` Schleife ausgeführt werden soll, wie eine sequenzielle Schleife.

```
#pragma omp ordered
   structured-block
```

### <a name="remarks"></a>Hinweise

Die `ordered` Richtlinie im dynamischen Wertebereich liegen eine [für](#for-openmp) oder `parallel for` erstellen, die mit einer `ordered` Klausel.

Die `ordered` -Anweisung unterstützt keine Klauseln.

Weitere Informationen finden Sie unter [2.6.6 ordered-Konstrukt](../../../parallel/openmp/2-6-6-ordered-construct.md).

### <a name="example"></a>Beispiel

```cpp
// omp_ordered.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

static float a[1000], b[1000], c[1000];

void test(int first, int last)
{
    #pragma omp for schedule(static) ordered
    for (int i = first; i <= last; ++i) {
        // Do something here.
        if (i % 2)
        {
            #pragma omp ordered
            printf_s("test() iteration %d\n", i);
        }
    }
}

void test2(int iter)
{
    #pragma omp ordered
    printf_s("test2() iteration %d\n", iter);
}

int main( )
{
    int i;
    #pragma omp parallel
    {
        test(1, 8);
        #pragma omp for ordered
        for (i = 0 ; i < 5 ; i++)
            test2(i);
    }
}
```

```Output
test() iteration 1
test() iteration 3
test() iteration 5
test() iteration 7
test2() iteration 0
test2() iteration 1
test2() iteration 2
test2() iteration 3
test2() iteration 4
```

## <a name="parallel"></a>Parallele

Definiert einen parallelen Bereich, also Code, die von mehreren Threads gleichzeitig ausgeführt werden.

```
#pragma omp parallel [clauses]
{
   code_block
}
```

### <a name="parameters"></a>Parameter

*clauses*<br/>
(Optional) NULL oder mehr Klauseln, finden Sie unter den **"Hinweise"** Abschnitt.

### <a name="remarks"></a>Hinweise

Die `parallel` -Anweisung unterstützt die folgenden Klauseln:

- [if](openmp-clauses.md#if-openmp)
- [private](openmp-clauses.md#private-openmp)
- [firstprivate](openmp-clauses.md#firstprivate)
- [default](openmp-clauses.md#default-openmp)
- [shared](openmp-clauses.md#shared-openmp)
- [copyin](openmp-clauses.md#copyin)
- [reduction](openmp-clauses.md#reduction)
- [num_threads](openmp-clauses.md#num-threads)

`parallel` kann auch verwendet werden, mit der [für](#for-openmp) und [Abschnitte](#sections-openmp) Anweisungen.

Weitere Informationen finden Sie unter [2.3 parallel-Konstrukt](../../../parallel/openmp/2-3-parallel-construct.md).

### <a name="example"></a>Beispiel

Im folgende Beispiel veranschaulicht die legen Sie die Anzahl von Threads und ein paralleles Bereichs zu definieren. Die Anzahl von Threads entspricht standardmäßig auf die Anzahl der logischen Prozessoren auf dem Computer zur Verfügung. Z. B. Wenn Sie einen Computer mit einem physischen Prozessor, die Hyperthreading aktiviert wurde verfügen, wird es zwei logischen Prozessoren und zwei Threads haben. Die Reihenfolge der Ausgabe kann auf verschiedenen Computern variieren.

```cpp
// omp_parallel.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main() {
   #pragma omp parallel num_threads(4)
   {
      int i = omp_get_thread_num();
      printf_s("Hello from thread %d\n", i);
   }
}
```

```Output
Hello from thread 0
Hello from thread 1
Hello from thread 2
Hello from thread 3
```

## <a name="sections-openmp"></a>Abschnitte

Identifiziert die Codeabschnitte, die auf allen Threads aufgeteilt werden.

```
#pragma omp [parallel] sections [clauses]
{
   #pragma omp section
   {
      code_block
   }
}
```

### <a name="parameters"></a>Parameter

*clauses*<br/>
(Optional) NULL oder mehr Klauseln, finden Sie unter den **"Hinweise"** Abschnitt.

### <a name="remarks"></a>Hinweise

Die `sections` Richtlinie kann 0 (null) oder mehrere enthalten `section` Anweisungen.

Die `sections` -Anweisung unterstützt die folgenden Klauseln:

- [private](openmp-clauses.md#private-openmp)
- [firstprivate](openmp-clauses.md#firstprivate)
- [lastprivate](openmp-clauses.md#lastprivate)
- [reduction](openmp-clauses.md#reduction)
- [nowait](openmp-clauses.md#nowait)

Wenn `parallel` ebenfalls angegeben wird, `clauses` kann jede beliebige Klausel von akzeptiert die `parallel` oder `sections` Anweisungen, mit Ausnahme von `nowait`.

Weitere Informationen finden Sie unter [2.4.2 sections-Konstrukt](../../../parallel/openmp/2-4-2-sections-construct.md).

### <a name="example"></a>Beispiel

```cpp
// omp_sections.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main() {
    #pragma omp parallel sections num_threads(4)
    {
        printf_s("Hello from thread %d\n", omp_get_thread_num());
        #pragma omp section
        printf_s("Hello from thread %d\n", omp_get_thread_num());
    }
}
```

```Output
Hello from thread 0
Hello from thread 0
```

## <a name="single"></a>einzelne

Sie können angeben, dass ein Abschnitt des Codes in einem einzelnen Thread, der nicht unbedingt die master-Thread ausgeführt werden soll.

```
#pragma omp single [clauses]
{
   code_block
}
```

### <a name="parameters"></a>Parameter

*clauses*<br/>
(Optional) NULL oder mehr Klauseln, finden Sie unter den **"Hinweise"** Abschnitt.

### <a name="remarks"></a>Hinweise

Die `single` -Anweisung unterstützt die folgenden Klauseln:

- [private](openmp-clauses.md#private-openmp)
- [firstprivate](openmp-clauses.md#firstprivate)
- [copyprivate](openmp-clauses.md#copyprivate)
- [nowait](openmp-clauses.md#nowait)

Die [master](#master) -Direktive können Sie angeben, dass ein Abschnitt des Codes nur für die master-Thread ausgeführt werden sollen.

Weitere Informationen finden Sie unter [2.4.3 einzelne erstellen](../../../parallel/openmp/2-4-3-single-construct.md).

### <a name="example"></a>Beispiel

```cpp
// omp_single.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main() {
   #pragma omp parallel num_threads(2)
   {
      #pragma omp single
      // Only a single thread can read the input.
      printf_s("read input\n");

      // Multiple threads in the team compute the results.
      printf_s("compute results\n");

      #pragma omp single
      // Only a single thread can write the output.
      printf_s("write output\n");
    }
}
```

```Output
read input
compute results
compute results
write output
```

## <a name="threadprivate"></a>threadprivate

Gibt an, dass eine Variable einem Thread zugehörig ist.

```
#pragma omp threadprivate(var)
```

### <a name="parameters"></a>Parameter

*var*<br/>
Eine durch Trennzeichen getrennte Liste von Variablen, die Sie an einen Thread als privat kennzeichnen möchten. *Var* muss entweder eine globale oder Namespace-bezogenen Variable oder eine statische lokale Variable sein.

### <a name="remarks"></a>Hinweise

Die `threadprivate` -Anweisung unterstützt keine Klauseln.

Der `threadprivate` Richtlinie basiert auf der [Thread](../../../cpp/thread.md) -Attribut mit dem [__declspec](../../../cpp/declspec.md) -Schlüsselwort, Grenzwerte für `__declspec(thread)` gelten für `threadprivate`. Z. B. eine `threadprivate` Variable befindet sich in jedem Thread im Prozess gestartet, nicht nur die Threads, die Teil eines Thread-Teams, die von einem parallelen Bereich Anwendungen erzeugt werden. Achten Sie auf Dieses Implementierungsdetail; Sie können feststellen, dass Konstruktoren für eine `threadprivate` einen benutzerdefinierten Typ heißen Weitere häufig wird erwartet.

Können Sie `threadprivate` in einer DLL, die beim Starten des Prozesses statisch geladen wird, jedoch können keine `threadprivate` in einer DLL, die über geladen werden [LoadLibrary](/windows/desktop/api/libloaderapi/nf-libloaderapi-loadlibrarya) wie z.B. DLLs, die mit geladen werden  [ /DELAYLOAD (Verzögerung Laden von Import)](../../../build/reference/delayload-delay-load-import.md), die auch verwendet `LoadLibrary`.

Ein `threadprivate` der Variable ein *"destructible"* ist nicht garantiert, dass Typ sein Destruktor aufgerufen werden. Zum Beispiel:

```
struct MyType
{
    ~MyType();
};

MyType threaded_var;
#pragma omp threadprivate(threaded_var)
int main()
{
    #pragma omp parallel
    {}
}
```

Benutzer haben keine Kontrolle, wenn die Threads enthalten sind, die den parallelen Bereich beendet wird. Wenn diese Threads vorhanden sind, wenn der Prozess beendet wird, die Threads nicht, über das Beenden des Prozesses informiert und der Destruktor nicht aufgerufen, für die `threaded_var` auf einem beliebigen Thread mit der Ausnahme, die beendet wird (Hier wird der primäre Thread). So können Code auf ordnungsgemäße Zerstörung von verlassen dürfen nicht `threadprivate` Variablen.

Weitere Informationen finden Sie unter [2.7.1 Threadprivate-Direktive](../../../parallel/openmp/2-7-1-threadprivate-directive.md).

### <a name="example"></a>Beispiel

Ein Beispiel der Verwendung von `threadprivate`, finden Sie unter [private](openmp-clauses.md#private-openmp).
