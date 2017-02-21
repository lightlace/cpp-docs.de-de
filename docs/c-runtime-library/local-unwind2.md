---
title: "_local_unwind2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_local_unwind2"
apilocation: 
  - "msvcr110_clr0400.dll"
  - "msvcrt.dll"
  - "msvcr100.dll"
  - "msvcr110.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr120.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_local_unwind2"
  - "local_unwind2"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_local_unwind2-Funktion"
  - "local_unwind2-Funktion"
ms.assetid: 44f1fa82-e01e-490f-a6e6-18fc6811c28c
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# _local_unwind2
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Interne CRT\-Funktion.  Führt alle Beendigungshandler aus, die in der angegebenen Bereichtabelle aufgelistet sind.  
  
## Syntax  
  
```  
void _local_unwind2(    PEXCEPTION_REGISTRATION xr,    int stop );  
```  
  
#### Parameter  
 \[in\] `xr`  
 Ein Registrierungseintrag, der mit einer Bereichtabelle verbunden ist.  
  
 \[in\] `stop`  
 Die lexikalische Ebene, die darauf hinweist, wo `_local_unwind2` aufhören sollte.  
  
## Hinweise  
 Diese Methode wird nur von der Laufzeitumgebung verwendet.  Rufen Sie die Methode nicht in Ihrem Code auf.  
  
 Wenn diese Methode Beendigungshandler ausführt, beginnt sie an der aktuellen lexikalischen Ebene und arbeitet sich die lexikalischen Ebenen hoch, bis sie die Ebene erreicht, die von `stop` angegeben wird.  Sie führt keine Beendigungshandler auf der Ebene aus, die von `stop` angegeben ist.  
  
## Siehe auch  
 [Alphabetische Funktionsreferenz](../c-runtime-library/reference/crt-alphabetical-function-reference.md)