---
title: "Übersicht über C-Anweisungen| Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- semicolon, in C statements
- statements, C
- semicolon
- statements, about statements
- Visual C, statements
ms.assetid: 0d49837a-5399-4881-b60c-af5f4e9720de
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 040cc7a1718975285088fb0d1a7474cc72a5c4d8
ms.contentlocale: de-de
ms.lasthandoff: 05/18/2017

---
# <a name="overview-of-c-statements"></a>Übersicht über C-Anweisungen
C-Anweisungen bestehen aus Token, Ausdrücken und anderen Anweisungen. Eine Anweisung, die eine Komponente einer andere Anweisung bildet, wird als "Text" der einschließenden Anweisung bezeichnet. Jeder Anweisungstyp, der von der folgenden Syntax angegeben wird, wird in diesem Abschnitt erläutert.  
  
## <a name="syntax"></a>Syntax  
 *Anweisung*:  
 [labeled-statement](../c-language/goto-and-labeled-statements-c.md)  
  
 [compound-statement](../c-language/compound-statement-c.md)  
  
 [expression-statement](../c-language/expression-statement-c.md)  
  
 [selection-statement](../c-language/if-statement-c.md)  
  
 [iteration-statement](../c-language/do-while-statement-c.md)  
  
 [jump-statement](../c-language/break-statement-c.md)  
  
 [try-except-statement](../c-language/try-except-statement-c.md)  
  
 /* Microsoft-spezifisch \*/[try-finally-statement](../c-language/try-finally-statement-c.md) /\* Microsoft-spezifisch\*/  
  
 Häufig handelt es sich bei einem Anweisungstext um eine "Verbundanweisung ". Eine Verbundanweisung besteht aus anderen Anweisungen, die Schlüsselwörter enthalten können. Die Verbundanweisung steht in geschweiften Klammern (**{ }**). Alle anderen C-Anweisungen enden mit einem Semikolon (**;**). Das Semikolon ist ein Anweisungsabschlusszeichen.  
  
 Die Ausdrucksanweisung enthält einen C-Ausdruck, der die arithmetischen oder logischen Operatoren, die in [Ausdrücke und Zuweisungen](../c-language/expressions-and-assignments.md) eingeführt werden, enthalten kann. Die Null-Anweisung ist eine leere Anweisung.  
  
 Jede C-Anweisung kann mit einer identifizierende Bezeichnung, die aus einem Namen und einem Doppelpunkt besteht, beginnen. Da nur die `goto`-Anweisung Anweisungsmarken erkennt, werden Anweisungsmarken mit `goto` erläutert. Weitere Informationen finden Sie unter [The goto and Labeled Statements](../c-language/goto-and-labeled-statements-c.md) (Die goto- und Labeled-Anweisung).  
  
## <a name="see-also"></a>Siehe auch  
 [Anweisungen](../c-language/statements-c.md)
