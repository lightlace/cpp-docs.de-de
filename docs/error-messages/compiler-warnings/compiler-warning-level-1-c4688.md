---
title: Compilerwarnung (Stufe 1) C4688
ms.date: 11/04/2016
f1_keywords:
- C4688
helpviewer_keywords:
- C4688
ms.assetid: a027df3c-b2b8-4c49-8539-c2bc42db74e8
ms.openlocfilehash: f37b5ed43d375c5ee31eb233ce49f7ec88200155
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50559925"
---
# <a name="compiler-warning-level-1-c4688"></a>Compilerwarnung (Stufe 1) C4688

"constraint": Die Einschränkungsliste enthält den privaten Assemblytyp "type".

Eine Einschränkungsliste enthält einen privaten Assemblytyp, ist also nicht verfügbar, wenn auf den Typ von außerhalb der Assembly zugegriffen wird. Weitere Informationen finden Sie unter [Generika](../../windows/generics-cpp-component-extensions.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4688 generiert:

```
// C4688.cpp
// compile with: /clr /c /W1
ref struct A {};   // private type
public ref struct B {};

// Delete the following 3 lines to resolve.
generic <class T>
where T : A   // C4688
public ref struct M {};

generic <class T>
where T : B
public ref struct N {};
```