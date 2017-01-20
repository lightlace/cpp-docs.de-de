---
title: "NMAKE: Schwerwiegender Fehler U1064"
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
  - "U1064"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1064"
ms.assetid: 7141e66e-cde6-4173-84df-a391f3ebcdd1
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# NMAKE: Schwerwiegender Fehler U1064
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

MAKEFILE nicht gefunden und kein Ziel angegeben  
  
 In der NMAKE\-Befehlszeile wurde kein Makefile oder kein Ziel angegeben, und das aktuelle Verzeichnis enthielt keine Datei mit dem Namen **MAKEFILE**.  
  
 Für NMAKE ist entweder ein Makefile oder ein Befehlszeilenziel oder beides erforderlich.  Um NMAKE ein Makefile zur Verfügung zu stellen, wird entweder die **\/F**\-Option angegeben oder eine Datei mit der Bezeichnung **MAKEFILE** im aktuellen Verzeichnis abgelegt.  Mit NMAKE kann unter Verwendung von Rückschlussregeln ein Befehlszeilenziel erstellt werden, falls kein Makefile angegeben ist.