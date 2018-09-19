---
title: Compilerfehler C3287 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3287
dev_langs:
- C++
helpviewer_keywords:
- C3287
ms.assetid: c1fa73d2-2c82-4136-a7da-0e75e3b420ad
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b7e91878b6c6809fb875380430496db6d6e0b065
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46067453"
---
# <a name="compiler-error-c3287"></a>Compilerfehler C3287

Der Typ 'Typ' (Rückgabetyp von 'GetEnumerator') muss eine passende öffentliche MoveNext-Memberfunktion und eine öffentliche Current-Eigenschaft aufweisen.

Benutzerdefinierte Auflistungsklassen müssen Definitionen für `MoveNext` und `Current`enthalten.

Weitere Informationen finden Sie unter [Gewusst wie: Durchlaufen einer benutzerdefinierten Auflistung mit der for-each-Klausel](../../dotnet/how-to-iterate-over-a-user-defined-collection-with-for-each.md) .

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3287 generiert:

```
// C3287.cpp
// compile with: /clr
using namespace System;

ref struct R {
   bool MoveNext() {
      return true;
   }
   property Object^ Current {
      Object^ get() {
         Object ^ o = gcnew Object;
         return o;
      }
   }
};

ref struct R2 {
   R ^GetEnumerator() {
      R^ r = gcnew R;
      return r;
   }
};

ref struct T {};

ref struct T2 {
   T ^GetEnumerator() {
      T^ t = gcnew T;
      return t;
   }
};

int main() {
   for each (int i in gcnew T2) {}   // C3287
   for each (int i in gcnew R2) {}   // OK
}
```