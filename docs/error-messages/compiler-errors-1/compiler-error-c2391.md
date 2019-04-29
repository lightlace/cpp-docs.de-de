---
title: Compilerfehler C2391
ms.date: 11/04/2016
f1_keywords:
- C2391
helpviewer_keywords:
- C2391
ms.assetid: 63a9c6b9-03cc-4517-885c-bdcd048643b3
ms.openlocfilehash: 7683ad1580454bd7edb1fc08e5bd110a3e5c36c4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62393622"
---
# <a name="compiler-error-c2391"></a>Compilerfehler C2391

'Bezeichner': 'Friend' kann nicht verwendet werden, während der Typdefinition

Die `friend` Deklaration enthält eine vollständige Klassendeklaration. Ein `friend` Deklaration kann eine Memberfunktion oder ein ausgearbeiteter Typspezifizierer, aber keine vollständige Klassendeklaration angeben.

Im folgenden Beispiel wird C2326 generiert:

```
// C2391.cpp
// compile with: /c
class D {
   void func( int );
};

class A {
   friend class B { int i; };   // C2391

   // OK
   friend class C;
   friend void D::func(int);
};
```