---
title: OpenMP-Funktionen
ms.date: 03/20/2019
f1_keywords:
- OpenMP functions
- omp_destroy_lock
- omp_destroy_nest_lock
- omp_get_dynamic
- omp_get_max_threads
- omp_get_nested
- omp_get_num_procs
- omp_get_num_threads
- omp_get_thread_num
- omp_get_wtick
- omp_get_wtime
- omp_in_parallel
- omp_init_lock
- omp_init_nest_lock
- omp_set_dynamic
- omp_set_lock
- omp_set_nest_lock
- omp_set_nested
- omp_set_num_threads
- omp_test_lock
- omp_test_nest_lock
- omp_unset_lock
- omp_unset_nest_lock
helpviewer_keywords:
- OpenMP functions
- omp_destroy_lock OpenMP function
- omp_destroy_nest_lock OpenMP function
- omp_get_dynamic OpenMP function
- omp_get_max_threads OpenMP function
- omp_get_nested OpenMP function
- omp_get_num_procs OpenMP function
- omp_get_num_threads OpenMP function
- omp_get_thread_num OpenMP function
- omp_get_wtick OpenMP function
- omp_get_wtime OpenMP function
- omp_in_parallel OpenMP function
- omp_init_lock OpenMP function
- omp_init_nest_lock OpenMP function
- omp_set_dynamic OpenMP function
- omp_set_lock OpenMP function
- omp_set_nest_lock OpenMP function
- omp_set_nested OpenMP function
- omp_set_num_threads OpenMP function
- omp_test_lock OpenMP function
- omp_test_nest_lock OpenMP function
- omp_unset_lock OpenMP function
- omp_unset_nest_lock OpenMP function
ms.assetid: a55a2e5c-a260-44ee-bbd6-de7e2351b384
ms.openlocfilehash: 1bf0e08f3b28368d9aea5438b3036ac8a0283735
ms.sourcegitcommit: 14b292596bc9b9b883a9c58cd3e366b282a1f7b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2019
ms.locfileid: "60124979"
---
# <a name="openmp-functions"></a>OpenMP-Funktionen

Enthält Links zu Funktionen, die in der OpenMP-API verwendet.

Das visuelle Element C++ -Implementierung des OpenMP umfasst die folgenden Funktionen und Datentypen.

Für die Ausführung der Umgebung:

