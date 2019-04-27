---
title: Argumentbezogene Namenssuche (Koenig) in Funktionen
ms.date: 11/04/2016
helpviewer_keywords:
- Koenig lookup
- argument-dependent lookup [C++]
ms.assetid: c0928401-da2c-4658-942d-9ba4df149c35
ms.openlocfilehash: d979b79c0f712ed35a42a44047dd1091010c72bf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62184469"
---
# <a name="argument-dependent-name-koenig-lookup-on-functions"></a>Argumentbezogene Namenssuche (Koenig) in Funktionen

Der Compiler kann eine argumentbezogene Namenssuche verwenden, um die Definition eines nicht qualifizierten Funktionsaufrufs zu suchen. Die argumentbezogene Namenssuche wird auch Koenig-Suche genannt. Der Typ jedes Arguments in einem Funktionsaufruf wird innerhalb einer Hierarchie von Namespaces, Klassen, Strukturen, Unions oder Vorlagen definiert. Wenn Sie einen nicht qualifizierten angeben [postfix](../cpp/postfix-expressions.md) Funktionsaufruf, der Compiler sucht die Definition der Funktion in der Hierarchie, die mit jedem Argumenttyp verknüpft ist.

## <a name="example"></a>Beispiel

Im Beispiel stellt der Compiler fest, dass Funktion `f()` ein Argument `x` akzeptiert. Argument `x` ist vom Typ `A::X`, der im Namespace `A` definiert ist. Der Compiler durchsucht Namespace `A` und findet eine Definition für die `f()`-Funktion, die ein Argument des Typs `A::X` akzeptiert.

```cpp
// argument_dependent_name_koenig_lookup_on_functions.cpp
namespace A
{
   struct X
   {
   };
   void f(const X&)
   {
   }
}
int main()
{
// The compiler finds A::f() in namespace A, which is where
// the type of argument x is defined. The type of x is A::X.
   A::X x;
   f(x);
}
```