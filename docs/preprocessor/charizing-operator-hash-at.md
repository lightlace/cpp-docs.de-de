---
title: Zeichenoperator (#@)
ms.date: 08/29/2019
f1_keywords:
- '#@'
helpviewer_keywords:
- preprocessor, operators
- charizing operator
- '#@ preprocessor operator'
ms.assetid: dee03314-d27c-4063-965c-64756efbef22
ms.openlocfilehash: cb2a4e07287edf5ed2d0850ec7d870c8ef307879
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70218533"
---
# <a name="charizing-operator-"></a>Zeichenoperator (#@)

**Microsoft-spezifisch**

Der Zeichenoperator kann nur mit Argumenten von Makros verwendet werden. Wenn `#@` einem formalen Parameter in der Definition des Makros vorangestellt wird, wird das tatsächliche Argument in einfache Anführungszeichen eingeschlossen und als Zeichen behandelt, wenn das Makro erweitert wird. Beispiel:

```cpp
#define makechar(x)  #@x
```

führt dazu, dass die Anweisung

```cpp
a = makechar(b);
```

erweitert wird auf

```cpp
a = 'b';
```

Das einfache Anführungszeichen (`'`) kann nicht mit dem Zeichen Operator verwendet werden.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Präprozessoroperatoren](../preprocessor/preprocessor-operators.md)
