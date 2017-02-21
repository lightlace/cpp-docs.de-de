---
title: "NMAKE: Schwerwiegender Fehler U1099 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "U1099"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1099"
ms.assetid: 6688a805-43e6-4247-a2d0-14be082f0b13
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# NMAKE: Schwerwiegender Fehler U1099
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stapelüberlauf  
  
 Das verarbeitete Makefile war zu komplex für die aktuelle Stapelreservierungsgröße.  NMAKE reserviert 0x3000 \(12 KB\).  
  
 Um die Stapelreservierungsgröße von NMAKE zu erhöhen, wird das [editbin \/stack](../../build/reference/stack.md)\-Dienstprogramm mit einer größeren Stapeloption ausgeführt:  
  
 **editbin \/STACK:**   
 ***reserve* NMAKE.EXE**  
  
 Bei *reserve* handelt es sich um eine größere Zahl als die aktuelle Stapelreservierungsgröße in NMAKE.