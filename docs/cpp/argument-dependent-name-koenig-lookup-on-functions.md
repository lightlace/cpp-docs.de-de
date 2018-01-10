---
title: "Argumentbezogene Namenssuche (Koenig) Lookup für Funktionen | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- Koenig lookup
- argument-dependent lookup [C++]
ms.assetid: c0928401-da2c-4658-942d-9ba4df149c35
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5a468d5eef9a400bfa5e12c90ca62e05ea2f160d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="argument-dependent-name-koenig-lookup-on-functions"></a>Argumentbezogene Namenssuche (Koenig) in Funktionen
Der Compiler kann eine argumentbezogene Namenssuche verwenden, um die Definition eines nicht qualifizierten Funktionsaufrufs zu suchen. Die argumentbezogene Namenssuche wird auch Koenig-Suche genannt. Der Typ jedes Arguments in einem Funktionsaufruf wird innerhalb einer Hierarchie von Namespaces, Klassen, Strukturen, Unions oder Vorlagen definiert. Wenn Sie einen nicht qualifizierten angeben [postfix](../cpp/postfix-expressions.md) Funktionsaufruf, der Compiler durchsucht, für die Funktionsdefinition in der Hierarchie, die mit jedem Argumenttyp verknüpft ist.  
  
## <a name="example"></a>Beispiel  
 Im Beispiel stellt der Compiler fest, dass Funktion `f()` ein Argument `x` akzeptiert. Argument `x` ist vom Typ `A::X`, der im Namespace `A` definiert ist. Der Compiler durchsucht Namespace `A` und findet eine Definition für die `f()`-Funktion, die ein Argument des Typs `A::X` akzeptiert.  
  
```  
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
