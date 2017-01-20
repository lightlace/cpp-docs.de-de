---
title: "ASSUME"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "ASSUME"
  - "_assume_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ASSUME directive"
ms.assetid: cd162070-aee9-4c65-babc-005c6cc73d7c
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# ASSUME
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Aktiviert die Fehlerprüfung für Registerwerte.  
  
## Syntax  
  
```  
  
      ASSUME segregister:name [[, segregister:name]]...  
ASSUME dataregister:type [[, dataregister:type]]...  
ASSUME register:ERROR [[, register:ERROR]]...  
ASSUME [[register:]] NOTHING [[, register:NOTHING]]...  
```  
  
## Hinweise  
 Nachdem `ASSUME` bewerkstelligt wird die Assembler überwachung für Änderungen an den Werten der angegebenen Register.  **FEHLER** generiert einen Fehler, wenn das Register verwendet wird.  **NICHTS** entfernt fehlerüberprüfung registrieren.  Sie können verschiedene Arten von Annahmen in einer Anweisung kombiniert werden.  
  
## Siehe auch  
 [Directives Reference](../../assembler/masm/directives-reference.md)