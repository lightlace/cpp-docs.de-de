---
title: Compilerfehler C3298
ms.date: 11/04/2016
f1_keywords:
- C3298
helpviewer_keywords:
- C3298
ms.assetid: 458c2680-95bb-4d5e-895f-ce4115844193
ms.openlocfilehash: d5e9586b026e0092491c80c23f55080354c9e465
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760074"
---
# <a name="compiler-error-c3298"></a>Compilerfehler C3298

"constraint_1": "constraint_2" kann nicht als Einschränkung verwendet werden, da "constraint_2" die ref-Einschränkung und "constraint_1" die Werteinschränkung aufweist.

Sie können keine sich gegenseitig ausschließende Eigenschaften für eine Einschränkung angeben. Beispielsweise kann ein generischer Typparameter nicht gleichzeitig auf einen Werttyp und einen Referenztyp eingeschränkt werden.

Weitere Informationen finden Sie unter [Einschränkungen für generische Typparameter (C++/CLI)](../../extensions/constraints-on-generic-type-parameters-cpp-cli.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3298 generiert:

```cpp
// C3298.cpp
// compile with: /clr /c
generic<class T, class U>
where T : ref class
where U : T, value class   // C3298
public ref struct R {};
```
