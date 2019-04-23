---
title: Compilerfehler C3114
ms.date: 11/04/2016
f1_keywords:
- C3114
helpviewer_keywords:
- C3114
ms.assetid: b5d2df4f-87d0-4292-9981-25c6a6013c05
ms.openlocfilehash: c5a4feae5c8805a27c020b532fd58e0562e46b6b
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59775593"
---
# <a name="compiler-error-c3114"></a>Compilerfehler C3114

'Argument': kein gültiges benanntes Attributargument.

In der Reihenfolge für Datenmember einer Attributklasse ein benanntes Argument gültig ist, es muss nicht gekennzeichnet werden `static`, `const`, oder `literal`. Wenn eine Eigenschaft, die Eigenschaft muss nicht `static` und muss über get- und set-Accessoren.

Weitere Informationen finden Sie unter [Eigenschaft](../../extensions/property-cpp-component-extensions.md) und [User-Defined Attributes](../../extensions/user-defined-attributes-cpp-component-extensions.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3114 generiert.

```
// C3114.cpp
// compile with: /clr /c
public ref class A : System::Attribute {
public:
   static property int StaticProp {
      int get();
   }

   property int Prop2 {
      int get();
      void set(int i);
   }
};

[A(StaticProp=123)]   // C3114
public ref class R {};

[A(Prop2=123)]   // OK
public ref class S {};
```