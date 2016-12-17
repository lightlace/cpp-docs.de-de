---
title: "Exitcodes von NMAKE"
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
helpviewer_keywords: 
  - "Exit-Codes"
  - "NMAKE (Programm), Exit-Codes"
ms.assetid: 75f6913c-1da5-4572-a2d3-8a4e058bed15
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Exitcodes von NMAKE
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Folgende Exitcodes werden von NMAKE zurückgegeben:  
  
|Code|Bedeutung|  
|----------|---------------|  
|0|Kein Fehler \(möglicherweise eine Warnung\)|  
|1|Unvollständiges Build \(wird nur bei der \/K\-Option ausgegeben\)|  
|2|Programmfehler, mögliche Ursachen:|  
||-   Ein Syntaxfehler im Makefile|  
||-   Ein Fehler oder Exitcode eines Befehls|  
||-   Eine Unterbrechung durch den Benutzer|  
|4|Systemfehler – Nicht genügend Arbeitsspeicher|  
|255|Ziel ist nicht aktuell \(wird nur bei der \/Q\-Option ausgegeben\)|  
  
## Siehe auch  
 [Ausführen von NMAKE](../build/running-nmake.md)