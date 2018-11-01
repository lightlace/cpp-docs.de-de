---
title: Compilerfehler C3902
ms.date: 11/04/2016
f1_keywords:
- C3902
helpviewer_keywords:
- C3902
ms.assetid: feb3bb29-f836-4d77-ba71-3876f7f4f216
ms.openlocfilehash: 22536f380187c6dceac3e355224d9d118cd1a2df
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50564527"
---
# <a name="compiler-error-c3902"></a>Compilerfehler C3902

"Accessor": Typ des letzten Parameters muss 'Type'

Der Typ des letzten Parameters des Set-Methode, die mindestens eine muss den Typ der Eigenschaft übereinstimmen. Weitere Informationen finden Sie unter [property](../../windows/property-cpp-component-extensions.md).

Im folgende Beispiel wird die C3902 generiert:

```
// C3902.cpp
// compile with: /clr /c
using namespace System;
ref class X {
   property String ^Name {
      void set(int);   // C3902
      // try the following line instead
      // void set(String^){}
   }

   property double values[int,int] {
      void set(int, int, float);   // C3902
      // try the following line instead
      // void set(int, int, double){}
   }
};
```