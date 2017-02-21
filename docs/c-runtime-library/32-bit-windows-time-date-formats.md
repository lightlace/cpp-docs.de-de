---
title: "32-Bit-Windows-Uhrzeit-/Datumsformate | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.time"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "32-Bit Windows"
ms.assetid: ef1589db-84d7-4b24-8799-7c7a22cfe2bf
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 32-Bit-Windows-Uhrzeit-/Datumsformate
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Dateizeit und Datum wird einzeln, mit ganzen Zahlen als vorzeichenlose Bitfelder gespeichert.  Dateizeit und \-Datum wird verpackt, wie folgt:  
  
### Uhrzeit  
  
|Bitposition:|0   1   2   3   4|5 6 7 8 9 A|B C D EF|  
|------------------|-----------------------|-----------------|--------------|  
|Länge:|5|6|5|  
|Inhalt:|hours|minutes|2\-Sekunden\- Inkremente|  
|Wert\-Bereich:|0–23|0–59|0\-29 in Intervallen von 2|  
  
### Datum  
  
|Bitposition:|0   1   2   3   4   5   6|7 8 9 A|B C D EF|  
|------------------|-------------------------------|-------------|--------------|  
|Länge:|7|4|5|  
|Inhalt:|Jahr|Monat|Tag|  
|Wert\-Bereich:|0–119|1–12|1–31|  
||\(relativ zu 1980\)|||  
  
## Siehe auch  
 [Globale Konstanten](../c-runtime-library/global-constants.md)