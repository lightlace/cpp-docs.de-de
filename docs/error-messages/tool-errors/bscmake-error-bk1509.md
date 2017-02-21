---
title: "BSCMAKE-Fehler BK1509 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "BK1509"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BK1509"
ms.assetid: 53df7037-1913-4b63-b425-c0bf44081792
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# BSCMAKE-Fehler BK1509
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Kein weiterer Heap\-Speicher verfügbar  
  
 BSCMAKE stand nicht genügend Arbeitsspeicher zur Verfügung, einschließlich des virtuellen Speichers.  
  
### Beachten Sie die folgenden Vorschläge zur Problembehebung:  
  
1.  Geben Sie einigen Festplattenspeicher frei.  
  
2.  Vergrößern Sie die Auslagerungsdatei.  
  
3.  Vergrößern Sie die Windows\-Auslagerungsdatei.  
  
4.  Reduzieren Sie den für BSCMAKE erforderlichen Speicher durch Verwenden von **\/Ei** oder **\/Es**, um einige Eingabedateien zu beseitigen, oder **\/Em**, um Makrotext zu beseitigen.