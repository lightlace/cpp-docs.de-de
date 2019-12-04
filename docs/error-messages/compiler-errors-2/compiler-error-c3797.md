---
title: Compilerfehler C3797
ms.date: 11/04/2016
f1_keywords:
- C3797
helpviewer_keywords:
- C3797
ms.assetid: ab27ff34-8c1d-4297-b004-9e39bd3a4f25
ms.openlocfilehash: 7236cb75aef4250440a1e992415df07fb5b7da3f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757175"
---
# <a name="compiler-error-c3797"></a>Compilerfehler C3797

' override ': die Ereignis Deklaration darf keinen Überschreibungsspezifizierer aufweisen (sollte stattdessen auf dem Ereignis Add/Remove/Raise-Methoden platziert werden).

Es ist nicht möglich, ein triviales Ereignis (ein Ereignis ohne explizit definierte Zugriffsmethoden) mit einem anderen trivialen Ereignis zu überschreiben. Das Überschreibungs Ereignis muss sein Verhalten mit Accessorfunktionen definieren.

Weitere Informationen finden Sie unter [Event](../../extensions/event-cpp-component-extensions.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3797 generiert.

```cpp
// C3797.cpp
// compile with: /clr /c
delegate void MyDel();

ref class Class1 {
public:
   virtual event MyDel ^ E;
};

ref class Class2 : public Class1 {
public:
   virtual event MyDel ^ E override;   // C3797
};

// OK
ref class Class3 : public Class1 {
public:
   virtual event MyDel ^ E {
      void add(MyDel ^ d) override {}
      void remove(MyDel ^ d) override {}
   }
};
```
