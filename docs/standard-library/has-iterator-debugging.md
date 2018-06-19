---
title: _HAS_ITERATOR_DEBUGGING | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- _HAS_ITERATOR_DEBUGGING
dev_langs:
- C++
helpviewer_keywords:
- _HAS_ITERATOR_DEBUGGING
ms.assetid: 90077dbb-8a76-4963-83a6-29f4854007a8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ab2de61df8c4e22b1955e9fd4798b5128a3e12be
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33845894"
---
# <a name="hasiteratordebugging"></a>_HAS_ITERATOR_DEBUGGING

Durch [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md) ersetzt, definiert dieses Makro, ob die Iteratordebugfunktion in einem Debugbuild aktiviert ist. Standardmäßig ist das Iteratordebuggen in Debugbuilds aktiviert und in Verkaufsversionen deaktiviert. Weitere Informationen finden Sie unter [Debugiterator-Unterstützung](../standard-library/debug-iterator-support.md).

> [!IMPORTANT]
> Die direkte Verwendung des `_HAS_ITERATOR_DEBUGGING`-Makros ist veraltet. Verwenden Sie stattdessen `_ITERATOR_DEBUG_LEVEL`, um Iteratordebugeinstellungen zu steuern. Weitere Informationen finden Sie unter [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md).

## <a name="remarks"></a>Hinweise

Legen Sie in Debugbuilds `_ITERATOR_DEBUG_LEVEL` auf 2 fest, um das Iteratordebuggen zu aktivieren. Dies entspricht einer `_HAS_ITERATOR_DEBUGGING`-Einstellung von 1 oder aktiviert:

```cpp
#define _ITERATOR_DEBUG_LEVEL 2
```

`_ITERATOR_DEBUG_LEVEL` kann in Verkaufsversionen nicht auf 2 festgelegt werden (und `_HAS_ITERATOR_DEBUGGING` nicht auf 1).

Legen Sie zum Deaktivieren des Debuggens der Iteratoren `_ITERATOR_DEBUG_LEVEL` auf 0 oder 1 in Debugbuilds. Dies entspricht einer `_HAS_ITERATOR_DEBUGGING`-Einstellung von 0 oder deaktiviert:

```cpp
#define _ITERATOR_DEBUG_LEVEL 0
```

## <a name="see-also"></a>Siehe auch

[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)<br/>
[Debug Iterator Support](../standard-library/debug-iterator-support.md)<br/>
[Checked Iterators](../standard-library/checked-iterators.md)<br/>
[Sichere Bibliotheken: C++-Standardbibliothek](../standard-library/safe-libraries-cpp-standard-library.md)<br/>
