---
title: "fwide | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "fwide"
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
apitype: "DLLExport"
f1_keywords: 
  - "fwide"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fwide-Funktion"
ms.assetid: a4641f5b-d74f-4946-95d5-53a64610d28d
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# fwide
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Unimplemented.  
  
## Syntax  
  
```  
int fwide(  
   FILE *stream,  
   int mode;  
);  
```  
  
#### Parameter  
 `stream`  
 Zeiger `FILE`\-Struktur \(ignoriert\).  
  
 `mode`  
 Die neue Breite des Streams: Positiv für das für Breitzeichen, negativ Byte, gleich unverändert wechseln. \(Dieser Wert wird ignoriert\).  
  
## Rückgabewert  
 Diese Funktion gibt derzeit nur `mode` zurück.  
  
## Hinweise  
 Die aktuelle Version der Funktion stimmt nicht mit dem Standard\- aus.  
  
## Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------------|  
|`fwide`|\<wchar.h\>|  
  
 Weitere Informationen finden Sie unter[Kompatibilität](../../c-runtime-library/compatibility.md).