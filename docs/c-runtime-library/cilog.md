---
title: "_CIlog"
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
  - "_CIlog"
apilocation: 
  - "msvcr90.dll"
  - "msvcr120.dll"
  - "msvcr80.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr100.dll"
  - "msvcrt.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_CIlog"
  - "CIlog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_CIlog (systemintern)"
  - "CIlog (systemintern)"
ms.assetid: 23503854-ddaa-4fe0-a4a3-7fbb3a43bdec
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# _CIlog
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Berechnet den natürlichen Logarithmus des obersten Werts im Stapel.  
  
## Syntax  
  
```  
void __cdecl _CIlog();  
```  
  
## Hinweise  
 Diese Version der Funktion `log` ist eine spezialisierte Aufrufkonvention, die vom Compiler unterstützten.  Sie die Ausführung beschleunigt, da diese Kopien an generiert und können mit Registerzuordnung verhindert.  
  
 Der resultierende Wert wird an den Anfang des Stapels gedrückt.  
  
## Anforderungen  
 x86**Plattform:**  
  
## Siehe auch  
 [Alphabetische Funktionsreferenz](../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [log, logf, log10, log10f](../c-runtime-library/reference/log-logf-log10-log10f.md)