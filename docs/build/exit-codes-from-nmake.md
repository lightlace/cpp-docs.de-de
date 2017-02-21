---
title: "Exitcodes von NMAKE | Microsoft Docs"
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
  - "Exit-Codes"
  - "NMAKE (Programm), Exit-Codes"
ms.assetid: 75f6913c-1da5-4572-a2d3-8a4e058bed15
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
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