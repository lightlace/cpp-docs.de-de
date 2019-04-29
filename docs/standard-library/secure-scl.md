---
title: _SECURE_SCL
ms.date: 11/04/2016
f1_keywords:
- _SECURE_SCL
helpviewer_keywords:
- _SECURE_SCL
ms.assetid: 4ffbc788-cc12-4c6a-8cd7-490081675086
ms.openlocfilehash: dcfaee2906136dffbe79a49f089a079104112e78
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62295746"
---
# <a name="securescl"></a>_SECURE_SCL

Ersetzt durch [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md), dieses Makro definiert, ob [Überprüfte Iteratoren](../standard-library/checked-iterators.md) aktiviert sind. Standardmäßig sind „Überprüfte Iteratoren“ in Debugbuilds aktiviert und in Verkaufsversionen deaktiviert.

> [!IMPORTANT]
> Direkte Verwendung des Makros _SECURE_SCL ist veraltet. Verwenden Sie stattdessen _ITERATOR_DEBUG_LEVEL, steuerelementeinstellungen überprüft Iterator. Weitere Informationen finden Sie unter [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md).

## <a name="remarks"></a>Hinweise

Wenn überprüfte Iteratoren aktiviert sind, verursacht die unsichere Verwendung einen Laufzeitfehler und das Programm wird beendet. Um überprüfte Iteratoren zu aktivieren, legen Sie _ITERATOR_DEBUG_LEVEL auf 1 oder 2 ein. Dies entspricht der Einstellung _SECURE_SCL 1 oder aktiviert:

```cpp
#define _ITERATOR_DEBUG_LEVEL 1
```

Um überprüfte Iteratoren zu deaktivieren, legen Sie _ITERATOR_DEBUG_LEVEL auf 0 fest. Dies ist gleichbedeutend mit _SECURE_SCL Einstellung 0 oder deaktiviert:

```cpp
#define _ITERATOR_DEBUG_LEVEL 0
```

Informationen über das Deaktivieren von Warnungen für überprüfte Iteratoren finden Sie unter [_SCL_SECURE_NO_WARNINGS](../standard-library/scl-secure-no-warnings.md).

## <a name="see-also"></a>Siehe auch

[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)<br/>
[Checked Iterators](../standard-library/checked-iterators.md)<br/>
[Debug Iterator Support](../standard-library/debug-iterator-support.md)<br/>
[Sichere Bibliotheken: C++-Standardbibliothek](../standard-library/safe-libraries-cpp-standard-library.md)<br/>
