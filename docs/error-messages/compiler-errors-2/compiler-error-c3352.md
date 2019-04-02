---
title: Compilerfehler C3352
ms.date: 11/04/2016
f1_keywords:
- C3352
helpviewer_keywords:
- C3352
ms.assetid: f233bed7-474e-425f-aad2-7801578169d4
ms.openlocfilehash: 6641f05c8daa5ad505c0bcb8d29a369ad5fd9a9a
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58779598"
---
# <a name="compiler-error-c3352"></a>Compilerfehler C3352

'Funktion': die angegebene Funktion entspricht nicht den Typ des Delegaten 'Typ'

Die Parameterlisten für `function` und der Delegat stimmen nicht überein.

Weitere Informationen finden Sie unter [Delegate (Komponentenerweiterungen)](../../extensions/delegate-cpp-component-extensions.md).

Im folgende Beispiel wird die C3352 generiert:

```
// C3352.cpp
// compile with: /clr
delegate int D( int, int );
ref class C {
public:
   int mf( int ) {
      return 1;
   }

   // Uncomment the following line to resolve.
   // int mf(int, int) { return 1; }
};

int main() {
   C^ pC = gcnew C;
   System::Delegate^ pD = gcnew D( pC, &C::mf );   // C3352
}
```
