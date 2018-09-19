---
title: Compilerwarnung (Stufe 4) C4487 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4487
dev_langs:
- C++
helpviewer_keywords:
- C4487
ms.assetid: 796144cf-cd3c-4edc-b6a4-96192b7eb4f0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ffc1a25d362cad95f2aad43d626e4918955903f5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46135840"
---
# <a name="compiler-warning-level-4-c4487"></a>Compilerwarnung (Stufe 4) C4487

'Abgeleitete_Klassenfunktion': entspricht der geerbten nicht virtuellen Methode "Basisklassenfunktion" aber ist nicht explizit als "new"

Eine Funktion in einer abgeleiteten Klasse hat die gleiche Signatur wie eine nicht virtuelle Basisklasse-Funktion. C4487 erinnert Sie daran, dass die Funktion der abgeleiteten Klasse die Funktion der Basisklasse nicht überschreibt. Markieren Sie die Funktion der abgeleiteten Klasse als explizit `new` auf diese Warnung zu beheben.

Weitere Informationen finden Sie unter [new (neuer Slot in Vtable)](../../windows/new-new-slot-in-vtable-cpp-component-extensions.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4487 generiert.

```
// C4487.cpp
// compile with: /W4 /clr
using namespace System;
public ref struct B {
   void f() { Console::WriteLine("in B::f"); }
   void g() { Console::WriteLine("in B::g"); }
};

public ref struct D : B {
   void f() { Console::WriteLine("in D::f"); }   // C4487
   void g() new { Console::WriteLine("in D::g"); }   // OK
};

int main() {
   B ^ a = gcnew D;
   // will call base class functions
   a->f();
   a->g();
}
```