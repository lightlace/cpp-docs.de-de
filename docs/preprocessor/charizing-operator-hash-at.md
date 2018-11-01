---
title: Zeichenoperator (#@)
ms.date: 11/04/2016
f1_keywords:
- '#@'
helpviewer_keywords:
- preprocessor, operators
- charizing operator
- '#@ preprocessor operator'
ms.assetid: dee03314-d27c-4063-965c-64756efbef22
ms.openlocfilehash: 7259487a3289173bc77517c8c616638c370041c4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50568339"
---
# <a name="charizing-operator-"></a>Zeichenoperator (#@)
**Microsoft-spezifisch**

Der Zeichenoperator kann nur mit Argumenten von Makros verwendet werden. Wenn `#@` steht einen formalen Parameter in der Definition des Makros ist das tatsächliche Argument in einfache Anführungszeichen eingeschlossen und als Zeichen behandelt wird, wenn das Makro erweitert wird. Zum Beispiel:

```
#define makechar(x)  #@x
```

führt dazu, dass die Anweisung

```
a = makechar(b);
```

erweitert wird auf

```
a = 'b';
```

Das einfache Anführungszeichen kann nicht mit dem Zeichenoperator verwendet werden.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Präprozessoroperatoren](../preprocessor/preprocessor-operators.md)