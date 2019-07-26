---
title: _SECURE_SCL
ms.date: 11/04/2016
f1_keywords:
- _SECURE_SCL
helpviewer_keywords:
- _SECURE_SCL
ms.assetid: 4ffbc788-cc12-4c6a-8cd7-490081675086
ms.openlocfilehash: 1af084363fc0d6d1723a9af7b633779f92ed2b38
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68450530"
---
# <a name="securescl"></a>_SECURE_SCL

Ersetzt durch [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md), dieses Makro definiert, ob [Überprüfte Iteratoren](../standard-library/checked-iterators.md) aktiviert sind. Standardmäßig sind „Überprüfte Iteratoren“ in Debugbuilds aktiviert und in Verkaufsversionen deaktiviert.

> [!IMPORTANT]
> Die direkte Verwendung des _SECURE_SCL-Makros ist veraltet. Verwenden Sie stattdessen _ITERATOR_DEBUG_LEVEL, um überprüfte iteratoreinstellungen zu steuern. Weitere Informationen finden Sie unter [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md).

## <a name="remarks"></a>Hinweise

Wenn überprüfte Iteratoren aktiviert sind, verursacht die unsichere Verwendung einen Laufzeitfehler und das Programm wird beendet. Um überprüfte Iteratoren zu aktivieren, legen Sie _ITERATOR_DEBUG_LEVEL auf 1 oder 2 fest. Dies entspricht einer _SECURE_SCL-Einstellung von 1 oder aktiviert:

```cpp
#define _ITERATOR_DEBUG_LEVEL 1
```

Legen Sie _ITERATOR_DEBUG_LEVEL auf 0 fest, um überprüfte Iteratoren zu deaktivieren. Dies entspricht einer _SECURE_SCL-Einstellung von 0 (null) oder deaktiviert:

```cpp
#define _ITERATOR_DEBUG_LEVEL 0
```

Informationen über das Deaktivieren von Warnungen für überprüfte Iteratoren finden Sie unter [_SCL_SECURE_NO_WARNINGS](../standard-library/scl-secure-no-warnings.md).

## <a name="see-also"></a>Siehe auch

[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)\
[Überprüfte Iteratoren](../standard-library/checked-iterators.md)\
[Unterstützung für Iteratordebugging](../standard-library/debug-iterator-support.md)\
[Sichere Bibliotheken: C++-Standardbibliothek](../standard-library/safe-libraries-cpp-standard-library.md)
