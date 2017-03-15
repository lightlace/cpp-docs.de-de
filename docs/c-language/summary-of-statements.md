---
title: "Zusammenfassung der Anweisungen | Microsoft Docs"
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
ms.assetid: ce45d2fe-ec0e-459f-afb1-80ab6a7f0239
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Zusammenfassung der Anweisungen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

*statement*:  
 *labeled\-statement*  
  
 *compound\-statement*  
  
 *expression\-statement*  
  
 *selection\-statement*  
  
 *iteration\-statement*  
  
 *jump\-statement*  
  
 *try\-except\-Anweisung* \/\* Microsoft\-spezifisch \*\/  
  
 *try\-finally\-Anweisung* \/\* Microsoft\-spezifisch \*\/  
  
 *Sprunganweisung*:  
 **goto**  *identifier*  **;**  
  
 **continue ;**  
  
 **break ;**  
  
 **return**  *expression* opt **;**  
  
 *compound\-statement*:  
 **{**  *declaration\-list* opt *statement\-list* opt **}**  
  
 *declaration\-list*:  
 *declaration*  
  
 *declaration\-list\-Deklaration*  
  
 *statement\-list*:  
 *Anweisung*  
  
 *statement\-list\-Anweisung*  
  
 *expression\-statement*:  
 *expression* opt **;**  
  
 *iteration\-statement*:  
 **while \(**  *expression*  **\)**  *statement*  
  
 **do**  *statement*  **while \(**  *expression*  **\) ;**  
  
 **for \(**  *expression* opt **;** *expression* opt **;** *expression* opt **\)** *statement*  
  
 *selection\-statement*:  
 **if \(**  *expression*  **\)**  *statement*  
  
 **if \(**  *expression*  **\)**  *statement*  **else**  *statement*  
  
 **switch \(**  *expression*  **\)**  *statement*  
  
 *labeled\-statement*:  
 *identifier*  **:**  *statement*  
  
 **case**  *constant\-expression*  **:**  *statement*  
  
 **default :**  *statement*  
  
 *try\-except\-Anweisung*:   \/\* Microsoft\-spezifisch \*\/  
 **\_\_try**  *compound\-statement*  
  
 **\_\_except \(**  *expression*  **\)**  *compound\-statement*  
  
 *try\-finally\-Anweisung*:   \/\* Microsoft\-spezifisch \*\/  
 **\_\_try**  *compound\-statement*  
  
 **\_\_finally**  *compound\-statement*  
  
## Siehe auch  
 [Phrasenstrukturgrammatik](../c-language/phrase-structure-grammar.md)