---
title: Compilerfehler C3901
ms.date: 11/04/2016
f1_keywords:
- C3901
helpviewer_keywords:
- C3901
ms.assetid: 19af4141-39ad-4c16-a68f-3ae76f648186
ms.openlocfilehash: 31fbb1e89a0619b4dc8b3f6c86f7f6bc748b80d6
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2019
ms.locfileid: "64344583"
---
# <a name="compiler-error-c3901"></a>Compilerfehler C3901

'Accessor_function': muss den Rückgabetyp 'Typ' haben

Rückgabetyp für mindestens eine Get-Methode muss mit den Eigenschaftentyp übereinstimmen. Weitere Informationen finden Sie unter [property](../../extensions/property-cpp-component-extensions.md).

Im folgende Beispiel wird die C3901 generiert:

```
// C3901.cpp
// compile with: /clr /c
using namespace System;
ref class X {
   property String^ Name {
      void get();   // C3901
      // try the following line instead
      // String^ get();
   };
};

ref class Y {
   property double values[int, int] {
      int get(int, int);   // C3901
      // try the following line instead
      // double get(int, int);
   };
};
```