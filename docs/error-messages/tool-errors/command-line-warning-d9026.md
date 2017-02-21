---
title: "Befehlszeilenwarnung D9026 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "D9026"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "D9026"
ms.assetid: 149fe5e3-5329-4be8-b871-49dfd423aaba
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Befehlszeilenwarnung D9026
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Optionen betreffen die gesamte Befehlszeile  
  
 Eine Option wurde zu einem Befehl angegeben, nachdem ein Dateiname angegeben wurde.  Die Option wurde auf die Datei, die dieser voranging, angewendet.  
  
 Beispielsweise wird im Befehl  
  
```  
CL verdi.c /G5 puccini.c  
```  
  
 die Datei **VERDI.c** mit der **\/G5**\-Option kompiliert, nicht mit der **\/G4**\-Standardoption.  
  
 Dieses Verhalten unterscheidet sich von dem einiger früherer Versionen, von denen nur die Optionen angewendet wurden, die vor dem Dateinamen angegeben wurden. Dies führte dazu, dass **VERDI.c** mit der **\/G4**\-Option und **PUCCINI.c** mit der **\/G5**\-Option kompiliert wurde.