---
title: "NMAKE: Schwerwiegender Fehler U1001 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "U1001"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1001"
ms.assetid: 5d7da559-6cbd-44d6-848c-aaf54cae0d1a
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# NMAKE: Schwerwiegender Fehler U1001
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Syntaxfehler: ungültiges Zeichen "Zeichen" in Makro  
  
 Das angegebene Zeichen ist in einem Makro aufgetreten. Es handelt sich jedoch nicht um einen Buchstaben, eine Zahl oder einen Unterstrich.  
  
 Dieser Fehler kann durch einen fehlenden Doppelpunkt in einer Makroerweiterung verursacht werden:  
  
```  
syntax error : illegal character '=' in macro  
```