---
title: Compilerwarnung (Stufe 4) C4516 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4516
dev_langs:
- C++
helpviewer_keywords:
- C4516
ms.assetid: 6677bb1f-d26e-4ab9-8644-6b5a2a8f4ff8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 88bb2232c635a89650be892a27e490a42d7197ca
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46045619"
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