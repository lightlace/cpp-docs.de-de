---
title: Compilerfehler C3374
ms.date: 11/04/2016
f1_keywords:
- C3374
helpviewer_keywords:
- C3374
ms.assetid: 41431299-bd20-47d4-a0c8-1334dd79018b
ms.openlocfilehash: c9ee9130d77e844ab435ecc34dcf53e12449abba
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50474931"
---
# <a name="compiler-error-c3374"></a>Compilerfehler C3374

Übernehmen der Adresse der 'Funktion' nicht möglich, außer bei Erstellung der Delegatinstanz

Die Adresse einer Funktion wurde in einem anderen Kontext als bei der Erstellung einer Delegatinstanz übernommen.

Im folgenden Beispiel wird C3374 generiert:

```
// C3374.cpp
// compile with: /clr
public delegate void MyDel(int i);

ref class A {
public:
   void func1(int i) {
      System::Console::WriteLine("in func1 {0}", i);
   }
};

int main() {
   &A::func1;   // C3374

   // OK
   A ^ a = gcnew A;
   MyDel ^ StaticDelInst = gcnew MyDel(a, &A::func1);
}
```

## <a name="see-also"></a>Siehe auch

[Vorgehensweise: Definieren und Verwenden von Delegaten (C++/CLI)](../../dotnet/how-to-define-and-use-delegates-cpp-cli.md)