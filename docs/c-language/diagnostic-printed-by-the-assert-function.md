---
title: "Diagnose von der Assert-Funktion gedruckt"
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
ms.assetid: 78b64200-520d-40da-9a61-71553f411d4f
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Diagnose von der Assert-Funktion gedruckt
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 4.2** Die von der **assert**\-Funktion gedruckte Diagnose und das Abbruchverhalten dieser Funktion  
  
 Die **assert**\-Funktion druckt eine Diagnosemeldung und ruft die **abort**\-Routine auf, wenn der Ausdruck "false" \(0\) ist.  Die Diagnosemeldung hat die Form  
  
 **Assertionsfehler**: *Ausdruck***, Datei** *Dateiname***, Zeile** *Zeilennummer*  
  
 wobei der "Dateiname" der Name der Quelldatei und "Zeilennummer" die Zeilennummer der Assertion ist, die in der Quelldatei einen Fehler aufweist.  Es werden keine Aktionen ausgeführt, wenn der Ausdruck "true" ist \(nicht Null\).  
  
## Siehe auch  
 [Bibliotheksfunktionen](../c-language/library-functions.md)