|Funktion|Beschreibung|
|--------|-----------|
|[omp_set_num_threads](#omp-set-num-threads)|Die Anzahl der Threads in zukünftigen parallelen Bereichen, legt fest, es sei denn, durch Überschreiben einer [Num_threads](openmp-clauses.md#num-threads) Klausel.|
|[omp_get_num_threads](#omp-get-num-threads)|Gibt die Anzahl der Threads in den parallelen Bereich zurück.|
|[omp_get_max_threads](#omp-get-max-threads)|Gibt eine ganze Zahl, die gleich oder größer als die Anzahl der Threads, die zur Verfügung, wenn einem parallelen Bereich ohne [Num_threads](openmp-clauses.md#num-threads) an diesem Punkt im Code definiert wurden.|
|[omp_get_thread_num](#omp-get-thread-num)|Gibt die Thread-Anzahl der ausgeführten Threads in die Thread-Team.|
|[omp_get_num_procs](#omp-get-num-procs)|Gibt die Anzahl der Prozessoren, die verfügbar sind, wenn die Funktion aufgerufen wird.|
|[omp_in_parallel](#omp-in-parallel)|Gibt, die ungleich NULL, wenn innerhalb eines parallelen Bereichs aufgerufen.|
|[omp_set_dynamic](#omp-set-dynamic)|Gibt an, dass die Anzahl der Threads, die in zukünftigen parallele Regionen zur Verfügung, die von der Laufzeit angepasst werden kann.|
|[omp_get_dynamic](#omp-get-dynamic)|Gibt einen Wert, der angibt, ob die Anzahl der Threads, die in zukünftigen parallele Regionen zur Verfügung, die von der Laufzeit angepasst werden kann.|
|[omp_set_nested](#omp-set-nested)|Ermöglicht geschachtelte Parallelität.|
|[omp_get_nested](#omp-get-nested)|Gibt einen Wert, der angibt, ob geschachtelte Parallelität aktiviert ist.|

Sperre:

|Funktion|Beschreibung|
|--------|-----------|
|[omp_init_lock](#omp-init-lock)|Initialisiert eine einfache Sperre an.|
|[omp_init_nest_lock](#omp-init-nest-lock)|Initialisiert eine Sperre an.|
|[omp_destroy_lock](#omp-destroy-lock)|Hebt die Initialisierung einer Sperre.|
|[omp_destroy_nest_lock](#omp-destroy-nest-lock)|Hebt die Initialisierung einer omp_nest_lock_t-Sperre.|
|[omp_set_lock](#omp-set-lock)|Blöcke Threadausführung, bis eine Sperre verfügbar ist.|
|[omp_set_nest_lock](#omp-set-nest-lock)|Blöcke Threadausführung, bis eine Sperre verfügbar ist.|
|[omp_unset_lock](#omp-unset-lock)|Gibt eine Sperre frei.|
|[omp_unset_nest_lock](#omp-unset-nest-lock)|Gibt eine omp_nest_lock_t-Sperre frei.|
|[omp_test_lock](#omp-test-lock)|Versucht, eine Sperre festzulegen, aber nicht die Ausführung des Threads zu blockieren.|
|[omp_test_nest_lock](#omp-test-nest-lock)|Versucht, eine omp_nest_lock_t-Sperre festzulegen, aber nicht die Ausführung des Threads zu blockieren.|

|Datentyp|Beschreibung|
|---------|-----------|
|`omp_lock_t`|Ein Typ, der den Status einer Sperre, gibt an, ob die Sperre verfügbar ist oder wenn ein Thread eine Sperre besitzt enthält.|
|`omp_nest_lock_t`|Ein Typ, der eines der folgenden Angaben zu einer Sperre enthält:, ob die Sperre verfügbar ist, und die Identität des Threads, die Sperre und die Schachtelung Anzahl besitzt.|

Für die Routinen zur zeitlichen Steuerung:

|Funktion|Beschreibung|
|--------|-----------|
|[omp_get_wtime](#omp-get-wtime)|Gibt ein Wert in Sekunden, der Zeit von einem bestimmten Punkt verstrichen ist.|
|[omp_get_wtick](#omp-get-wtick)|Gibt die Anzahl der Sekunden zwischen den Teilstrichen Prozessor zurück.|

## <a name="omp-destroy-lock"></a>omp_destroy_lock

Hebt die Initialisierung einer Sperre.

```
void omp_destroy_lock(
   omp_lock_t *lock
);
```

### <a name="parameters"></a>Parameter

*lock*<br/>
Eine Variable vom Typ `omp_lock_t` , die mit initialisiert wurde [Omp_init_lock](#omp-init-lock).

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [3.2.2 Omp_destroy_lock- und Omp_destroy_nest_lock-Funktionen](../../../parallel/openmp/3-2-2-omp-destroy-lock-and-omp-destroy-nest-lock-functions.md).

### <a name="example"></a>Beispiel

Finden Sie unter [Omp_init_lock](#omp-init-lock) ein Beispiel der Verwendung von `omp_destroy_lock`.

## <a name="omp-destroy-nest-lock"></a>omp_destroy_nest_lock

Hebt die Initialisierung einer omp_nest_lock_t-Sperre.

```
void omp_destroy_nest_lock(
   omp_nest_lock_t *lock
);
```

### <a name="parameters"></a>Parameter

*lock*<br/>
Eine Variable vom Typ `omp_nest_lock_t` , die mit initialisiert wurde [Omp_init_nest_lock](#omp-init-nest-lock).

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [3.2.2 Omp_destroy_lock- und Omp_destroy_nest_lock-Funktionen](../../../parallel/openmp/3-2-2-omp-destroy-lock-and-omp-destroy-nest-lock-functions.md).

### <a name="example"></a>Beispiel

Finden Sie unter [Omp_init_nest_lock](#omp-init-nest-lock) ein Beispiel der Verwendung von `omp_destroy_nest_lock`.

## <a name="omp-get-dynamic"></a>omp_get_dynamic

Gibt einen Wert, der angibt, ob die Anzahl der Threads, die in zukünftigen parallele Regionen zur Verfügung, die von der Laufzeit angepasst werden kann.

```
int omp_get_dynamic();
```

### <a name="return-value"></a>Rückgabewert

Ein Wert ungleich NULL bedeutet, dass die Threads dynamisch angepasst werden.

### <a name="remarks"></a>Hinweise

Dynamische Anpassung des Threads wird angegeben, mit [Omp_set_dynamic](#omp-set-dynamic) und [OMP_DYNAMIC](openmp-environment-variables.md#omp-dynamic).

Weitere Informationen finden Sie unter [3.1.7 Omp_set_dynamic-Funktion](../../../parallel/openmp/3-1-7-omp-set-dynamic-function.md).

### <a name="example"></a>Beispiel

Finden Sie unter [Omp_set_dynamic](#omp-set-dynamic) ein Beispiel der Verwendung von `omp_get_dynamic`.

## <a name="omp-get-max-threads"></a>omp_get_max_threads

Gibt eine ganze Zahl, die gleich oder größer als die Anzahl der Threads, die zur Verfügung, wenn einem parallelen Bereich ohne [Num_threads](openmp-clauses.md#num-threads) an diesem Punkt im Code definiert wurden.

```
int omp_get_max_threads( )
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [3.1.3 Omp_get_max_threads-Funktion](../../../parallel/openmp/3-1-3-omp-get-max-threads-function.md).

### <a name="example"></a>Beispiel

```cpp
// omp_get_max_threads.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main( )
{
    omp_set_num_threads(8);
    printf_s("%d\n", omp_get_max_threads( ));
    #pragma omp parallel
        #pragma omp master
        {
            printf_s("%d\n", omp_get_max_threads( ));
        }

    printf_s("%d\n", omp_get_max_threads( ));

    #pragma omp parallel num_threads(3)
        #pragma omp master
        {
            printf_s("%d\n", omp_get_max_threads( ));
        }

    printf_s("%d\n", omp_get_max_threads( ));
}
```

```Output
8
8
8
8
8
```

## <a name="omp-get-nested"></a>omp_get_nested

Gibt einen Wert, der angibt, ob geschachtelte Parallelität aktiviert ist.

```
int omp_get_nested( );
```

### <a name="return-value"></a>Rückgabewert

Ein Wert ungleich NULL bedeutet, dass geschachtelte Parallelität aktiviert ist.

### <a name="remarks"></a>Hinweise

Geschachtelte Parallelität wird angegeben, mit [Omp_set_nested](#omp-set-nested) und [OMP_NESTED](openmp-environment-variables.md#omp-nested).

Weitere Informationen finden Sie unter [3.1.10 Omp_get_nested-Funktion](../../../parallel/openmp/3-1-10-omp-get-nested-function.md).

### <a name="example"></a>Beispiel

Finden Sie unter [Omp_set_nested](#omp-set-nested) ein Beispiel der Verwendung von `omp_get_nested`.

## <a name="omp-get-num-procs"></a>omp_get_num_procs

Gibt die Anzahl der Prozessoren, die verfügbar sind, wenn die Funktion aufgerufen wird.

```
int omp_get_num_procs();
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [3.1.5 Omp_get_num_procs-Funktion](../../../parallel/openmp/3-1-5-omp-get-num-procs-function.md).

### <a name="example"></a>Beispiel

```cpp
// omp_get_num_procs.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main( )
{
    printf_s("%d\n", omp_get_num_procs( ));
    #pragma omp parallel
        #pragma omp master
        {
            printf_s("%d\n", omp_get_num_procs( ));
        }
}
```

```Output
// Expect the following output when the example is run on a two-processor machine:
2
2
```

## <a name="omp-get-num-threads"></a>omp_get_num_threads

Gibt die Anzahl der Threads in den parallelen Bereich zurück.

```
int omp_get_num_threads( );
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [3.1.2 Omp_get_num_threads-Funktion](../../../parallel/openmp/3-1-2-omp-get-num-threads-function.md).

### <a name="example"></a>Beispiel

```cpp
// omp_get_num_threads.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main()
{
    omp_set_num_threads(4);
    printf_s("%d\n", omp_get_num_threads( ));
    #pragma omp parallel
        #pragma omp master
        {
            printf_s("%d\n", omp_get_num_threads( ));
        }

    printf_s("%d\n", omp_get_num_threads( ));

    #pragma omp parallel num_threads(3)
        #pragma omp master
        {
            printf_s("%d\n", omp_get_num_threads( ));
        }

    printf_s("%d\n", omp_get_num_threads( ));
}
```

```Output
1
4
1
3
1
```

## <a name="omp-get-thread-num"></a>omp_get_thread_num

Gibt die Thread-Anzahl der ausgeführten Threads in die Thread-Team.

```
int omp_get_thread_num( );
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [3.1.4 Omp_get_thread_num-Funktion](../../../parallel/openmp/3-1-4-omp-get-thread-num-function.md).

### <a name="example"></a>Beispiel

Finden Sie unter [parallele](openmp-directives.md#parallel) ein Beispiel der Verwendung von `omp_get_thread_num`.

## <a name="omp-get-wtick"></a>omp_get_wtick

Gibt die Anzahl der Sekunden zwischen den Teilstrichen Prozessor zurück.

```
double omp_get_wtick( );
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [3.3.2 Omp_get_wtick-Funktion](../../../parallel/openmp/3-3-2-omp-get-wtick-function.md).

### <a name="example"></a>Beispiel

Finden Sie unter [Omp_get_wtime](#omp-get-wtime) ein Beispiel der Verwendung von `omp_get_wtick`.

## <a name="omp-get-wtime"></a>omp_get_wtime

Gibt ein Wert in Sekunden, der Zeit von einem bestimmten Punkt verstrichen ist.

```
double omp_get_wtime( );
```

### <a name="return-value"></a>Rückgabewert

Gibt zurück, der einige beliebige, jedoch konsistent Zeitpunkt ein Wert in Sekunden, der Zeit vergangen ist.

### <a name="remarks"></a>Hinweise

Dieser Punkt wird während der programmausführung, wodurch der bevorstehenden Vergleiche konsistent bleiben.

Weitere Informationen finden Sie unter [3.3.1 Omp_get_wtime-Funktion](../../../parallel/openmp/3-3-1-omp-get-wtime-function.md).

### <a name="example"></a>Beispiel

```cpp
// omp_get_wtime.cpp
// compile with: /openmp
#include "omp.h"
#include <stdio.h>
#include <windows.h>

int main() {
    double start = omp_get_wtime( );
    Sleep(1000);
    double end = omp_get_wtime( );
    double wtick = omp_get_wtick( );

    printf_s("start = %.16g\nend = %.16g\ndiff = %.16g\n",
             start, end, end - start);

    printf_s("wtick = %.16g\n1/wtick = %.16g\n",
             wtick, 1.0 / wtick);
}
```

```Output
start = 594255.3671159324
end = 594256.3664474116
diff = 0.9993314791936427
wtick = 2.793651148400146e-007
1/wtick = 3579545
```

## <a name="omp-in-parallel"></a>omp_in_parallel

Gibt, die ungleich NULL, wenn innerhalb eines parallelen Bereichs aufgerufen.

```
int omp_in_parallel( );
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [3.1.6 Omp_in_parallel-Funktion](../../../parallel/openmp/3-1-6-omp-in-parallel-function.md).

### <a name="example"></a>Beispiel

```cpp
// omp_in_parallel.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main( )
{
    omp_set_num_threads(4);
    printf_s("%d\n", omp_in_parallel( ));

    #pragma omp parallel
        #pragma omp master
        {
            printf_s("%d\n", omp_in_parallel( ));
        }
}
```

```Output
0
1
```

## <a name="omp-init-lock"></a>omp_init_lock

Initialisiert eine einfache Sperre an.

```
void omp_init_lock(
   omp_lock_t *lock
);
```

### <a name="parameters"></a>Parameter

*lock*<br/>
Eine Variable des Typs `omp_lock_t`.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [3.2.1 Omp_init_lock and Omp_init_nest_lock-Funktionen](../../../parallel/openmp/3-2-1-omp-init-lock-and-omp-init-nest-lock-functions.md).

### <a name="example"></a>Beispiel

```cpp
// omp_init_lock.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

omp_lock_t my_lock;

int main() {
   omp_init_lock(&my_lock);

   #pragma omp parallel num_threads(4)
   {
      int tid = omp_get_thread_num( );
      int i, j;

      for (i = 0; i < 5; ++i) {
         omp_set_lock(&my_lock);
         printf_s("Thread %d - starting locked region\n", tid);
         printf_s("Thread %d - ending locked region\n", tid);
         omp_unset_lock(&my_lock);
      }
   }

   omp_destroy_lock(&my_lock);
}
```

```Output
Thread 0 - starting locked region
Thread 0 - ending locked region
Thread 0 - starting locked region
Thread 0 - ending locked region
Thread 0 - starting locked region
Thread 0 - ending locked region
Thread 0 - starting locked region
Thread 0 - ending locked region
Thread 0 - starting locked region
Thread 0 - ending locked region
Thread 1 - starting locked region
Thread 1 - ending locked region
Thread 1 - starting locked region
Thread 1 - ending locked region
Thread 1 - starting locked region
Thread 1 - ending locked region
Thread 1 - starting locked region
Thread 1 - ending locked region
Thread 1 - starting locked region
Thread 1 - ending locked region
Thread 2 - starting locked region
Thread 2 - ending locked region
Thread 2 - starting locked region
Thread 2 - ending locked region
Thread 2 - starting locked region
Thread 2 - ending locked region
Thread 2 - starting locked region
Thread 2 - ending locked region
Thread 2 - starting locked region
Thread 2 - ending locked region
Thread 3 - starting locked region
Thread 3 - ending locked region
Thread 3 - starting locked region
Thread 3 - ending locked region
Thread 3 - starting locked region
Thread 3 - ending locked region
Thread 3 - starting locked region
Thread 3 - ending locked region
Thread 3 - starting locked region
Thread 3 - ending locked region
```

## <a name="omp-init-nest-lock"></a>omp_init_nest_lock

Initialisiert eine Sperre an.

```
void omp_init_nest_lock(
   omp_nest_lock_t *lock
);
```

### <a name="parameters"></a>Parameter

*lock*<br/>
Eine Variable des Typs `omp_nest_lock_t`.

### <a name="remarks"></a>Hinweise

Die Anzahl die ersten Schachtelungsebene ist 0 (null).

Weitere Informationen finden Sie unter [3.2.1 Omp_init_lock and Omp_init_nest_lock-Funktionen](../../../parallel/openmp/3-2-1-omp-init-lock-and-omp-init-nest-lock-functions.md).

### <a name="example"></a>Beispiel

```cpp
// omp_init_nest_lock.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

omp_nest_lock_t my_lock;

void Test() {
   int tid = omp_get_thread_num( );
   omp_set_nest_lock(&my_lock);
   printf_s("Thread %d - starting nested locked region\n", tid);
   printf_s("Thread %d - ending nested locked region\n", tid);
   omp_unset_nest_lock(&my_lock);
}

int main() {
   omp_init_nest_lock(&my_lock);

   #pragma omp parallel num_threads(4)
   {
      int i, j;

      for (i = 0; i < 5; ++i) {
         omp_set_nest_lock(&my_lock);
            if (i % 3)
               Test();
            omp_unset_nest_lock(&my_lock);
        }
    }

    omp_destroy_nest_lock(&my_lock);
}
```

```Output
Thread 0 - starting nested locked region
Thread 0 - ending nested locked region
Thread 0 - starting nested locked region
Thread 0 - ending nested locked region
Thread 3 - starting nested locked region
Thread 3 - ending nested locked region
Thread 3 - starting nested locked region
Thread 3 - ending nested locked region
Thread 3 - starting nested locked region
Thread 3 - ending nested locked region
Thread 2 - starting nested locked region
Thread 2 - ending nested locked region
Thread 2 - starting nested locked region
Thread 2 - ending nested locked region
Thread 2 - starting nested locked region
Thread 2 - ending nested locked region
Thread 1 - starting nested locked region
Thread 1 - ending nested locked region
Thread 1 - starting nested locked region
Thread 1 - ending nested locked region
Thread 1 - starting nested locked region
Thread 1 - ending nested locked region
Thread 0 - starting nested locked region
Thread 0 - ending nested locked region
```

## <a name="omp-set-dynamic"></a>omp_set_dynamic

Gibt an, dass die Anzahl der Threads, die in zukünftigen parallele Regionen zur Verfügung, die von der Laufzeit angepasst werden kann.

```
void omp_set_dynamic(
   int val
);
```

### <a name="parameters"></a>Parameter

*val*<br/>
Ein Wert, der angibt, ob die Anzahl der Threads, die in zukünftigen parallele Regionen zur Verfügung, die von der Laufzeit angepasst werden kann. Wert ungleich null der Common Language Runtime die Anzahl der Threads, wenn der Wert 0 anpassen kann, wird nicht die Anzahl der Threads von die Laufzeit dynamisch anpassen.

### <a name="remarks"></a>Hinweise

Die Anzahl von Threads wird durch festgelegten Wert nie übersteigen [Omp_set_num_threads](#omp-set-num-threads) oder [OMP_NUM_THREADS](openmp-environment-variables.md#omp-num-threads).

Verwendung [Omp_get_dynamic](#omp-get-dynamic) zum Anzeigen der aktuellen Einstellung des `omp_set_dynamic`.

Die Einstellung für `omp_set_dynamic` überschreibt die Einstellung der [OMP_DYNAMIC](openmp-environment-variables.md#omp-dynamic) -Umgebungsvariablen angegeben.

Weitere Informationen finden Sie unter [3.1.7 Omp_set_dynamic-Funktion](../../../parallel/openmp/3-1-7-omp-set-dynamic-function.md).

### <a name="example"></a>Beispiel

```cpp
// omp_set_dynamic.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main()
{
    omp_set_dynamic(9);
    omp_set_num_threads(4);
    printf_s("%d\n", omp_get_dynamic( ));
    #pragma omp parallel
        #pragma omp master
        {
            printf_s("%d\n", omp_get_dynamic( ));
        }
}
```

```Output
1
1
```

## <a name="omp-set-lock"></a>omp_set_lock

Blöcke Threadausführung, bis eine Sperre verfügbar ist.

```
void omp_set_lock(
   omp_lock_t *lock
);
```

### <a name="parameters"></a>Parameter

*lock*<br/>
Eine Variable vom Typ `omp_lock_t` , die mit initialisiert wurde [Omp_init_lock](#omp-init-lock).

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [3.2.3 Omp_set_lock- und Omp_set_nest_lock-Funktionen](../../../parallel/openmp/3-2-3-omp-set-lock-and-omp-set-nest-lock-functions.md).

### <a name="examples"></a>Beispiele

Finden Sie unter [Omp_init_lock](#omp-init-lock) ein Beispiel der Verwendung von `omp_set_lock`.

## <a name="omp-set-nest-lock"></a>omp_set_nest_lock

Blöcke Threadausführung, bis eine Sperre verfügbar ist.

```
void omp_set_nest_lock(
   omp_nest_lock_t *lock
);
```

### <a name="parameters"></a>Parameter

*lock*<br/>
Eine Variable vom Typ `omp_nest_lock_t` , die mit initialisiert wurde [Omp_init_nest_lock](#omp-init-nest-lock).

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [3.2.3 Omp_set_lock- und Omp_set_nest_lock-Funktionen](../../../parallel/openmp/3-2-3-omp-set-lock-and-omp-set-nest-lock-functions.md).

### <a name="examples"></a>Beispiele

Finden Sie unter [Omp_init_nest_lock](#omp-init-nest-lock) ein Beispiel der Verwendung von `omp_set_nest_lock`.

## <a name="omp-set-nested"></a>omp_set_nested

Ermöglicht geschachtelte Parallelität.

```
void omp_set_nested(
   int val
);
```

### <a name="parameters"></a>Parameter

*val*<br/>
Ein Wert ungleich Null ermöglicht geschachtelte Parallelität, während Null geschachtelte Parallelität deaktiviert sind.

### <a name="remarks"></a>Hinweise

Geschachtelte OMP Parallelität kann mit aktiviert werden `omp_set_nested`, oder durch Festlegen der [OMP_NESTED](openmp-environment-variables.md#omp-nested) -Umgebungsvariablen angegeben.

Die Einstellung für `omp_set_nested` überschreibt die Einstellung der `OMP_NESTED` -Umgebungsvariablen angegeben.

Aktivieren die Umgebungsvariable kann einem andernfalls operational Programm unterbrechen, da die Anzahl der Threads beim Schachteln von paralleler Bereichen exponentiell. Beispielsweise erfordert eine Funktion, die bis zu sechs Mal mit der Anzahl der Threads OMP auf 4 bezieht 4.096 (4, um die Leistungsfähigkeit von 6) Threads. Mit Ausnahme von nimmt mit e/A Anwendungen, die Leistung einer Anwendung in der Regel treten mehr Threads als Prozessoren.

Verwendung [Omp_get_nested](#omp-get-nested) zum Anzeigen der aktuellen Einstellung des `omp_set_nested`.

Weitere Informationen finden Sie unter [3.1.9 Omp_set_nested-Funktion](../../../parallel/openmp/3-1-9-omp-set-nested-function.md).

### <a name="example"></a>Beispiel

```cpp
// omp_set_nested.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main( )
{
    omp_set_nested(1);
    omp_set_num_threads(4);
    printf_s("%d\n", omp_get_nested( ));
    #pragma omp parallel
        #pragma omp master
        {
            printf_s("%d\n", omp_get_nested( ));
        }
}
```

```Output
1
1
```

## <a name="omp-set-num-threads"></a>omp_set_num_threads

Die Anzahl der Threads in zukünftigen parallelen Bereichen, legt fest, es sei denn, durch Überschreiben einer [Num_threads](openmp-clauses.md#num-threads) Klausel.

```
void omp_set_num_threads(
   int num_threads
);
```

### <a name="parameters"></a>Parameter

*num_threads*<br/>
Die Anzahl der Threads in den parallelen Bereich.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [3.1.1 Omp_set_num_threads-Funktion](../../../parallel/openmp/3-1-1-omp-set-num-threads-function.md).

### <a name="example"></a>Beispiel

Finden Sie unter [Omp_get_num_threads](#omp-get-num-threads) ein Beispiel der Verwendung von `omp_set_num_threads`.

## <a name="omp-test-lock"></a>omp_test_lock

Versucht, eine Sperre festzulegen, aber nicht die Ausführung des Threads zu blockieren.

```
int omp_test_lock(
   omp_lock_t *lock
);
```

### <a name="parameters"></a>Parameter

*lock*<br/>
Eine Variable vom Typ `omp_lock_t` , die mit initialisiert wurde [Omp_init_lock](#omp-init-lock).

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [3.2.5 Omp_test_lock and Omp_test_nest_lock-Funktionen](../../../parallel/openmp/3-2-5-omp-test-lock-and-omp-test-nest-lock-functions.md).

### <a name="example"></a>Beispiel

```cpp
// omp_test_lock.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

omp_lock_t simple_lock;

int main() {
    omp_init_lock(&simple_lock);

    #pragma omp parallel num_threads(4)
    {
        int tid = omp_get_thread_num();

        while (!omp_test_lock(&simple_lock))
            printf_s("Thread %d - failed to acquire simple_lock\n",
                     tid);

        printf_s("Thread %d - acquired simple_lock\n", tid);

        printf_s("Thread %d - released simple_lock\n", tid);
        omp_unset_lock(&simple_lock);
    }

    omp_destroy_lock(&simple_lock);
}
```

```Output
Thread 1 - acquired simple_lock
Thread 1 - released simple_lock
Thread 0 - failed to acquire simple_lock
Thread 3 - failed to acquire simple_lock
Thread 0 - failed to acquire simple_lock
Thread 3 - failed to acquire simple_lock
Thread 2 - acquired simple_lock
Thread 0 - failed to acquire simple_lock
Thread 3 - failed to acquire simple_lock
Thread 0 - failed to acquire simple_lock
Thread 3 - failed to acquire simple_lock
Thread 2 - released simple_lock
Thread 0 - failed to acquire simple_lock
Thread 3 - failed to acquire simple_lock
Thread 0 - acquired simple_lock
Thread 3 - failed to acquire simple_lock
Thread 0 - released simple_lock
Thread 3 - failed to acquire simple_lock
Thread 3 - acquired simple_lock
Thread 3 - released simple_lock
```

## <a name="omp-test-nest-lock"></a>omp_test_nest_lock

Versucht, eine omp_nest_lock_t-Sperre festzulegen, aber nicht die Ausführung des Threads zu blockieren.

```
int omp_test_nest_lock(
   omp_nest_lock_t *lock
);
```

### <a name="parameters"></a>Parameter

*lock*<br/>
Eine Variable vom Typ `omp_nest_lock_t` , die mit initialisiert wurde [Omp_init_nest_lock](#omp-init-nest-lock).

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [3.2.5 Omp_test_lock and Omp_test_nest_lock-Funktionen](../../../parallel/openmp/3-2-5-omp-test-lock-and-omp-test-nest-lock-functions.md).

### <a name="example"></a>Beispiel

```cpp
// omp_test_nest_lock.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

omp_nest_lock_t nestable_lock;

int main() {
   omp_init_nest_lock(&nestable_lock);

   #pragma omp parallel num_threads(4)
   {
      int tid = omp_get_thread_num();
      while (!omp_test_nest_lock(&nestable_lock))
         printf_s("Thread %d - failed to acquire nestable_lock\n",
                tid);

      printf_s("Thread %d - acquired nestable_lock\n", tid);

      if (omp_test_nest_lock(&nestable_lock)) {
         printf_s("Thread %d - acquired nestable_lock again\n",
                tid);
         printf_s("Thread %d - released nestable_lock\n",
                tid);
         omp_unset_nest_lock(&nestable_lock);
      }

      printf_s("Thread %d - released nestable_lock\n", tid);
      omp_unset_nest_lock(&nestable_lock);
   }

   omp_destroy_nest_lock(&nestable_lock);
}
```

```Output
Thread 1 - acquired nestable_lock
Thread 0 - failed to acquire nestable_lock
Thread 1 - acquired nestable_lock again
Thread 0 - failed to acquire nestable_lock
Thread 1 - released nestable_lock
Thread 0 - failed to acquire nestable_lock
Thread 1 - released nestable_lock
Thread 0 - failed to acquire nestable_lock
Thread 3 - acquired nestable_lock
Thread 0 - failed to acquire nestable_lock
Thread 3 - acquired nestable_lock again
Thread 0 - failed to acquire nestable_lock
Thread 2 - failed to acquire nestable_lock
Thread 3 - released nestable_lock
Thread 2 - failed to acquire nestable_lock
Thread 3 - released nestable_lock
Thread 2 - failed to acquire nestable_lock
Thread 0 - acquired nestable_lock
Thread 2 - failed to acquire nestable_lock
Thread 2 - failed to acquire nestable_lock
Thread 2 - failed to acquire nestable_lock
Thread 0 - acquired nestable_lock again
Thread 2 - failed to acquire nestable_lock
Thread 0 - released nestable_lock
Thread 2 - failed to acquire nestable_lock
Thread 0 - released nestable_lock
Thread 2 - failed to acquire nestable_lock
Thread 2 - acquired nestable_lock
Thread 2 - acquired nestable_lock again
Thread 2 - released nestable_lock
Thread 2 - released nestable_lock
```

## <a name="omp-unset-lock"></a>omp_unset_lock

Gibt eine Sperre frei.

```
void omp_unset_lock(
   omp_lock_t *lock
);
```

### <a name="parameters"></a>Parameter

*lock*<br/>
Eine Variable vom Typ `omp_lock_t` , die mit initialisiert wurde [Omp_init_lock](#omp-init-lock), im Besitz von Threads und in der Funktion ausgeführt.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [3.2.4 Omp_unset_lock and Omp_unset_nest_lock-Funktionen](../../../parallel/openmp/3-2-4-omp-unset-lock-and-omp-unset-nest-lock-functions.md).

### <a name="example"></a>Beispiel

Finden Sie unter [Omp_init_lock](#omp-init-lock) ein Beispiel der Verwendung von `omp_unset_lock`.

## <a name="omp-unset-nest-lock"></a>omp_unset_nest_lock

Gibt eine omp_nest_lock_t-Sperre frei.

```
void omp_unset_nest_lock(
   omp_nest_lock_t *lock
);
```

### <a name="parameters"></a>Parameter

*lock*<br/>
Eine Variable vom Typ `omp_nest_lock_t` , die mit initialisiert wurde [Omp_init_nest_lock](#omp-init-nest-lock), im Besitz von Threads und in der Funktion ausgeführt.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [3.2.4 Omp_unset_lock and Omp_unset_nest_lock-Funktionen](../../../parallel/openmp/3-2-4-omp-unset-lock-and-omp-unset-nest-lock-functions.md).

### <a name="example"></a>Beispiel

Finden Sie unter [Omp_init_nest_lock](#omp-init-nest-lock) ein Beispiel der Verwendung von `omp_unset_nest_lock`.
