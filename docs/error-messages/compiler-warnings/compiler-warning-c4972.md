---
title: Compilerwarnung C4972
ms.date: 11/04/2016
f1_keywords:
- C4972
helpviewer_keywords:
- C4972
ms.assetid: d18e8e65-b2ef-4d75-a207-fbd0c17c9060
ms.openlocfilehash: dcf08f26809c7c61e3e00c41c555416c95f4a0e0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50598834"
---
# <a name="compiler-warning-c4972"></a>Compilerwarnung C4972

Das direkte Ändern oder Behandeln des Ergebnisses eines Unboxing-Vorgangs als L-Wert kann nicht überprüft werden.

Das Dereferenzieren eines Handles für einen Werttyp (auch als Unboxing bezeichnet) und das anschließende Zuweisen ist nicht überprüfbar.

Weitere Informationen finden Sie unter [Boxing](../../windows/boxing-cpp-component-extensions.md)definiert sind.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4972 generiert.

```
// C4972.cpp
// compile with: /clr:safe
using namespace System;
ref struct R {
   int ^ p;   // a value type
};

int main() {
   R ^ r = gcnew R;
   *(r->p) = 10;   // C4972

   // OK
   r->p = 10;
   Console::WriteLine( r->p );
   Console::WriteLine( *(r->p) );
}
```