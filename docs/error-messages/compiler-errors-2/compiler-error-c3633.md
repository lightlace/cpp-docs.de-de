---
title: Compilerfehler C3633
ms.date: 11/04/2016
f1_keywords:
- C3633
helpviewer_keywords:
- C3633
ms.assetid: 7d65babf-2191-4d67-a69f-f5c4c2ddf946
ms.openlocfilehash: 2d96a0e4f5f0b34c76f41058316c7f158f1a939d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385705"
---
# <a name="compiler-error-c3633"></a>Compilerfehler C3633

'Member' kann nicht als Member des verwalteten 'Typs' definiert werden.

CLR-Referenz-Klassendatenmember darf nicht von einem nicht - POD-C++-Typ sein.  Sie können nur einen systemeigenen POD-Typ in einen CLR-Typ instanziieren.  Beispielsweise kann kein POD-Typ einen Kopierkonstruktor oder Zuweisungsoperator enthalten.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3633 generiert.

```
// C3633.cpp
// compile with: /clr /c
#pragma warning( disable : 4368 )

class A1 {
public:
   A1() { II = 0; }
   int II;
};

ref class B {
public:
   A1 a1;   // C3633
   A1 * a2;   // OK
   B() : a2( new A1 ) {}
    ~B() { delete a2; }
};
```
