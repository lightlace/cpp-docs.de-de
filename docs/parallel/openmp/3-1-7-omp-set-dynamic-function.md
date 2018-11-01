---
title: 3.1.7 omp_set_dynamic-Funktion
ms.date: 11/04/2016
ms.assetid: 1fba961b-b82c-4a1e-ab0f-e4be826e50ab
ms.openlocfilehash: 641b2ecfdb19aec9387aa299d22a041f25b22929
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50492936"
---
# <a name="317-ompsetdynamic-function"></a>3.1.7 omp_set_dynamic-Funktion

Die **Omp_set_dynamic** Funktion aktiviert oder deaktiviert die dynamische Anpassung der Anzahl der Threads, die für die Ausführung von parallelen Bereichen verfügbar. Es wird folgendes Format verwendet:

```
#include <omp.h>
void omp_set_dynamic(int dynamic_threads);
```

Wenn *Dynamic_threads* ergibt einen Wert ungleich NULL, die Anzahl der Threads, die verwendet werden, für die Ausführung nachfolgender paralleler Bereichen kann angepasst werden automatisch von der Laufzeit-Umgebung auf die Systemressourcen optimal zu nutzen. Daher ist die Anzahl der Threads, die vom Benutzer angegebenen die maximale Threadanzahl beträgt. Die Anzahl der Threads im Team, das Ausführen eines parallelen Bereichs bleibt für die Dauer der parallelen Region und wird gemeldet, indem die **Omp_get_num_threads** Funktion.

Wenn *Dynamic_threads* ergibt 0 ist, wird der dynamische Anpassung ist deaktiviert.

Diese Funktion hat die Auswirkungen, die oben beschriebenen, beim Aufrufen durch einen Teil des Programms, in denen die **Omp_in_parallel** Funktion gibt 0 (null) zurück. Wenn sie über einen Teil des Programms aufgerufen wird, in denen die **Omp_in_parallel** Funktion gibt einen Wert ungleich NULL zurück, das Verhalten dieser Funktion ist nicht definiert.

Ein Aufruf von **Omp_set_dynamic** hat Vorrang vor den **OMP_DYNAMIC** -Umgebungsvariablen angegeben.

Der Standardwert für die dynamische Anpassung des Threads wird die Implementierung definiert. Daher sollten Benutzer-Codes, die abhängig von einer bestimmten Anzahl von Threads zur richtigen Ausführung explizit deaktivieren, dynamische Threads. Implementierungen sind nicht erforderlich, um die Möglichkeit bieten, die Anzahl der Threads dynamisch anpassen, aber sie sind erforderlich, um die Schnittstelle bereitzustellen, um Portabilität auf allen Plattformen zu unterstützen.

## <a name="cross-references"></a>Datenbankübergreifende Verweise:

- **Omp_get_num_threads** funktionieren, finden Sie unter [Abschnitt 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) auf Seite 37.

- **OMP_DYNAMIC** Umgebung Variablen, finden Sie unter [Abschnitt-4.3](../../parallel/openmp/4-3-omp-dynamic.md) auf 49.

- **Omp_in_parallel** funktionieren, finden Sie unter [Abschnitt 3.1.6](../../parallel/openmp/3-1-6-omp-in-parallel-function.md) auf 38.