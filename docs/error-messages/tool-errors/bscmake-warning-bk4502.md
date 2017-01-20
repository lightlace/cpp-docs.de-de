---
title: "BSCMAKE-Warnung BK4502"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "BK4502"
  - "BK1513"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BK1513"
  - "BK4502"
ms.assetid: ee412ec8-df03-4cdb-91ee-5d609ded8691
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# BSCMAKE-Warnung BK4502
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Abgeschnittene SBR\-Datei "Dateiname" nicht in Dateiname  
  
 Eine SBR\-Datei mit Länge 0 \(null\), die nicht ursprünglich Teil einer BSC\-Datei war, wurde in einem Update angegeben.  
  
### Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Falscher Dateiname angegeben.  
  
2.  Datei gelöscht. \(Dies führt zum Fehler [BK1513](../../error-messages/tool-errors/bscmake-error-bk1513.md).\)  
  
3.  Datei beschädigt, Durchführung eines vollständigen Builds durch BSCMAKE erforderlich.