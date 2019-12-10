---
title: Compilerwarnung (Stufe 4) C4623
ms.date: 11/04/2016
f1_keywords:
- C4623
helpviewer_keywords:
- C4623
ms.assetid: e630d8d0-f6ea-469c-a74f-07b027587225
ms.openlocfilehash: 4d0dd9aec19fb21870a1233cd3b713337fa15aaa
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74990630"
---
# <a name="compiler-warning-level-4-c4623"></a>Compilerwarnung (Stufe 4) C4623

'`derived class`': Der Standardkonstruktor wurde implizit als gelöscht definiert, da ein Basisklassen-Standardkonstruktor nicht zugreifbar ist oder gelöscht wurde.

Auf einen Konstruktor konnte nicht in einer Basisklasse zugegriffen werden und ein Konstruktor wurde nicht für die abgeleitete Klasse generiert. Jeder Versuch, ein Objekt dieses Typs auf dem Stapel zu erstellen, verursacht einen Compilerfehler.

Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4623 generiert.

```cpp
// C4623.cpp
// compile with: /W4
#pragma warning(default : 4623)
class B {
   B();
};

class C {
public:
   C();
};

class D : public B {};   // C4623 - to fix, make B's constructor public
class E : public C {};   // OK - class C constructor is public

int main() {
   // D d;  will cause an error
}
```
