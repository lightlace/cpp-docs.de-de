---
title: Compilerwarnung (Stufe 3) C4243 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4243
dev_langs:
- C++
helpviewer_keywords:
- C4243
ms.assetid: ca72f9ad-ce0b-43a9-a68c-106e1f8b90ef
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b407939b58d1025698f7c3d82bbe1921b33f90a5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46025684"
---
# <a name="compiler-warning-level-3-c4243"></a>Compilerwarnung (Stufe 3) C4243

'Konvertierungstyp'-Konvertierung von 'type1' in 'Typ2' vorhanden, aber es ist nicht möglich.

Ein Zeiger auf eine abgeleitete Klasse in einen Zeiger auf eine Basisklasse konvertiert wird, aber die abgeleitete Klasse erbt von der Basisklasse mit privaten oder geschützten Zugriff.

Im folgende Beispiel wird die C4243 generiert:

```
// C4243.cpp
// compile with: /W3
// C4243 expected
struct B {
   int f() {
      return 0;
   };
};

struct D : private B {};
struct E : public B {};

int main() {
   // Delete the following 2 lines to resolve.
   int (D::* d)() = (int(D::*)()) &B::f;
   d;

   int (E::* e)() = (int(E::*)()) &B::f; // OK
   e;
}
```