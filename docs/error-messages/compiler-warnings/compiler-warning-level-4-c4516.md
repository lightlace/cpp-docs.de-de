---
title: Compilerwarnung (Stufe 4) C4516
ms.date: 11/04/2016
f1_keywords:
- C4516
helpviewer_keywords:
- C4516
ms.assetid: 6677bb1f-d26e-4ab9-8644-6b5a2a8f4ff8
ms.openlocfilehash: 8020103e8e20bf1a5e955cbfdfafc6a328b439e6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62221032"
---
# <a name="compiler-warning-level-4-c4516"></a>Compilerwarnung (Stufe 4) C4516

"Zugriffsdeklarationen": Zugriffsdeklarationen sind veraltet. using-Deklarationen stellen eine bessere Alternative dar

Das ANSI C++ Committee hat Zugriffsdeklarationen (Ändern der Zugriffsebene eines Members in einer abgeleiteten Klasse, ohne die [mit](../../cpp/using-declaration.md) Schlüsselwort) veraltet sein. Access-Deklarationen können in künftigen Versionen von C++ nicht unterstützt.

Im folgende Beispiel wird die C4516 generiert:

```
// C4516.cpp
// compile with: /W4
class A
{
public:
   void x(char);
};

class B : protected A
{
public:
   A::x;  // C4516 on access-declaration
   // use the following line instead
   // using A::x; // using-declaration, ok
};

int main()
{
}
```