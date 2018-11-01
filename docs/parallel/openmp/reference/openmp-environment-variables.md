---
title: OpenMP-Umgebungsvariablen
ms.date: 10/23/2018
f1_keywords:
- OpenMP environment variables
- OMP_DYNAMIC
- OMP_NESTED
- OMP_NUM_THREADS
- OMP_SCHEDULE
helpviewer_keywords:
- OpenMP environment variables
- OMP_DYNAMIC OpenMP environment variable
- OMP_NESTED OpenMP environment variable
- OMP_NUM_THREADS OpenMP environment variable
- OMP_SCHEDULE OpenMP environment variable
ms.assetid: 2178ce2b-ffa1-45ec-a455-64437711d15d
ms.openlocfilehash: 99868fec581d93f451d321af365f6c4546319077
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50449685"
---
# <a name="openmp-environment-variables"></a>OpenMP-Umgebungsvariablen

Enthält Links zu den Umgebungsvariablen, die in der OpenMP-API verwendet.

Die Visual C++-Implementierung von der OpenMP-standard umfasst die folgenden Umgebungsvariablen. Diese Umgebungsvariablen werden gelesen, beim Programmstart und Änderungen an deren Werte zur Laufzeit ignoriert werden (z. B. [_putenv, _wputenv](../../../c-runtime-library/reference/putenv-wputenv.md)).

