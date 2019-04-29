---
title: Compilerfehler C3830
ms.date: 11/04/2016
f1_keywords:
- C3830
helpviewer_keywords:
- C3830
ms.assetid: c9798f88-5001-4067-9fb1-09957ddc6fa8
ms.openlocfilehash: 25f2b86e21d4672c9e0907c366da17072bafa183
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62390541"
---
# <a name="compiler-error-c3830"></a>Compilerfehler C3830

"Typ1": kann nicht von 'type2', Wert Typen können nur von Schnittstellenklassen erben erben

Ein Werttyp kann nicht auf eine Basisklasse erben.  Weitere Informationen finden Sie unter [Klassen und Strukturen](../../extensions/classes-and-structs-cpp-component-extensions.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3830 generiert:

```
// C3830a.cpp
// compile with: /clr /c
public value struct MyStruct4 {
   int i;
};

public value class MyClass : public MyStruct4 {};   // C3830

// OK
public interface struct MyInterface4 {
   void i();
};

public value class MyClass2 : public MyInterface4 {
public:
   virtual void i(){}
};
```
