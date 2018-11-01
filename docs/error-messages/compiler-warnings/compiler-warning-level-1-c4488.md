---
title: Compilerwarnung (Stufe 1) C4488
ms.date: 11/04/2016
f1_keywords:
- C4488
helpviewer_keywords:
- C4488
ms.assetid: 55625e46-ddb5-4c7c-99c7-cd4aa9f879bd
ms.openlocfilehash: c816c1b3f5481ccff19fd2a2377c5fc98f950fee
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50577826"
---
# <a name="compiler-warning-level-1-c4488"></a>Compilerwarnung (Stufe 1) C4488

'Funktion': 'Schlüsselwort' Schlüsselwort muss die Schnittstelle '-Schnittstellenmethode ' implementieren

Eine Klasse muss alle Member einer Schnittstelle implementieren, von dem sie direkt erbt. Ein implementierter Member muss öffentliche zugriffsmöglichkeiten aufweisen, und Sie müssen als virtuell markiert werden.

## <a name="example"></a>Beispiel

C4488 kann auftreten, wenn auf ein implementierter Member nicht öffentlich ist. Im folgende Beispiel wird die C4488 generiert.

```
// C4488.cpp
// compile with: /clr /c /W1 /WX
interface struct MyI {
   void f1();
};

// implemented member not public
ref class B : MyI { virtual void f1() {} };  // C4488

// OK
ref class C : MyI {
public:
   virtual void f1() {}
};
```

## <a name="example"></a>Beispiel

C4488 kann auftreten, wenn ein implementierter Member nicht als virtuell gekennzeichnet ist. Im folgende Beispiel wird die C4488 generiert.

```
// C4488_b.cpp
// compile with: /clr /c /W1 /WX
interface struct MyI {
   void f1();
};

ref struct B : MyI { void f1() {} };   // C4488
ref struct C : MyI { virtual void f1() {} };   // OK
```