|Umgebungsvariable|Beschreibung|
|--------------------|-----------|
|[OMP_DYNAMIC](#omp-dynamic)|Gibt an, ob die OpenMP zur Laufzeit die Anzahl der Threads in einem parallelen Bereich anpassen kann.|
|[OMP_NESTED](#omp-nested)|Gibt an, ob geschachtelte Parallelität aktiviert ist, es sei denn, geschachtelte Parallelität aktiviert oder deaktiviert ist, `omp_set_nested`.|
|[OMP_NUM_THREADS](#omp-num-threads)|Legt die maximale Anzahl von Threads in den parallelen Bereich fest, es sei denn, durch außer Kraft gesetzt [Omp_set_num_threads](openmp-functions.md#omp-set-num-threads) oder [Num_threads](openmp-clauses.md#num-threads).|
|[OMP_SCHEDULE](#omp-schedule)|Ändert das Verhalten von der [Zeitplan](openmp-clauses.md#schedule) Klausel bei `schedule(runtime)` angegeben ist, eine `for` oder `parallel for` Richtlinie.|

## <a name="omp-dynamic"></a>OMP_DYNAMIC

Gibt an, ob die OpenMP zur Laufzeit die Anzahl der Threads in einem parallelen Bereich anpassen kann.

```
set OMP_DYNAMIC[=TRUE | =FALSE]
```

### <a name="remarks"></a>Hinweise

Die `OMP_DYNAMIC` Umgebungsvariable kann überschrieben werden, indem die [Omp_set_dynamic](openmp-functions.md#omp-set-dynamic) Funktion.

Der Standardwert in der Visual C++-Implementierung des OpenMP-Standards ist `OMP_DYNAMIC=FALSE`.

Weitere Informationen finden Sie unter [4.3 OMP_DYNAMIC](../../../parallel/openmp/4-3-omp-dynamic.md).

### <a name="example"></a>Beispiel

Der folgende Befehl legt die `OMP_DYNAMIC` -Umgebungsvariable auf "true":

```
set OMP_DYNAMIC=TRUE
```

Der folgende Befehl zeigt die aktuelle Einstellung der `OMP_DYNAMIC` -Umgebungsvariablen angegeben:

```
set OMP_DYNAMIC
```

## <a name="omp-nested"></a>OMP_NESTED

Gibt an, ob geschachtelte Parallelität aktiviert ist, es sei denn, geschachtelte Parallelität aktiviert oder deaktiviert ist, `omp_set_nested`.

```
set OMP_NESTED[=TRUE | =FALSE]
```

### <a name="remarks"></a>Hinweise

Die `OMP_NESTED` Umgebungsvariable kann überschrieben werden, indem die [Omp_set_nested](openmp-functions.md#omp-set-nested) Funktion.

Der Standardwert in der Visual C++-Implementierung des OpenMP-Standards ist `OMP_DYNAMIC=FALSE`.

Weitere Informationen finden Sie unter [4.4 OMP_NESTED](../../../parallel/openmp/4-4-omp-nested.md).

### <a name="example"></a>Beispiel

Der folgende Befehl legt die `OMP_NESTED` -Umgebungsvariable auf "true":

```
set OMP_NESTED=TRUE
```

Der folgende Befehl zeigt die aktuelle Einstellung der `OMP_NESTED` -Umgebungsvariablen angegeben:

```
set OMP_NESTED
```

## <a name="omp-num-threads"></a>OMP_NUM_THREADS

Legt die maximale Anzahl von Threads in den parallelen Bereich fest, es sei denn, durch außer Kraft gesetzt [Omp_set_num_threads](openmp-functions.md#omp-set-num-threads) oder [Num_threads](openmp-clauses.md#num-threads).

```
set OMP_NUM_THREADS[=num]
```

### <a name="parameters"></a>Parameter

*num*<br/>
Die maximale Anzahl von Threads, die Sie in den parallelen Bereich, bis zu 64 in der Visual C++-Implementierung verwenden möchten.

### <a name="remarks"></a>Hinweise

Die `OMP_NUM_THREADS` Umgebungsvariable kann überschrieben werden, indem die [Omp_set_num_threads](openmp-functions.md#omp-set-num-threads) Funktion oder durch [Num_threads](openmp-clauses.md#num-threads).

Der Standardwert von `num` in der Visual C++-Implementierung der OpenMP-Standard ist die Anzahl virtueller Prozessoren, einschließlich CPUs mit Hyperthreading.

Weitere Informationen finden Sie unter [4.2 OMP_NUM_THREADS](../../../parallel/openmp/4-2-omp-num-threads.md).

### <a name="example"></a>Beispiel

Der folgende Befehl legt die `OMP_NUM_THREADS` -Umgebungsvariable auf 16:

```
set OMP_NUM_THREADS=16
```

Der folgende Befehl zeigt die aktuelle Einstellung der `OMP_NUM_THREADS` -Umgebungsvariablen angegeben:

```
set OMP_NUM_THREADS
```

## <a name="omp-schedule"></a>OMP_SCHEDULE

Ändert das Verhalten von der [Zeitplan](openmp-clauses.md#schedule) Klausel bei `schedule(runtime)` angegeben ist, eine `for` oder `parallel for` Richtlinie.

```
set OMP_SCHEDULE[=type[,size]]
```

### <a name="parameters"></a>Parameter

*size*<br/>
(Optional) Gibt die Größe der Iterationen. `size` Eine positive ganze Zahl muss sein. Der Standardwert ist 1, außer wenn `type` ist statisch. Nicht gültig, wenn `type` ist `runtime`.

*Typ*<br/>
Die Art der Planung:

- `dynamic`
- `guided`
- `runtime`
- `static`

### <a name="remarks"></a>Hinweise

Der Standardwert in der Visual C++-Implementierung des OpenMP-Standards ist `OMP_SCHEDULE=static,0`.

Weitere Informationen finden Sie unter [4.1 OMP_SCHEDULE](../../../parallel/openmp/4-1-omp-schedule.md).

### <a name="example"></a>Beispiel

Der folgende Befehl legt die `OMP_SCHEDULE` -Umgebungsvariablen angegeben:

```
set OMP_SCHEDULE="guided,2"
```

Der folgende Befehl zeigt die aktuelle Einstellung der `OMP_SCHEDULE` -Umgebungsvariablen angegeben:

```
set OMP_SCHEDULE
```
