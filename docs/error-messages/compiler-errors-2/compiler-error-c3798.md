---
title: Compilerfehler C3798
ms.date: 11/04/2016
f1_keywords:
- C3798
helpviewer_keywords:
- C3798
ms.assetid: b2f8b1d8-8812-49b8-a346-28e48f02ba5c
ms.openlocfilehash: a11c88f536e3282e887e32ef437077e61f4424cc
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58773267"
---
# <a name="compiler-error-c3798"></a>Compilerfehler C3798

"Spezifizierer": Eigenschaftendeklaration darf keinen Überschreibungsspezifizierer (sollte in der Eigenschaft Get/Set-Methoden stattdessen platziert werden)

Eine Eigenschaft wurde falsch deklariert. Weitere Informationen finden Sie unter

- [Eigenschaft](../../extensions/property-cpp-component-extensions.md)

- [abstract](../../extensions/abstract-cpp-component-extensions.md)

- [sealed](../../extensions/sealed-cpp-component-extensions.md)

## <a name="example"></a>Beispiel

Im folgende Beispiel wird C3798 generiert:

```
// C3798.cpp
// compile with: /clr /c
ref struct A {
   property int Prop_1 abstract;   // C3798
   property int Prop_2 sealed;   // C3798

   // OK
   property int Prop_3 {
      virtual int get() abstract;
      virtual void set(int i) abstract;
   }

   property int Prop_4 {
      virtual int get() sealed;
      virtual void set(int i) sealed;
   }
};
```