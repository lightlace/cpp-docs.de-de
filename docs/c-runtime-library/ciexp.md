---
title: "_CIexp | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CIexp"
apilocation: 
  - "msvcr120.dll"
  - "msvcr80.dll"
  - "msvcr110.dll"
  - "msvcr100.dll"
  - "msvcrt.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr90.dll"
apitype: "DLLExport"
f1_keywords: 
  - "CIexp"
  - "_CIexp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CIexp (systemintern)"
  - "_CIexp (systemintern)"
ms.assetid: f8a3e3b7-fa57-41a3-9983-6c81914cbb55
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# _CIexp
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Berechnet die Exponentialfunktion des obersten Wert auf dem Stapel.  
  
## Syntax  
  
```  
void __cdecl _CIexp();  
```  
  
## Hinweise  
 Diese Version der Funktion `exp` ist eine spezialisierte Aufrufkonvention, die vom Compiler unterstützten.  Sie die Ausführung beschleunigt, da diese Kopien an generiert und können mit Registerzuordnung verhindert.  
  
 Der resultierende Wert wird an den Anfang des Stapels gedrückt.  
  
## Anforderungen  
 x86**Plattform:**  
  
## Siehe auch  
 [Alphabetische Funktionsreferenz](../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [exp, expf](../c-runtime-library/reference/exp-expf.md)