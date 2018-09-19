---
title: Compilerfehler C3530 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3530
dev_langs:
- C++
helpviewer_keywords:
- C3530
ms.assetid: 21be81ce-b699-4c74-81bc-80a0c34d2d5a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5866e2ea44b84f3afeb0cef8423abc28f8e056ab
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46094792"
---
# <a name="compiler-error-c3530"></a>Compilerfehler C3530

'Auto' kann nicht mit einem anderen Typspezifizierer kombiniert werden

Ein Typspezifizierer der Verwendung der `auto` Schlüsselwort.

### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

1. Verwenden Sie keinen Typspezifizierer in einer Variablendeklaration, die verwendet die `auto` Schlüsselwort.

## <a name="example"></a>Beispiel

Das folgenden Beispiel wird C3530 erzeugt, weil Variablen `x` wird deklariert, mit der `auto` -Schlüsselwort und Typ `int`, und da im Beispiel wird die Kompilierung mit **/Zc: Auto**.

```
// C3530.cpp
// Compile with /Zc:auto
int main()
{
   auto int x;   // C3530
   return 0;
}
```

## <a name="see-also"></a>Siehe auch

[Auto-Schlüsselwort](../../cpp/auto-keyword.md)