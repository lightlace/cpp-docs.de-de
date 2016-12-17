---
title: "&#220;bersicht &#252;ber C-Anweisungen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Semikolon"
  - "Semikolon, In C-Anweisungen"
  - "Anweisungen, Informationen über Anweisungen"
  - "Anweisungen, C"
  - "Visual C, Anweisungen"
ms.assetid: 0d49837a-5399-4881-b60c-af5f4e9720de
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# &#220;bersicht &#252;ber C-Anweisungen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C\-Anweisungen bestehen aus Token, Ausdrücken und anderen Anweisungen.  Eine Anweisung, die eine Komponente einer andere Anweisung bildet, wird als "Text" der einschließenden Anweisung bezeichnet.  Jeder Anweisungstyp, der von der folgenden Syntax angegeben wird, wird in diesem Abschnitt erläutert.  
  
## Syntax  
 *statement*:  
 [labeled\-statement](../c-language/goto-and-labeled-statements-c.md)  
  
 [compound\-statement](../c-language/compound-statement-c.md)  
  
 [expression\-statement](../c-language/expression-statement-c.md)  
  
 [selection\-statement](../c-language/if-statement-c.md)  
  
 [iteration\-statement](../c-language/do-while-statement-c.md)  
  
 [jump\-statement](../c-language/break-statement-c.md)  
  
 [try\-except\-statement](../c-language/try-except-statement-c.md)  
  
 \/\* Microsoft\-spezifisch \*\/[try\-finally\-statement](../c-language/try-finally-statement-c.md) \/\* Microsoft\-spezifisch \*\/  
  
 Häufig handelt es sich bei einem Anweisungstext um eine "Verbundanweisung ". Eine Verbundanweisung besteht aus anderen Anweisungen, die Schlüsselwörter enthalten können.  Die Verbundanweisung steht in geschweiften Klammern \(**{ }**\).  Alle anderen C\-Anweisungen enden mit einem Semikolon \(**;**\).  Das Semikolon ist ein Anweisungsabschlusszeichen.  
  
 Die Ausdrucksanweisung enthält einen C\-Ausdruck, der die arithmetischen oder logischen Operatoren, die in [Ausdrücke und Zuweisungen](../c-language/expressions-and-assignments.md) eingeführt werden, enthalten kann.  Die Null\-Anweisung ist eine leere Anweisung.  
  
 Jede C\-Anweisung kann mit einer identifizierende Bezeichnung, die aus einem Namen und einem Doppelpunkt besteht, beginnen.  Da nur die `goto`\-Anweisung Anweisungsmarken erkennt, werden Anweisungsmarken mit `goto` erläutert.  Weitere Informationen finden Sie unter [goto\-Anweisungen und Anweisungen mit Bezeichnung](../c-language/goto-and-labeled-statements-c.md).  
  
## Siehe auch  
 [Anweisungen](../c-language/statements-c.md)