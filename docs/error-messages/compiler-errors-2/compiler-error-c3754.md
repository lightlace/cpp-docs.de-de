---
title: Compilerfehler C3754
ms.date: 11/04/2016
f1_keywords:
- C3754
helpviewer_keywords:
- C3754
ms.assetid: 14b877bc-9277-40ec-af1c-196a58b45f10
ms.openlocfilehash: e03ac39213429fbbb9f289be3514718985c04b4b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50582116"
---
# <a name="compiler-error-c3754"></a>Compilerfehler C3754

Delegatkonstruktor: Member-Funktion 'Funktion' kann nicht in einer Instanz von Typ 'Typ' aufgerufen werden

Eine Funktion über einen Zeiger auf einen Typ wurde aufgerufen, die die Funktion nicht enthält.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3754 generiert:

```
// C3754a.cpp
// compile with: /clr
using namespace System;

delegate void MyDel();

interface class MyInterface {};

ref struct MyClass : MyInterface {
   void f() {}
};

int main() {
   MyInterface^ p = gcnew MyClass;
   MyDel^ q = gcnew MyDel(p, &MyClass::f);   // C3754
   // try the following line instead
//   MyDel^ q = gcnew MyDel(safe_cast<MyClass^>(p), &MyClass::f);
}
```
