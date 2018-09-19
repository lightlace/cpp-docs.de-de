---
title: Compilerfehler C3536 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3536
dev_langs:
- C++
helpviewer_keywords:
- C3536
ms.assetid: 8d866075-866b-49eb-9979-ee27b308f7e3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7585a75ebe9733c228756e92d8e5ae57699aca27
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46088578"
---
# <a name="compiler-error-c3536"></a>Compilerfehler C3536

'Symbol': kann nicht verwendet werden, bevor es initialisiert wird

Das angegebene Symbol kann nicht verwendet werden, bevor es initialisiert wird. In der Praxis bedeutet dies, dass eine Variable nicht verwendet werden kann, um sich selbst zu initialisieren.

### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

1. Initialisieren Sie eine Variable mit sich selbst nicht.

## <a name="example"></a>Beispiel

Im folgende Beispiel C3536 erzeugt, weil jede Variable, mit sich selbst initialisiert wird.

```
// C3536.cpp
// Compile with /Zc:auto
int main()
{
   auto a = a;     //C3536
   auto b = &b;    //C3536
   auto c = c + 1; //C3536
   auto* d = &d;   //C3536
   auto& e = e;    //C3536
   return 0;
};
```

## <a name="see-also"></a>Siehe auch

[Auto-Schlüsselwort](../../cpp/auto-keyword.md)