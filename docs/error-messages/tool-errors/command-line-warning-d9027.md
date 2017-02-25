---
title: "Befehlszeilenwarnung D9027 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "D9027"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "D9027"
ms.assetid: 2a29edc5-5649-48f2-9058-2057c747284c
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Befehlszeilenwarnung D9027
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Quelldatei '\<dateiname\>' ignoriert  
  
 Die Eingabequelldatei wurde von **CL.exe** ignoriert.  
  
 Diese Warnung kann durch ein Leerzeichen zwischen der \/Fo\-Option und einem Ausgabedateinamen auf der Befehlszeile mit der \/c\-Option ausgelöst werden.  Beispiel:  
  
```  
cl /c /Fo output.obj input.c   
```  
  
 Weil ein Leerzeichen zwischen **\/Fo** und `output.obj` vorhanden ist, interpretiert **CL.exe** die Zeichenfolge  als den Namen der Eingabedatei.  Zur Behebung des Problems entfernen Sie das Leerzeichen:  
  
```  
cl /c /Fooutput.obj input.c   
```