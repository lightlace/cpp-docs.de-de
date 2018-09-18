---
title: Compilerfehler C2027 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2027
dev_langs:
- C++
helpviewer_keywords:
- C2027
ms.assetid: a39150c0-ec04-45ec-934c-a838bfe76627
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 69aae289fbab56cd77e544118909b2d7ef72ae0c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46032041"
---
# <a name="compiler-error-c2027"></a>Compilerfehler C2027

Verwendung von undefiniertem Typ 'Typ'

Ein Typ kann nicht verwendet werden, bevor sie definiert ist. Um den Fehler zu beheben, achten Sie darauf, dass der Typ vollständig definiert ist, bevor auf Sie verwiesen wird.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C2027 generiert.

```
// C2027.cpp
class C;
class D {
public:
   void func() {
   }
};

int main() {
   C *pC;
   pC->func();   // C2027

   D *pD;
   pD->func();
}
```

## <a name="example"></a>Beispiel

Es ist möglich, einen Zeiger auf einen Typ deklariert, aber nicht definierte zu deklarieren.  Visual C++, nicht jedoch einen Verweis auf einen nicht definierten Typ.

Im folgende Beispiel wird die C2027 generiert.

```
// C2027_b.cpp
class A;
A& CreateA();

class B;
B* CreateB();

int main() {
   CreateA();   // C2027
   CreateB();   // OK
}
```