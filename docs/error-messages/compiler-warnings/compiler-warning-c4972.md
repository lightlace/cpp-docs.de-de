---
title: Compilerwarnung C4972
ms.date: 11/04/2016
f1_keywords:
- C4972
helpviewer_keywords:
- C4972
ms.assetid: d18e8e65-b2ef-4d75-a207-fbd0c17c9060
ms.openlocfilehash: 7c58258298fb91d04014e719732135a1f33f13b6
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "58777076"
---
# <a name="compiler-warning-c4972"></a>Compilerwarnung C4972

Das direkte Ändern oder Behandeln des Ergebnisses eines Unboxing-Vorgangs als L-Wert kann nicht überprüft werden.

Das Dereferenzieren eines Handles für einen Werttyp (auch als Unboxing bezeichnet) und das anschließende Zuweisen ist nicht überprüfbar.

Weitere Informationen finden Sie unter [Boxing](../../extensions/boxing-cpp-component-extensions.md)definiert sind.

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