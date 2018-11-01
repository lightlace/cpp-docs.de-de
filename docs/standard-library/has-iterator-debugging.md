---
title: _HAS_ITERATOR_DEBUGGING
ms.date: 11/04/2016
f1_keywords:
- _HAS_ITERATOR_DEBUGGING
helpviewer_keywords:
- _HAS_ITERATOR_DEBUGGING
ms.assetid: 90077dbb-8a76-4963-83a6-29f4854007a8
ms.openlocfilehash: 339c32f9b487db2e318f8763ac01a0d155fc1dc1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50575876"
---
# <a name="hasiteratordebugging"></a>_HAS_ITERATOR_DEBUGGING

Durch [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md) ersetzt, definiert dieses Makro, ob die Iteratordebugfunktion in einem Debugbuild aktiviert ist. Standardmäßig ist das Iteratordebuggen in Debugbuilds aktiviert und in Verkaufsversionen deaktiviert. Weitere Informationen finden Sie unter [Debugiterator-Unterstützung](../standard-library/debug-iterator-support.md).

> [!IMPORTANT]
> Direkte Verwendung des Makros "_HAS_ITERATOR_DEBUGGING" ist veraltet. Verwenden Sie stattdessen _ITERATOR_DEBUG_LEVEL, Einstellungen zum Debuggen von Steuerelement-Iterator. Weitere Informationen finden Sie unter [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md).

## <a name="remarks"></a>Hinweise

Um das iteratordebuggen in Debugbuilds zu aktivieren, müssen Sie _ITERATOR_DEBUG_LEVEL auf 2 festgelegt. Dies entspricht der Einstellung "_HAS_ITERATOR_DEBUGGING" 1 oder aktiviert:

```cpp
#define _ITERATOR_DEBUG_LEVEL 2
```

_ITERATOR_DEBUG_LEVEL kann nicht auf 2 festgelegt werden (und "_HAS_ITERATOR_DEBUGGING" kann nicht auf 1 festgelegt werden) im Einzelhandel erstellt.

Legen Sie zum Deaktivieren Debugiteratoren in Debugbuilds _ITERATOR_DEBUG_LEVEL auf 0 oder 1 ein. Dies ist gleichbedeutend mit "_HAS_ITERATOR_DEBUGGING" die Einstellung 0 oder deaktiviert:

```cpp
#define _ITERATOR_DEBUG_LEVEL 0
```

## <a name="see-also"></a>Siehe auch

[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)<br/>
[Debug Iterator Support](../standard-library/debug-iterator-support.md)<br/>
[Checked Iterators](../standard-library/checked-iterators.md)<br/>
[Sichere Bibliotheken: C++-Standardbibliothek](../standard-library/safe-libraries-cpp-standard-library.md)<br/>
