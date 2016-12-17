---
title: "_acmdln, _tcmdln, _wcmdln"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "_wcmdln"
  - "_acmdln"
apilocation: 
  - "msvcrt.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_acmdln"
  - "acmdln"
  - "_wcmdln"
  - "wcmdln"
  - "_tcmdln"
  - "tcmdln"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_acmdln (globale Variable)"
  - "_tcmdln (globale Variable)"
  - "_wcmdln (globale Variable)"
  - "acmdln (globale Variable)"
  - "tcmdln (globale Variable)"
  - "wcmdln (globale Variable)"
ms.assetid: 4fc0a6a0-3f93-420a-a19f-5276061ba539
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# _acmdln, _tcmdln, _wcmdln
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Interne globale CRT\-Variable.  Die Befehlszeile.  
  
## Syntax  
  
```  
char * _acmdln; wchar_t * _wcmdln;  #ifdef WPRFLAG    #define _tcmdln _wcmdln #else    #define _tcmdln _acmdln  
```  
  
## Hinweise  
 Diese internen CRT\-Variablen speichern die vollständige Befehlszeile.  Sie sind in den exportierten Symbolen für die CRT verfügbar, aber nicht zur Verwendung in Ihrem Code vorgesehen.  `_acmdln` speichert die Daten als Zeichenfolge.  `_wcmdln` speichert die Daten als Breitzeichen\-Zeichenfolge.  `_tcmdln` kann als `_acmdln` oder  `_wcmdln` definiert werden, abhängig davon, was angemessen ist.  
  
## Siehe auch  
 [Globale Variablen](../c-runtime-library/global-variables.md)