---
title: 'Wert Kategorien: Lvalues und Rvalues (Visual C++) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- R-values [C++]
- L-values [C++]
ms.assetid: a8843344-cccc-40be-b701-b71f7b5cdcaf
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e06dca827d6b5cb5d457a2eda6aa143bb5d0fe5e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="lvalues-and-rvalues-visual-c"></a>Lvalues und Rvalues (Visual C++)
Jeder C++-Ausdruck weist einen Typ auf und gehört zu einem *Wert Kategorie*. Der Wert Kategorien sind die Grundlage für Regeln, die Compiler befolgen müssen, wenn erstellen, kopieren und Verschieben von temporären Objekten während der Auswertung von Ausdrücken. 

 Die C ++ 17-standard definiert Ausdruck Wert Kategorien wie folgt aus:

- Ein *Glvalue* ist ein Ausdruck, dessen Auswertung die Identität des Objekts, eines Bitfeld oder einer Funktion bestimmt. 
- Ein *Prvalue* ist ein Ausdruck, dessen Auswertung Initialisiert ein Objekt oder ein Bitfeld, oder den Wert des Operanden eines Operators berechnet, wie vom Kontext angegeben, in dem sie erscheint. 
- Ein *Xvalue* einen Glvalue, die ein Objekt oder ein Bitfeld, deren Ressourcen wiederverwendet werden können, (in der Regel, da er befindet sich am Ende ihrer Lebensdauer) bezeichnet wird. [Beispiel: bestimmte Arten von Ausdrücken, die im Zusammenhang mit Rvalue-Verweise (8.3.2) ergeben Xvalues, z. B. einen Aufruf an eine Funktion, deren Rückgabetyp ein Rvalue-Verweis ist, oder eine Umwandlung in einen Rvalue-Verweistyp. ] 
- Ein *Lvalue* ist eine Glvalue, die keine Xvalue ist. 
- Ein *Rvalue* ist eine Prvalue oder ein Xvalue. 

Das folgende Diagramm veranschaulicht die Beziehungen zwischen den Kategorien:

 ![C++-Ausdruck Wert Kategorien](media/value_categories.png "C++ Ausdruck Wert Kategorien")  
 
 Ein Lvalue verfügt über eine Adresse, die Ihre Anwendung zugreifen kann. Beispiele für Lvalue-Ausdrücke sind Namen von Variable, einschließlich `const` Variablen, Arrayelemente, Funktionsaufrufe, die einen Lvalue-Verweis, Bitfelder Unions und Klassenmember zurückgeben. 
 
 Ein Prvalue Ausdruck hat keine Adresse, die von Ihrer Anwendung zugegriffen werden kann. Beispiele für Ausdrücke Prvalue sind Literale, Funktionsaufrufe, die einen Verweistyp zurückzugeben und temporäre Objekte, die während der Evaluierung von Ausdruck jedoch zugegriffen werden kann nur vom Compiler erstellt werden. 

 Ein Ausdruck Xvalue besitzt keine Adresse aber kann verwendet werden, um einen Rvalue-Verweis zu initialisieren, der Zugriff auf den Ausdruck enthält. Beispiele für sind Funktionsaufrufe, die einen Rvalue-Verweis, und die Arrayfeldindex, Member und Zeiger auf Member-Ausdrücke zurückgeben, in dem das Array oder Objekt einen Rvalue-Verweis ist. 
 
 Das folgende Beispiel zeigt mehrere korrekte und falsche Verwendungen von lvalues und rvalues:  
  
```  
// lvalues_and_rvalues2.cpp  
int main()  
{  
   int i, j, *p;  
  
   // Correct usage: the variable i is an lvalue and the literal 7 is a prvalue.  
   i = 7;  
  
   // Incorrect usage: The left operand must be an lvalue (C2106).  `j * 4` is a prvalue.
   7 = i; // C2106  
   j * 4 = 7; // C2106  
  
   // Correct usage: the dereferenced pointer is an lvalue.  
   *p = i;   
  
   const int ci = 7;  
   // Incorrect usage: the variable is a non-modifiable lvalue (C3892).  
   ci = 9; // C3892  
  
   // Correct usage: the conditional operator returns an lvalue.  
   ((i < 3) ? i : j) = 7;  
}  
```  
  
> [!NOTE]
>  Die Beispiele zu diesem Thema veranschaulichen die korrekte und falsche Verwendung, wenn Operatoren nicht überladen werden. Indem Sie Operatoren überladen, können Sie aus einem Ausdruck wie `j * 4` einen lvalue machen.  

  
 Die Begriffe *Lvalue* und *Rvalue* werden häufig verwendet werden, wenn Sie in auf Objektverweise Bezug. Weitere Informationen zu verweisen finden Sie unter [Lvalue-Verweisdeklarator: &](../cpp/lvalue-reference-declarator-amp.md) und [Rvalue-Verweisdeklarator: & &](../cpp/rvalue-reference-declarator-amp-amp.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Grundlegende Konzepte](../cpp/basic-concepts-cpp.md)   
 [Lvalue-Verweisdeklarator: &](../cpp/lvalue-reference-declarator-amp.md)   
 [Rvalue-Verweisdeklarator: &&](../cpp/rvalue-reference-declarator-amp-amp.md)