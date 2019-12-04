---
title: Compilerfehler C3077
ms.date: 11/04/2016
f1_keywords:
- C3077
helpviewer_keywords:
- C3077
ms.assetid: d9f3c619-d1e2-4656-81a5-a35a9586a7d4
ms.openlocfilehash: b2dfe4c17ee122baa8f648669f9080b28584a66f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756733"
---
# <a name="compiler-error-c3077"></a>Compilerfehler C3077

„finalizer“: Ein Finalizer kann nur ein Member eines Verweistyps sein.

Ein Finalizer kann nicht in einem systemeigenen oder Werttyp deklariert werden.

Weitere Informationen finden Sie unter [debugtoren und Finalizer in Gewusst wie: definieren und Verarbeiten von Klassen und StrukturenC++(/CLI)](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3077 generiert:

```cpp
// C3077.cpp
// compile with: /clr /c
value struct vs {
   !vs(){}   // C3077
};

ref struct rs {
protected:
   !rs(){}   // OK
};
```
