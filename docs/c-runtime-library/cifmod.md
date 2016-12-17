---
title: "_CIfmod"
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
  - "_CIfmod"
apilocation: 
  - "msvcrt.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr100.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr120.dll"
  - "msvcr110.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_CIfmod"
  - "CIfmod"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CIfmod (systemintern)"
  - "_CIfmod (systemintern)"
ms.assetid: 7c050653-7ec6-4810-b3a7-7a0057ea65ed
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# _CIfmod
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Berechnet den Gleitkommarest der obersten zwei Werte auf dem Stapel.  
  
## Syntax  
  
```  
void __cdecl _CIfmod();  
```  
  
## Hinweise  
 Diese Version der Funktion `fmod` ist eine spezialisierte Aufrufkonvention, die vom Compiler unterstützten.  Sie die Ausführung beschleunigt, da diese Kopien an generiert und können mit Registerzuordnung verhindert.  
  
 Der resultierende Wert wird an den Anfang des Stapels gedrückt.  
  
## Anforderungen  
 x86**Plattform:**  
  
## Siehe auch  
 [Alphabetische Funktionsreferenz](../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fmod, fmodf](../c-runtime-library/reference/fmod-fmodf.md)