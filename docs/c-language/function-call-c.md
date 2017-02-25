---
title: "Funktionsaufruf (C) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Funktionsaufrufe"
  - "Funktionsaufrufe, C-Funktionen"
  - "Funktionen [C], Aufrufen"
ms.assetid: 35c66719-3f15-4d3b-97da-4e19dc97b308
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Funktionsaufruf (C)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein "Funktionsaufruf" ist ein Ausdruck, der den Namen der aufgerufenen Funktion oder den Wert eines Funktionszeigers und optional die Argumente, die der Funktion übergeben werden, enthält.  
  
## Syntax  
 *postfix\-expression*:  
 *postfix\-expression*  **\(**  *argument\-expression\-list*  opt **\)**  
  
 *argument\-expression\-list*:  
 *assignment\-expression*  
  
 *argument\-expression\-list*  **,**  *assignment\-expression*  
  
 Der *Postfixausdruck* muss eine Funktionsadresse ergeben \(z. B. einen Funktionsbezeichner oder Funktionszeigerwert\), und die *Argumentausdrucksliste* ist eine Ausdrucksliste \(durch Kommas getrennt\), deren Werte \(die "Argumente"\) an die Funktion übergeben werden.  Das *argument\-expression\-list*\-Argument kann leer sein.  
  
 Ein Funktionsaufrufausdruck hat den Wert und Typ des Rückgabewerts der Funktion.  Eine Funktion kann kein Objekt des Arraytyps zurückgeben.  Wenn der Rückgabetyp der Funktion `void` ist \(die Funktion also so deklariert wurde, dass sie niemals einen Wert zurückgibt\), hat der Funktionsaufrufausdruck ebenfalls den Typ `void`. Weitere Informationen finden Sie unter [Funktionsaufrufe](../c-language/function-calls.md).  
  
## Siehe auch  
 [Funktionsaufrufoperator: \(\)](../cpp/function-call-operator-parens.md)