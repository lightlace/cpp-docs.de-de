---
title: Compilerfehler C3797
ms.date: 11/04/2016
f1_keywords:
- C3797
helpviewer_keywords:
- C3797
ms.assetid: ab27ff34-8c1d-4297-b004-9e39bd3a4f25
ms.openlocfilehash: 2c8570edf16b9c002f9506b1b179a2ab36f7f26e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50557531"
---
# <a name="compiler-error-c3797"></a>Compilerfehler C3797

"override": Ereignisdeklaration darf keinen Überschreibungsspezifizierer (sollte platziert werden. auf Ereignis hinzufügen/entfernen/Raise-Methoden stattdessen)

Ein triviales Ereignis (ein Ereignis ohne explizit definierte Accessormethoden) mit einem anderen triviales Ereignis kann nicht überschrieben werden. Das Ereignis überschreiben muss deren Verhalten mit Accessor-Funktionen definieren.

Weitere Informationen finden Sie unter [Ereignis](../../windows/event-cpp-component-extensions.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3797 generiert.

```
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