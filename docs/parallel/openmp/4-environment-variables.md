---
title: 4. Umgebungsvariablen
ms.date: 01/16/2019
ms.assetid: 4ec7ed81-e9ca-46a1-84f8-8f9ce4587346
ms.openlocfilehash: b41829fd9cf2f90312f669ef991f56dda02947f7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62363192"
---
# <a name="4-environment-variables"></a>4. Umgebungsvariablen

In diesem Kapitel wird beschrieben, die Umgebungsvariablen OpenMP-C- und C++-API (oder ähnliche plattformspezifische Mechanismen), die die Ausführung von parallelen Code steuern.  Die Namen der Umgebungsvariablen muss in Großbuchstaben. Die Werte, die ihnen zugewiesene werden Groß-/Kleinschreibung und möglicherweise führende und nachfolgende Leerzeichen.  Änderungen der Werte, die nach dem Start des Programms werden ignoriert.

Die Umgebungsvariablen sind wie folgt aus:

- [OMP_SCHEDULE](#41-omp_schedule) legt die Laufzeit-Zeitplan-Typ und Block Größe fest.
- [OMP_NUM_THREADS](#42-omp_num_threads) legt die Anzahl der Threads an, während der Ausführung verwendet.
- [OMP_DYNAMIC](#43-omp_dynamic) aktiviert oder deaktiviert die dynamische Anpassung der Anzahl von Threads.
- [OMP_NESTED](#44-omp_nested) aktiviert oder deaktiviert die geschachtelten Parallelität.

Den Beispielen in diesem Kapitel wird nur gezeigt, wie diese Variablen in Unix C shellumgebungen (Csh) festgelegt werden können. In den Korn-Shell und ein DOS-Umgebungen ähneln die Aktionen:

Csh:  
`setenv OMP_SCHEDULE "dynamic"`

Ksh:  
`export OMP_SCHEDULE="dynamic"`

DOS:  
`set OMP_SCHEDULE="dynamic"`

## <a name="41-omp_schedule"></a>4.1 OMP_SCHEDULE

`OMP_SCHEDULE` gilt nur für `for` und `parallel for` Direktiven, die den Zeitplantyp `runtime`. Der Zeitplan Typ und die Block-Größe für alle Schleifen kann zur Laufzeit festgelegt werden. Diese Umgebungsvariable festgelegt, um alle erkannten Zeitplantyp und eine optionale *Chunk_size*.

Für `for` und `parallel for` Direktiven, die einen Zeitplantyp aufweisen `runtime`, `OMP_SCHEDULE` wird ignoriert. Der Standardwert für diese Umgebungsvariable wird die Implementierung definiert. Wenn der optionale *Chunk_size* festgelegt ist, wird der Wert muss positiv sein. Wenn *Chunk_size* ist nicht festgelegt ist, wird der Wert 1 wird angenommen, es sei denn, der Zeitplan `static`. Für eine `static` planen, die standardmäßige Segmentgröße zum Bereich Iteration Schleife geteilt durch die Anzahl der Threads, die angewendet werden, um die Schleife festgelegt ist.

Beispiel:

```csh
setenv OMP_SCHEDULE "guided,4"
setenv OMP_SCHEDULE "dynamic"
```

### <a name="cross-references"></a>Querverweise

- [für](2-directives.md#241-for-construct) Richtlinie
- [für die parallele](2-directives.md#251-parallel-for-construct) Richtlinie

## <a name="42-omp_num_threads"></a>4.2 OMP_NUM_THREADS

Die `OMP_NUM_THREADS` -Umgebungsvariable wird die Standardanzahl von Threads zur Verwendung während der Ausführung. `OMP_NUM_THREADS` wird ignoriert, wenn diese Zahl explizit, durch den Aufruf geändert wird der `omp_set_num_threads` Bibliotheksroutine. Es ist auch ignoriert, wenn ein expliziter `num_threads` -Klausel für eine `parallel` Richtlinie.

Der Wert des der `OMP_NUM_THREADS` -Umgebungsvariable muss eine positive ganze Zahl sein. Die Auswirkungen hängt davon ab, ob die dynamische Anpassung der Anzahl der Threads aktiviert ist. Für einen umfassenden Satz von Regeln über die Interaktion zwischen der `OMP_NUM_THREADS` Umgebung Variable und die dynamische Anpassung der Threads finden Sie unter [Abschnitt 2.3](2-directives.md#23-parallel-construct).

Die Anzahl der zu verwendenden Threads wird Wenn implementierungsdefinierte:

- die `OMP_NUM_THREADS` -Umgebungsvariable nicht angegeben ist,
- Der angegebene Wert ist nicht in eine positive ganze Zahl, oder
- der Wert ist größer als die maximale Anzahl von Threads, die das System unterstützen kann.

Beispiel:

```csh
setenv OMP_NUM_THREADS 16
```

### <a name="cross-references"></a>Querverweise

- [Num_threads](2-directives.md#23-parallel-construct) Klausel
- [omp_set_num_threads](3-run-time-library-functions.md#311-omp_set_num_threads-function) function
- [omp_set_dynamic](3-run-time-library-functions.md#317-omp_set_dynamic-function) function

## <a name="43-omp_dynamic"></a>4.3 OMP_DYNAMIC

Die `OMP_DYNAMIC` Umgebungsvariablen aktiviert oder deaktiviert die dynamische Anpassung der Anzahl der Threads, die für die Ausführung von parallelen Bereichen verfügbar. `OMP_DYNAMIC` wird ignoriert, wenn die dynamische Anpassung explizit aktiviert oder deaktiviert werden, durch den Aufruf der `omp_set_dynamic` Bibliotheksroutine. Muss sein Wert `TRUE` oder `FALSE`.

Wenn `OMP_DYNAMIC` nastaven NA hodnotu `TRUE`, die Anzahl der Threads, die verwendet werden, für die Ausführung von paralleler Bereichen kann angepasst werden, von der Common Language Runtime-Umgebung zur optimalen Verwendung der Systemressourcen.  Wenn `OMP_DYNAMIC` nastaven NA hodnotu `FALSE`, dynamische Anpassung ist deaktiviert. Die standardbedingung wird die Implementierung definiert.

Beispiel:

```csh
setenv OMP_DYNAMIC TRUE
```

### <a name="cross-references"></a>Querverweise

- [Parallelen Bereichen](2-directives.md#23-parallel-construct)
- [omp_set_dynamic](3-run-time-library-functions.md#317-omp_set_dynamic-function) function

## <a name="44-omp_nested"></a>4.4 OMP_NESTED

Die `OMP_NESTED` Umgebungsvariablen aktiviert oder geschachtelte Parallelität deaktiviert, es sei denn, geschachtelte Parallelität aktiviert oder werden, durch den Aufruf deaktiviert der `omp_set_nested` Bibliotheksroutine. Wenn `OMP_NESTED` nastaven NA hodnotu `TRUE`, geschachtelte Parallelität aktiviert ist. Wenn `OMP_NESTED` nastaven NA hodnotu `FALSE`, geschachtelte Parallelität deaktiviert ist. Der Standardwert ist `FALSE`.

Beispiel:

```csh
setenv OMP_NESTED TRUE
```

### <a name="cross-reference"></a>Querverweise

- [Omp_set_nested](3-run-time-library-functions.md#319-omp_set_nested-function) Funktion
