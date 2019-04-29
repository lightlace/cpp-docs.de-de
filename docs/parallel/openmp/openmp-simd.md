---
title: SIMD-Erweiterung
ms.date: 03/20/2019
helpviewer_keywords:
- SIMD
- OpenMP in Visual C++, new features
- explicit parallelization, new features
ms.openlocfilehash: 52402aa553c6d68d3073aba26ecac7b784522ee9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62363270"
---
# <a name="simd-extension"></a>SIMD-Erweiterung

Visual C++ unterstützt derzeit die OpenMP 2.0-Standard, jedoch Visual Studio-2019 jetzt auch SIMD-Funktionen bietet.

> [!NOTE]
> Um SIMD zu verwenden, kompilieren Sie mit der `-openmp:experimental` Switch, die zusätzliche OpenMP-Funktionen nicht verfügbar bei Verwendung der `-openmp` wechseln.
>
> Die `-openmp:experimental` Switch subsumes `-openmp`, d. h., alle OpenMP 2.0-Features sind enthalten, verwendet.

Weitere Informationen finden Sie unter [SIMD-Erweiterung für C++ OpenMP in Visual Studio](https://devblogs.microsoft.com/cppblog/simd-extension-to-c-openmp-in-visual-studio/).

## <a name="openmp-simd-in-visual-c"></a>OpenMP-SIMD in visuellen ElementC++

OpenMP SIMD, eingeführt in 4.0 OpenMP standard, Ziele, die Vektor-freundliche Schleifen vornehmen. Mithilfe der `simd` Direktive, bevor Sie eine Schleife, der Compiler kann vektorabhängigkeiten zu ignorieren, die Schleife als Vektor-freundliche wie möglich und berücksichtigen Sie die Absicht des Benutzers müssen mehrere Schleifeniterationen, die gleichzeitig ausgeführt.

```c
    #pragma omp simd
    for (i = 0; i < count; i++)
    {
        a[i] = a[i-1] + 1;
        b[i] = *c + 1;
        bar(i);
    }
```

Visual C++ bietet ähnliche nicht OpenMP-Schleife-Pragmas wie `#pragma vector` und `#pragma ivdep`, jedoch mit OpenMP SIMD, der Compiler mehrere, z. B. möglich:

- Darf stets vorhanden vektorabhängigkeiten ignorieren.
- `/fp:fast` ist innerhalb der Schleife aktiviert werden.
- Äußere Schleife und Schleifen mit Funktionsaufrufen sind geeignete Vektor.
- Geschachtelte Schleifen können in einer Schleife vereinigt und Vektor-freundliche vorgenommen werden.
- Hybrid-Beschleunigung mit `#pragma omp for simd` undifferenzierte Multithreading und detaillierte Vektoren zu aktivieren.  

Vector-freundliche Schleifen bleibt der Compiler im Hintergrund, wenn Sie ein Support-Vector-Log-Schalter verwenden:

```cmd
    cl -O2 -openmp:experimental -Qvec-report:2 mycode.cpp
```

```Output
    mycode.cpp(84) : info C5002: Omp simd loop not vectorized due to reason '1200'
    mycode.cpp(90) : info C5002: Omp simd loop not vectorized due to reason '1200'
    mycode.cpp(96) : info C5001: Omp simd loop vectorized
```

For-Schleifen für nicht-Vektor-Friendly gibt der Compiler jeweils eine Nachricht:

```cmd
    cl -O2 -openmp:experimental mycode.cpp
```

```Output
    mycode.cpp(84) : info C5002: Omp simd loop not vectorized due to reason '1200'
    mycode.cpp(90) : info C5002: Omp simd loop not vectorized due to reason '1200'
```

### <a name="clauses"></a>Klauseln

Die OpenMP SIMD-Direktive kann auch die folgenden Klauseln zur Verbesserung der Vector-Support nutzen:

|Direktive|Beschreibung|
|---|---|
|`simdlen(length)`|Geben Sie die Anzahl der Bereiche des Vektors.|
|`safelen(length)`|Geben Sie die Entfernung der Vector-Abhängigkeit.|
|`linear(list[ : linear-step]`)|Die lineare Zuordnung schleifeninduktionsvariable Array-Abonnement.|
|`aligned(list[ : alignment])`|Die Ausrichtung der Daten.|
|`private(list)`|Geben Sie die Daten Privatisierung.|
|`lastprivate(list)`|Geben Sie Daten Privatisierung, mit der endgültigen Wert aus der letzten Iteration.|
|`reduction(reduction-identifier:list)`|Geben Sie benutzerdefinierte Reduction-Vorgänge.|
|`collapse(n)`|Zusammenfügenden Schleife schachteln.|

