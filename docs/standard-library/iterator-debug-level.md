---
title: _ITERATOR_DEBUG_LEVEL | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- _ITERATOR_DEBUG_LEVEL
dev_langs:
- C++
helpviewer_keywords:
- _ITERATOR_DEBUG_LEVEL
ms.assetid: 718549cd-a9a9-4ab3-867b-aac00b321e67
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7219ed039e77d0857151c54e73a03a0d1f6a3f5e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33864137"
---
# <a name="iteratordebuglevel"></a>_ITERATOR_DEBUG_LEVEL

Das `_ITERATOR_DEBUG_LEVEL`-Makro steuert, ob [überprüfte Iteratoren](../standard-library/checked-iterators.md) und [Unterstützung für Iteratordebugging](../standard-library/debug-iterator-support.md) aktiviert sind. Dieses Makro hat Vorrang und kombiniert die Funktionalität der älteren `_SECURE_SCL`- und `_HAS_ITERATOR_DEBUGGING`-Makros.

## <a name="macro-values"></a>Makrowerte

In der folgenden Tabelle werden die möglichen Werte für das `_ITERATOR_DEBUG_LEVEL`-Makro angezeigt.

|Kompilierungsmodus|Makrowert|Beschreibung|
|----------------------|----------------|-----------------|
|**Debuggen**|||
||0|Deaktiviert überprüfte Iteratoren und das Iteratordebugging.|
||1|Aktiviert überprüfte Iteratoren und deaktiviert das Iteratordebugging.|
||2 (Standard)|Aktiviert das Iteratordebugging; überprüfte Iteratoren sind nicht relevant.|
|**Version**|||
||0 (Standard)|Deaktivierte überprüfte Iteratoren.|
||1|Aktiviert überprüfte Iteratoren; das Iteratordebugging ist nicht relevant.|

Im Releasemodus generiert der Compiler einen Fehler, wenn Sie `_ITERATOR_DEBUG_LEVEL` als 2 angeben.

## <a name="remarks"></a>Hinweise

Das `_ITERATOR_DEBUG_LEVEL`-Makro steuert, ob [überprüfte Iteratoren](../standard-library/checked-iterators.md) aktiviert ist, und im Debugmodus, ob die [Unterstützung für Iteratordebugging](../standard-library/debug-iterator-support.md) aktiviert ist. Wenn `_ITERATOR_DEBUG_LEVEL` als 1 oder 2 definiert ist, stellen aktivierte Iteratoren sicher, dass die Grenzen des Containers nicht überschrieben werden. Wenn `_ITERATOR_DEBUG_LEVEL` gleich 0 ist, werden Iteratoren nicht überprüft. Wenn `_ITERATOR_DEBUG_LEVEL` als 1 definiert ist, verursacht die unsichere Verwendung von Iteratoren einen Laufzeitfehler und das Programm wird beendet. Wenn `_ITERATOR_DEBUG_LEVEL` als 2 definiert ist, verursacht die unsichere Verwendung von Iteratoren eine Assert-Anweisung und ein Laufzeitfehler-Dialogfeld, dass Sie den Debugger unterbrechen lässt.

Da das `_ITERATOR_DEBUG_LEVEL`-Makro ähnliche Funktionalitäten wie die `_SECURE_SCL` und `_HAS_ITERATOR_DEBUGGING`-Makros unterstützt, sind Sie möglicherweise unsicher, welche Makros und Makrowerte Sie in einer bestimmten Situation verwenden sollten. Um Verwirrung zu vermeiden, wird empfohlen, nur das `_ITERATOR_DEBUG_LEVEL`-Makro zu verwenden. Diese Tabelle beschreibt den entsprechenden `_ITERATOR_DEBUG_LEVEL`-Makrowert für die Verwendung verschiedener Werte von `_SECURE_SCL` und `_HAS_ITERATOR_DEBUGGING` in vorhandenem Code.

|**_ITERATOR_DEBUG_LEVEL** |**_SECURE_SCL** |**_HAS_ITERATOR_DEBUGGING**|
|---|---|---|
|0 (Releasestandard)|0 (deaktiviert)|0 (deaktiviert)|
|1|1 (aktiviert)|0 (deaktiviert)|
|2 (Debug-Standard)|(nicht relevant)|1 (aktiviert im Debugmodus)|

Informationen über das Deaktivieren der Warnungen für überprüfte Iteratoren finden Sie unter [_SCL_SECURE_NO_WARNINGS](../standard-library/scl-secure-no-warnings.md).

### <a name="example"></a>Beispiel

Verwenden Sie für die Angabe eines Werts für das `_ITERATOR_DEBUG_LEVEL`-Makro eine [/D](../build/reference/d-preprocessor-definitions.md)-Compileroption, um es in der Befehlszeile zu definieren, oder verwenden Sie `#define`, bevor die Kopfzeilen der C++-Standardbibliothek in Ihren Quelldateien enthalten sind. Um beispielsweise in der Befehlszeile *sample.cpp* im Debugmodus zu kompilieren und die Unterstützung für Iteratordebugging zu verwenden, können Sie die `_ITERATOR_DEBUG_LEVEL`-Makrodefinition angeben:

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
