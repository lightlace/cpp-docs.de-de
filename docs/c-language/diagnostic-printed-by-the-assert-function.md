---
title: "Diagnose von der Assert-Funktion gedruckt | Microsoft Docs"
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
ms.assetid: 78b64200-520d-40da-9a61-71553f411d4f
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Diagnose von der Assert-Funktion gedruckt
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 4.2** Die von der **assert**\-Funktion gedruckte Diagnose und das Abbruchverhalten dieser Funktion  
  
 Die **assert**\-Funktion druckt eine Diagnosemeldung und ruft die **abort**\-Routine auf, wenn der Ausdruck "false" \(0\) ist.  Die Diagnosemeldung hat die Form  
  
 **Assertionsfehler**: *Ausdruck***, Datei** *Dateiname***, Zeile** *Zeilennummer*  
  
 wobei der "Dateiname" der Name der Quelldatei und "Zeilennummer" die Zeilennummer der Assertion ist, die in der Quelldatei einen Fehler aufweist.  Es werden keine Aktionen ausgeführt, wenn der Ausdruck "true" ist \(nicht Null\).  
  
## Siehe auch  
 [Bibliotheksfunktionen](../c-language/library-functions.md)