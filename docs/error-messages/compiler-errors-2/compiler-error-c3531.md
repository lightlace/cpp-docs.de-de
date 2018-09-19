---
title: Compilerfehler C3531 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3531
dev_langs:
- C++
helpviewer_keywords:
- C3531
ms.assetid: 2bdb9fdc-9ddf-403e-8b92-02763d434487
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 375eb419e3f2f492df328a964eeb1bb77bc0d5dd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46106845"
---
# <a name="compiler-error-c3531"></a>Compilerfehler C3531

'Symbol': ein Symbol, dessen Typ enthält, 'auto' muss einen Initialisierer aufweisen.

Die angegebene Variable muss einen Initialisiererausdruck nicht.

### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

1. Geben Sie einen Initialisiererausdruck, z. B. eine einfache Zuweisung, die Gleichheitszeichen Syntax verwendet, wenn Sie die Variable deklarieren.

## <a name="example"></a>Beispiel

Im folgende Beispiel C3531, da Variablen `x1`, `y1, y2, y3`, und `z2` nicht initialisiert werden.

```
// C3531.cpp
// Compile with /Zc:auto
int main()
{
   auto x1;                  // C3531
   auto y1, y2, y3;          // C3531
   auto z1 = 1, z2, z3 = -1; // C3531
   return 0;
}
```

## <a name="see-also"></a>Siehe auch

[Auto-Schlüsselwort](../../cpp/auto-keyword.md)