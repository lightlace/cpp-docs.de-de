---
title: _HAS_ITERATOR_DEBUGGING
ms.date: 11/04/2016
f1_keywords:
- _HAS_ITERATOR_DEBUGGING
helpviewer_keywords:
- _HAS_ITERATOR_DEBUGGING
ms.assetid: 90077dbb-8a76-4963-83a6-29f4854007a8
ms.openlocfilehash: a1e3017ed7c6def18ce02d99dc8253b69c11ab58
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68448836"
---
# <a name="hasiteratordebugging"></a>_HAS_ITERATOR_DEBUGGING

Durch [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md) ersetzt, definiert dieses Makro, ob die Iteratordebugfunktion in einem Debugbuild aktiviert ist. Standardmäßig ist das Iteratordebuggen in Debugbuilds aktiviert und in Verkaufsversionen deaktiviert. Weitere Informationen finden Sie unter [Debugiterator-Unterstützung](../standard-library/debug-iterator-support.md).

> [!IMPORTANT]
> Die direkte Verwendung des _HAS_ITERATOR_DEBUGGING-Makros ist veraltet. Verwenden Sie stattdessen _ITERATOR_DEBUG_LEVEL, um die iteratordebugeinstellungen zu steuern. Weitere Informationen finden Sie unter [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md).

## <a name="remarks"></a>Hinweise

Um das iteratordebugging in Debugbuilds zu aktivieren, legen Sie _ITERATOR_DEBUG_LEVEL auf 2 fest. Dies entspricht einer _HAS_ITERATOR_DEBUGGING-Einstellung von 1 oder aktiviert:

```cpp
#define _ITERATOR_DEBUG_LEVEL 2
```

_ITERATOR_DEBUG_LEVEL kann nicht auf 2 (und _HAS_ITERATOR_DEBUGGING kann nicht auf 1 festgelegt werden) in Einzelhandels Builds festgelegt werden.

Um debuggingiteratoren in Debugbuilds zu deaktivieren, legen Sie _ITERATOR_DEBUG_LEVEL auf 0 oder 1 fest. Dies entspricht einer _HAS_ITERATOR_DEBUGGING-Einstellung von 0 (null) oder deaktiviert:

```cpp
#define _ITERATOR_DEBUG_LEVEL 0
```

## <a name="see-also"></a>Siehe auch

[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)\
[Unterstützung für Iteratordebugging](../standard-library/debug-iterator-support.md)\
[Überprüfte Iteratoren](../standard-library/checked-iterators.md)\
[Sichere Bibliotheken: C++-Standardbibliothek](../standard-library/safe-libraries-cpp-standard-library.md)
