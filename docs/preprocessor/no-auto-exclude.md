---
title: no_auto_exclude
ms.date: 11/04/2016
f1_keywords:
- no_auto_exclude
helpviewer_keywords:
- no_auto_exclude attribute
ms.assetid: 3241ef9c-758a-4e86-bdc5-37da6072430f
ms.openlocfilehash: 06bde7535bd181057750ab9dd4c3999321b4990c
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59038941"
---
# <a name="noautoexclude"></a>no_auto_exclude
**C++-spezifisch**

Deaktiviert den automatische Ausschluss.

## <a name="syntax"></a>Syntax

```
no_auto_exclude
```

## <a name="remarks"></a>Hinweise

Typbibliotheken können Definitionen der Elemente enthalten, die in Systemheadern oder anderen Typbibliotheken definiert sind. `#import` versucht, mehrfache definitionsfehler zu vermeiden, indem Sie solche Elemente automatisch ausgeschlossen. Wenn dies abgeschlossen ist, [Compilerwarnung (Stufe 3) C4192](../error-messages/compiler-warnings/compiler-warning-level-3-c4192.md) für die einzelnen Elemente ausgeschlossen werden ausgegeben. Sie können diesen automatischen Ausschluss deaktivieren, indem Sie dieses Attribut verwenden.

**Ende C++-spezifisch**

## <a name="see-also"></a>Siehe auch

[#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import-Anweisung](../preprocessor/hash-import-directive-cpp.md)