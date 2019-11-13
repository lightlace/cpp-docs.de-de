---
title: Compilerwarnung (Stufe 1) C4806
ms.date: 11/04/2016
f1_keywords:
- C4806
helpviewer_keywords:
- C4806
ms.assetid: 79eb74cd-b925-4b5b-84e1-8ae6f33e38b3
ms.openlocfilehash: dae6ed7d7a38daf0ce525ae62409823212db711b
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052362"
---
# <a name="compiler-warning-level-1-c4806"></a>Compilerwarnung (Stufe 1) C4806

"operation": unsichere Operation: kein Wert vom Typ "type" erweitert auf Typ "type" kann mit der angegebenen Konstante übereinstimmen

Diese Meldung warnt Sie vor Code wie `b == 3`, wobei `b` Typ `bool`aufweist. Aufgrund der Erweiterungsregeln wird `bool` auf `int`erweitert. Dies ist zulässig, es kann aber nie **true**sein. Im folgenden Beispiel wird C4806 generiert:

```cpp
// C4806.cpp
// compile with: /W1
int main()
{
   bool b = true;
   // try..
   // int b = true;

   if (b == 3)   // C4806
   {
      b = false;
   }
}
```