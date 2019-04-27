---
title: Compilerfehler C3298
ms.date: 11/04/2016
f1_keywords:
- C3298
helpviewer_keywords:
- C3298
ms.assetid: 458c2680-95bb-4d5e-895f-ce4115844193
ms.openlocfilehash: fe6913d402c6ce4df3551c159eb56a12590799cb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62222530"
---
# <a name="compiler-error-c3298"></a>Compilerfehler C3298

"constraint_1": "constraint_2" kann nicht als Einschränkung verwendet werden, da "constraint_2" die ref-Einschränkung und "constraint_1" die Werteinschränkung aufweist.

Sie können keine sich gegenseitig ausschließende Eigenschaften für eine Einschränkung angeben. Beispielsweise kann ein generischer Typparameter nicht gleichzeitig auf einen Werttyp und einen Referenztyp eingeschränkt werden.

Weitere Informationen finden Sie unter [Einschränkungen für generische Typparameter (C++ / CLI)](../../extensions/constraints-on-generic-type-parameters-cpp-cli.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3298 generiert:

```
// C3298.cpp
// compile with: /clr /c
generic<class T, class U>
where T : ref class
where U : T, value class   // C3298
public ref struct R {};
```