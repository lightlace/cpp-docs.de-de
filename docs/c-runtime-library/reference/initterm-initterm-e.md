---
title: "_initterm, _initterm_e | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_initterm_e"
  - "_initterm"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_initterm_e"
  - "initterm"
  - "_initterm"
  - "initterm_e"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "initterm-Funktion"
  - "initterm_e-Funktion"
  - "_initterm-Funktion"
  - "_initterm_e-Funktion"
ms.assetid: 85131efe-c747-429a-8897-bcdedb000172
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# _initterm, _initterm_e
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Interne Methoden, die eine Tabelle von Funktionszeigern durchlaufen und sie initialisieren.  
  
 Der erste Zeiger ist die Anfangsposition in der Tabelle und die zweite Zeiger ist der Endespeicherort.  
  
## Syntax  
  
```  
void __cdecl _initterm(  
   PVFV *,  
   PVFV *  
);  
  
int __cdecl _initterm_e(  
   PVFV *,  
   PVFV *  
);  
```  
  
## Rückgabewert  
 Ein Fehlercode ungleich 0 \(null\), wenn eine Initialisierung und verlässt einen Fehler auslöst; 0 Wenn kein Fehler auftritt.  
  
## Hinweise  
 Diese Methoden sind nur intern während der Initialisierung aus einem C\+\+\-Programm aufgerufen.  Rufen Sie diese Methoden in einem Programm auf.  
  
 Wenn diese Methoden eine Tabelle von Funktionseinträgen durchlaufen, überspringen sie `NULL` Einträge und Fortfahren.  
  
## Siehe auch  
 [Alphabetische Funktionsreferenz](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)