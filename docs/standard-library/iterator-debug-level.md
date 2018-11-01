---
title: _ITERATOR_DEBUG_LEVEL
ms.date: 11/04/2016
f1_keywords:
- _ITERATOR_DEBUG_LEVEL
helpviewer_keywords:
- _ITERATOR_DEBUG_LEVEL
ms.assetid: 718549cd-a9a9-4ab3-867b-aac00b321e67
ms.openlocfilehash: a584fe5a97e251205e750507b27e53e6e7b9a20e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50502816"
---
# <a name="iteratordebuglevel"></a>_ITERATOR_DEBUG_LEVEL

Die _ITERATOR_DEBUG_LEVEL-Makro steuert, ob [überprüfte Iteratoren](../standard-library/checked-iterators.md) und [Unterstützung für iteratordebugging](../standard-library/debug-iterator-support.md) aktiviert sind. Dieses Makro hat Vorrang und kombiniert die Funktionalität der älteren Makros "_SECURE_SCL" und "_HAS_ITERATOR_DEBUGGING".

## <a name="macro-values"></a>Makrowerte

In der folgende Tabelle sind die möglichen Werte für das Makro _ITERATOR_DEBUG_LEVEL zusammengefasst.

|Kompilierungsmodus|Makrowert|Beschreibung|
|----------------------|----------------|-----------------|
|**Debuggen**|||
||0|Deaktiviert überprüfte Iteratoren und das Iteratordebugging.|
||1|Aktiviert überprüfte Iteratoren und deaktiviert das Iteratordebugging.|
||2 (Standard)|Aktiviert das Iteratordebugging; überprüfte Iteratoren sind nicht relevant.|
|**Version**|||
||0 (Standard)|Deaktivierte überprüfte Iteratoren.|
||1|Aktiviert überprüfte Iteratoren; das Iteratordebugging ist nicht relevant.|

Im Releasemodus generiert der Compiler einen Fehler aus, bei der Angabe von _ITERATOR_DEBUG_LEVEL als 2.

## <a name="remarks"></a>Hinweise

Die _ITERATOR_DEBUG_LEVEL-Makro steuert, ob [überprüfte Iteratoren](../standard-library/checked-iterators.md) aktiviert ist, und im Debugmodus befindet, gibt an, ob [Unterstützung für iteratordebugging](../standard-library/debug-iterator-support.md) aktiviert ist. Wenn _ITERATOR_DEBUG_LEVEL als 1 oder 2 definiert ist, stellen Sie überprüfte Iteratoren sicher, dass die Grenzen des Containers nicht überschrieben werden. Wenn _ITERATOR_DEBUG_LEVEL 0 ist, werden Iteratoren nicht überprüft werden. Wenn _ITERATOR_DEBUG_LEVEL als 1 definiert ist, bewirkt, dass alle unsichere Verwendung einen Laufzeitfehler und das Programm wird beendet. Wenn _ITERATOR_DEBUG_LEVEL 2 definiert ist, verwenden unsicherer Iterator Ursachen, die eine Assert-Anweisung und ein Laufzeitfehler-Dialogfeld, in dem Sie können den Debugger zu unterbrechen.

Da das Makro _ITERATOR_DEBUG_LEVEL ähnliche Funktionalität wie die Makros "_SECURE_SCL" und "_HAS_ITERATOR_DEBUGGING" unterstützt, können Sie nicht sicher sind möglicherweise welche Makros und Makrowerte Wert in einer bestimmten Situation verwendet. Um Verwirrung zu vermeiden, empfehlen wir, dass Sie nur das _ITERATOR_DEBUG_LEVEL-Makro verwenden. Diese Tabelle beschreibt die entsprechende _ITERATOR_DEBUG_LEVEL Makrowert für verschiedene Werte von "_SECURE_SCL" und "_HAS_ITERATOR_DEBUGGING" in das vorhandenem Code.

|**_ITERATOR_DEBUG_LEVEL** |**_SECURE_SCL** |**_HAS_ITERATOR_DEBUGGING**|
|---|---|---|
|0 (Releasestandard)|0 (deaktiviert)|0 (deaktiviert)|
|1|1 (aktiviert)|0 (deaktiviert)|
|2 (Debug-Standard)|(nicht relevant)|1 (aktiviert im Debugmodus)|

Informationen über das Deaktivieren der Warnungen für überprüfte Iteratoren finden Sie unter [_SCL_SECURE_NO_WARNINGS](../standard-library/scl-secure-no-warnings.md).

### <a name="example"></a>Beispiel

Verwenden Sie zum Angeben eines Werts für das Makro _ITERATOR_DEBUG_LEVEL eine [/d](../build/reference/d-preprocessor-definitions.md) -Compileroption verwenden, um es in der Befehlszeile definieren, oder verwenden Sie `#define` Header sind vor der C++-Standardbibliothek in Ihren Quelldateien enthalten. Z. B. auf der Befehlszeile kompilieren *sample.cpp* im Debugmodus befindet und Unterstützung für das iteratordebugging zu verwenden, können Sie die Makrodefinition _ITERATOR_DEBUG_LEVEL angeben:

`cl /EHsc /Zi /MDd /D_ITERATOR_DEBUG_LEVEL=1 sample.cpp`

Geben Sie das Makro in einer Quelldatei ein, bevor die Kopfzeilen der Standardbibliothek Iteratoren definieren.

```cpp
// sample.cpp

#define _ITERATOR_DEBUG_LEVEL 1

#include <vector>

// ...
```

## <a name="see-also"></a>Siehe auch

[Checked Iterators](../standard-library/checked-iterators.md)<br/>
[Debug Iterator Support](../standard-library/debug-iterator-support.md)<br/>
[Sichere Bibliotheken: C++-Standardbibliothek](../standard-library/safe-libraries-cpp-standard-library.md)<br/>
