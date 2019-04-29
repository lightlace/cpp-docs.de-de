---
title: Compilerfehler C3797
ms.date: 11/04/2016
f1_keywords:
- C3797
helpviewer_keywords:
- C3797
ms.assetid: ab27ff34-8c1d-4297-b004-9e39bd3a4f25
ms.openlocfilehash: 76206cdffce3f551ff472cbd83df486eb41ae80b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400135"
---
# <a name="compiler-error-c3797"></a>Compilerfehler C3797

"override": Ereignisdeklaration darf keinen Überschreibungsspezifizierer (sollte platziert werden. auf Ereignis hinzufügen/entfernen/Raise-Methoden stattdessen)

Ein triviales Ereignis (ein Ereignis ohne explizit definierte Accessormethoden) mit einem anderen triviales Ereignis kann nicht überschrieben werden. Das Ereignis überschreiben muss deren Verhalten mit Accessor-Funktionen definieren.

Weitere Informationen finden Sie unter [Ereignis](../../extensions/event-cpp-component-extensions.md).

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