---
title: "_CIlog10"
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
  - "_CIlog10"
apilocation: 
  - "msvcr100.dll"
  - "msvcr120.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr110_clr0400.dll"
  - "msvcrt.dll"
  - "msvcr110.dll"
apitype: "DLLExport"
f1_keywords: 
  - "CIlog10"
  - "_CIlog10"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_CIlog10 (systemintern)"
  - "CIlog10 (systemintern)"
ms.assetid: 05d7fcaa-3cff-4cc5-8d44-015e7cacba24
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# _CIlog10
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Führt einen `log10` \- Vorgang auf dem obersten Wert im Stapel aus.  
  
## Syntax  
  
```  
void __cdecl _CIlog10();  
```  
  
## Hinweise  
 Diese Version der Funktion `log10` ist eine spezialisierte Aufrufkonvention, die vom Compiler unterstützten.  Die Funktion beschleunigt die Ausführung, da diese Kopien an generiert und können mit Registerzuordnung verhindert.  
  
 Der resultierende Wert wird an den Anfang des Stapels gedrückt.  
  
## Anforderungen  
 x86**Plattform:**  
  
## Siehe auch  
 [Alphabetische Funktionsreferenz](../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [log, logf, log10, log10f](../c-runtime-library/reference/log-logf-log10-log10f.md)