---
title: _ITERATOR_DEBUG_LEVEL
ms.date: 11/04/2016
f1_keywords:
- _ITERATOR_DEBUG_LEVEL
helpviewer_keywords:
- _ITERATOR_DEBUG_LEVEL
ms.assetid: 718549cd-a9a9-4ab3-867b-aac00b321e67
ms.openlocfilehash: 7b573127518969accdfdcc4a25a50269dd6aa002
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456399"
---
# <a name="iteratordebuglevel"></a>_ITERATOR_DEBUG_LEVEL

Das _ITERATOR_DEBUG_LEVEL-Makro steuert, ob aktivierte [Iteratoren](../standard-library/checked-iterators.md) und die [Unterstützung](../standard-library/debug-iterator-support.md) für den debugabterator aktiviert sind Dieses Makro ersetzt und kombiniert die Funktionalität der älteren _SECURE_SCL-und _HAS_ITERATOR_DEBUGGING-Makros.

## <a name="macro-values"></a>Makrowerte

In der folgenden Tabelle sind die möglichen Werte für das _ITERATOR_DEBUG_LEVEL-Makro zusammengefasst.

|Kompilierungsmodus|Makrowert|Beschreibung|
|----------------------|----------------|-----------------|
|**Debuggen**|||
||0|Deaktiviert überprüfte Iteratoren und das Iteratordebugging.|
||1|Aktiviert überprüfte Iteratoren und deaktiviert das Iteratordebugging.|
||2 (Standard)|Aktiviert das Iteratordebugging; überprüfte Iteratoren sind nicht relevant.|
|**Version**|||
||0 (Standard)|Deaktivierte überprüfte Iteratoren.|
||1|Aktiviert überprüfte Iteratoren; das Iteratordebugging ist nicht relevant.|

Im Releasemodus generiert der Compiler einen Fehler, wenn Sie _ITERATOR_DEBUG_LEVEL als 2 angeben.

## <a name="remarks"></a>Hinweise

Das _ITERATOR_DEBUG_LEVEL-Makro steuert, ob aktivierte [Iteratoren](../standard-library/checked-iterators.md) aktiviert sind, und im Debugmodus, ob die [Unterstützung für das Debugiterator](../standard-library/debug-iterator-support.md) aktiviert ist. Wenn _ITERATOR_DEBUG_LEVEL als 1 oder 2 definiert ist, stellen überprüfte Iteratoren sicher, dass die Grenzen ihrer Container nicht überschrieben werden. Wenn _ITERATOR_DEBUG_LEVEL 0 ist, werden Iteratoren nicht überprüft. Wenn _ITERATOR_DEBUG_LEVEL als 1 definiert ist, verursacht jede unsichere Iteratorverwendung einen Laufzeitfehler, und das Programm wird beendet. Wenn _ITERATOR_DEBUG_LEVEL als 2 definiert ist, verursacht die unsichere Verwendung von Iteratoren einen Assert-und ein Lauf Zeit Fehler Dialogfeld, mit dem Sie den Debugger unterbrechen können.

Da das _ITERATOR_DEBUG_LEVEL-Makro eine ähnliche Funktionalität wie die _SECURE_SCL-und _HAS_ITERATOR_DEBUGGING-Makros unterstützt, sind Sie möglicherweise unsicher, welches Makro und welcher Makro Wert in einer bestimmten Situation verwendet werden soll. Um Verwirrung zu vermeiden, empfiehlt es sich, nur das _ITERATOR_DEBUG_LEVEL-Makro zu verwenden. In dieser Tabelle wird der entsprechende _ITERATOR_DEBUG_LEVEL-Makro Wert beschrieben, der für verschiedene Werte von _SECURE_SCL und _HAS_ITERATOR_DEBUGGING in vorhandenem Code verwendet werden soll.

|**_ITERATOR_DEBUG_LEVEL** |**_SECURE_SCL** |**_HAS_ITERATOR_DEBUGGING**|
|---|---|---|
|0 (Releasestandard)|0 (deaktiviert)|0 (deaktiviert)|
|1|1 (aktiviert)|0 (deaktiviert)|
|2 (Debug-Standard)|(nicht relevant)|1 (aktiviert im Debugmodus)|

Informationen über das Deaktivieren der Warnungen für überprüfte Iteratoren finden Sie unter [_SCL_SECURE_NO_WARNINGS](../standard-library/scl-secure-no-warnings.md).

### <a name="example"></a>Beispiel

Um einen Wert für das _ITERATOR_DEBUG_LEVEL-Makro anzugeben, verwenden Sie eine [/D](../build/reference/d-preprocessor-definitions.md) -Compileroption, um Sie in der Befehls `#define` Zeile zu C++ definieren, oder verwenden Sie, bevor die Standard Bibliotheks Header in den Quelldateien enthalten sind. Beispielsweise können Sie in der Befehlszeile die _ITERATOR_DEBUG_LEVEL-Makro Definition angeben, um *Sample. cpp* im Debugmodus zu kompilieren und die Unterstützung für die debugiteratorunterstützung zu verwenden:

`cl /EHsc /Zi /MDd /D_ITERATOR_DEBUG_LEVEL=1 sample.cpp`

Geben Sie das Makro in einer Quelldatei ein, bevor die Kopfzeilen der Standardbibliothek Iteratoren definieren.

```cpp
// sample.cpp

#define _ITERATOR_DEBUG_LEVEL 1

#include <vector>

// ...
```

## <a name="see-also"></a>Siehe auch

[Überprüfte Iteratoren](../standard-library/checked-iterators.md)\
[Unterstützung für Iteratordebugging](../standard-library/debug-iterator-support.md)\
[Sichere Bibliotheken: C++-Standardbibliothek](../standard-library/safe-libraries-cpp-standard-library.md)
