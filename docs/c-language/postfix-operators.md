---
title: "Postfixoperatoren | Microsoft Docs"
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
  - "Operatoren [C], Postfix"
  - "Postfixoperatoren"
ms.assetid: 76260011-1624-484e-8bef-72ae7ab556cc
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Postfixoperatoren
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Postfix\-Operatoren weisen den höchsten Rang \(die festeste Bindung\) in der Ausdrucksauswertung auf.  
  
## Syntax  
 *postfix\-expression*:  
 *primary\-expression*  
  
 *postfix\-expression*  **\[**  *expression*  **\]**  
  
 *postfix\-expression*  **\(**  *argument\-expression\-list*  opt **\)**  
  
 *postfix\-expression*  **.**  *identifier*  
  
 *postfix\-expression*  **–\>**  *identifier*  
  
 *postfix\-expression*  **\+\+**  
  
 *postfix\-expression*  **––**  
  
 Operatoren in dieser Rangfolgenebene sind die Arrayfeldindizes, Funktionsaufrufe, die Struktur\- und Union\-Member sowie Postfix\-Operatoren für Inkrement und Dekrement.  
  
## Siehe auch  
 [C\-Operatoren](../c-language/c-operators.md)