> [!NOTE]
> Nicht-ab-SIMD-Klauseln werden analysiert und vom Compiler eine Warnung ignoriert wird.
>
> Verwenden Sie z. B. der folgende Codeprobleme eine Warnung:
>
> ```c
>    #pragma omp simd simdlen(8)
>    for (i = 0; i < count; i++)
>    {
>        a[i] = a[i-1] + 1;
>        b[i] = *c + 1;
>        bar(i);
>    }
> ```
>
> ```Output
>    warning C4849: OpenMP 'simdlen' clause ignored in 'simd' directive
> ```

### <a name="example"></a>Beispiel
  
Die Direktive von OpenMP SIMD bietet Benutzern eine Möglichkeit zum Festlegen der Compiler stellen Schleifen Vektor geeignet. Benutzer möchten, durch das Hinzufügen einer Schleife mit OpenMP SIMD-Direktive, müssen mehrere Schleifeniterationen, die gleichzeitig ausgeführt.

Beispielsweise wird die folgende Schleife mit OpenMP SIMD-Direktive versehen. Es ist keine perfekte Parallelität zwischen Schleifeniterationen da rückwärts Abhängigkeit von einer [i] in einen [i-1], aber aufgrund der SIMD-Direktive, die der Compiler zum Packen von aufeinander folgenden Iterationen von der ersten Anweisung in einem Vektor-Anweisung, und führen Sie immer noch möglich ist Diese parallel.

```c
    #pragma omp simd
    for (i = 0; i < count; i++)
    {
        a[i] = a[i-1] + 1;
        b[i] = *c + 1;
        bar(i);
    }
```

Daher folgendermaßen transformierte Vektor der Schleife ist **rechtliche** da der Compiler das sequenzielle Verhalten von jeder ursprüngliche Schleifeniteration beibehält. Das heißt, `a[i]` ausgeführt wird, nachdem `a[-1]`, `b[i]` ist nach `a[i]` und der Aufruf von `bar` zuletzt geschieht.

```c
    for (i = 0; i < count; i+=4)
    {
        a[i:i+3] = a[i-1:i+2] + 1;
        b[i:i+3] = *c + 1;
        bar(i);
        bar(i+1);
        bar(i+2);
        bar(i+3);
    }
```

Hat **unzulässige** zum Verschieben der Speicherverweis `*c` aus der Schleife, wenn sie Aliasnamen dürfen die `a[i]` oder `b[i]`. Es ist auch nicht zulässig, die Anweisungen innerhalb einer ursprünglichen Iteration neu anzuordnen, wenn sie die sequenzielle Abhängigkeit unterbrochen. Die folgende transformierte Schleife ist z. B. nicht zulässig:

```c
    c = b;
    t = *c;
    for (i = 0; i < count; i+=4)
    {
        a[i:i+3] = a[i-1:i+2] + 1;
        bar(i);            // illegal to reorder if bar[i] depends on b[i]
        b[i:i+3] = t + 1;  // illegal to move *c out of the loop
        bar(i+1);
        bar(i+2);
        bar(i+3);
    }
```

## <a name="see-also"></a>Siehe auch

[/openmp (OpenMP 2.0-Unterstützung aktivieren)](../../build/reference/openmp-enable-openmp-2-0-support.md)<br/>
