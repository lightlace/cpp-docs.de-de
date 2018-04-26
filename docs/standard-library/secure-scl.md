---
title: _SECURE_SCL | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- _SECURE_SCL
dev_langs:
- C++
helpviewer_keywords:
- _SECURE_SCL
ms.assetid: 4ffbc788-cc12-4c6a-8cd7-490081675086
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b75342fb28d31c9249657080c0abf10d0e99391b
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="securescl"></a>_SECURE_SCL

Ersetzt durch [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md), dieses Makro definiert, ob [Überprüfte Iteratoren](../standard-library/checked-iterators.md) aktiviert sind. Standardmäßig sind „Überprüfte Iteratoren“ in Debugbuilds aktiviert und in Verkaufsversionen deaktiviert.

> [!IMPORTANT]
> Die direkte Verwendung des `_SECURE_SCL`-Makros ist veraltet. Verwenden Sie stattdessen `_ITERATOR_DEBUG_LEVEL`, um die Einstellungen von überprüften Iteratoren zu steuern. Weitere Informationen finden Sie unter [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md).

## <a name="remarks"></a>Hinweise

Wenn überprüfte Iteratoren aktiviert sind, verursacht die unsichere Verwendung einen Laufzeitfehler und das Programm wird beendet. Um überprüfte Iteratoren zu aktivieren, legen Sie `_ITERATOR_DEBUG_LEVEL` auf 1 oder 2 fest. Dies entspricht der `_SECURE_SCL`-Einstellung 1 oder „Aktiviert“:

```cpp
#define _ITERATOR_DEBUG_LEVEL 1
```

Um überprüfte Iteratoren zu deaktivieren, legen Sie `_ITERATOR_DEBUG_LEVEL` auf 0 fest. Dies entspricht der `_SECURE_SCL`-Einstellung 0 oder „Deaktiviert“:

```cpp
#define _ITERATOR_DEBUG_LEVEL 0
```

Informationen über das Deaktivieren von Warnungen für überprüfte Iteratoren finden Sie unter [_SCL_SECURE_NO_WARNINGS](../standard-library/scl-secure-no-warnings.md).

## <a name="see-also"></a>Siehe auch

[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)<br/>
[Checked Iterators](../standard-library/checked-iterators.md)<br/>
[Debug Iterator Support](../standard-library/debug-iterator-support.md)<br/>
[Sichere Bibliotheken: C++-Standardbibliothek](../standard-library/safe-libraries-cpp-standard-library.md)<br/>
