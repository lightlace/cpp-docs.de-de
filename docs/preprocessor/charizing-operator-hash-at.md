---
title: Zeichenoperator (#@) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- '#@'
dev_langs:
- C++
helpviewer_keywords:
- preprocessor, operators
- charizing operator
- '#@ preprocessor operator'
ms.assetid: dee03314-d27c-4063-965c-64756efbef22
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d86c49c8d7d0cda91ba2415167cc79c810a96b3d
ms.sourcegitcommit: d10a2382832373b900b1780e1190ab104175397f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43895304"
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