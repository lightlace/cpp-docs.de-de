---
title: Argumentbezogene Namenssuche (Koenig)-Lookup für Funktionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- Koenig lookup
- argument-dependent lookup [C++]
ms.assetid: c0928401-da2c-4658-942d-9ba4df149c35
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8e71a1fd5a795fb95520ec8d7859e70460a9372c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46028817"
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