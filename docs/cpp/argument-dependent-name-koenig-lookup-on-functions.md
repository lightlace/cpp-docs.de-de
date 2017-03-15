---
title: "Argumentbezogene Namenssuche (Koenig) in Funktionen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Argumentbezogenes Lookup [C++]"
  - "Koenig-Suche"
ms.assetid: c0928401-da2c-4658-942d-9ba4df149c35
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Argumentbezogene Namenssuche (Koenig) in Funktionen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der Compiler kann eine argumentbezogene Namenssuche verwenden, um die Definition eines nicht qualifizierten Funktionsaufrufs zu suchen.  Die argumentbezogene Namenssuche wird auch Koenig\-Suche genannt.  Der Typ jedes Arguments in einem Funktionsaufruf wird innerhalb einer Hierarchie von Namespaces, Klassen, Strukturen, Unions oder Vorlagen definiert.  Wenn Sie einen nicht qualifizierten [postfix](../cpp/postfix-expressions.md)\-Funktionsaufruf angeben, wird vom Compiler nach der Funktionsdefinition in der Hierarchie gesucht, die mit jedem Argumenttyp verknüpft ist.  
  
## Beispiel  
 Im Beispiel stellt der Compiler fest, dass Funktion `f()` ein Argument `x` akzeptiert.  Argument `x` ist vom Typ `A::X`, der im Namespace `A` definiert ist.  Der Compiler durchsucht Namespace `A` und findet eine Definition für die `f()`\-Funktion, die ein Argument des Typs `A::X` akzeptiert.  
  
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
  
## Siehe auch  
 [Visual C\+\+. NET 2003 erweiterte Compilerkonformität](../misc/visual-cpp-dotnet-2003-enhanced-compiler-conformance.md)