---
title: Compilerfehler C3375
ms.date: 11/04/2016
f1_keywords:
- C3375
helpviewer_keywords:
- C3375
ms.assetid: f1df78c6-e6ca-48f3-8b29-4e1710002bf3
ms.openlocfilehash: b3dfc17f9df495fe6907b816bace0dac1eff08cc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50545274"
---
# <a name="compiler-error-c3375"></a>Compilerfehler C3375

'Funktion': Mehrdeutige Delegatfunktion.

Ein Delegat wurde möglicherweise als statische Memberfunktion oder ein ungebundener Delegat als Instanzfunktion instanziiert, daher hat der Compiler diesen Fehler ausgelöst.

Weitere Informationen finden Sie unter [Delegate (Komponentenerweiterungen)](../../windows/delegate-cpp-component-extensions.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3375 generiert:

```
// C3375.cpp
// compile with: /clr
ref struct R {
   static void f(R^) {}
   void f() {}
};

delegate void Del(R^);

int main() {
   Del ^ a = gcnew Del(&R::f);   // C3375
}
```