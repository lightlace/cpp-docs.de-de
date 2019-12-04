---
title: Compilerfehler C2535
ms.date: 11/04/2016
f1_keywords:
- C2535
helpviewer_keywords:
- C2535
ms.assetid: a958f83e-e2bf-4a59-b44b-d406ec325d7e
ms.openlocfilehash: f5cecd847837214f6392bead624e5377cef4833f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758644"
---
# <a name="compiler-error-c2535"></a>Compilerfehler C2535

'Bezeichner' : Memberfunktion bereits definiert oder deklariert

Dieser Fehler kann auftreten, wenn dieselbe Liste formaler Parameter in mehr als einer Funktionsdefinition oder -deklaration einer überladenen Funktion verwendet wird.

Wenn Sie C2535 aufgrund der Funktion "verwerfen" erhalten, finden Sie weitere Informationen unter [debugtoren und Finalizer](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers) .

Im folgenden Beispiel wird C2535 generiert:

```cpp
// C2535.cpp
// compile with: /c
class C {
public:
   void func();   // forward declaration
   void func() {}   // C2535
};
```
