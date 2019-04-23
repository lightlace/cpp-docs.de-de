---
title: Compilerfehler C3352
ms.date: 11/04/2016
f1_keywords:
- C3352
helpviewer_keywords:
- C3352
ms.assetid: f233bed7-474e-425f-aad2-7801578169d4
ms.openlocfilehash: 6641f05c8daa5ad505c0bcb8d29a369ad5fd9a9a
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59778331"
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
