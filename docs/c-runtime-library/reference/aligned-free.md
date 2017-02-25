---
title: "_aligned_free | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_aligned_free"
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
  - "api-ms-win-crt-heap-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "aligned_free"
  - "_aligned_free"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_aligned_free-Funktion"
  - "aligned_free-Funktion"
ms.assetid: ed1ce952-cdfc-4682-85cc-f75d4101603d
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# _aligned_free
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt einen Speicherblock freigeben, der mit [\_aligned\_malloc](../../c-runtime-library/reference/aligned-malloc.md) oder [\_aligned\_offset\_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md) zugeordnet wurde.  
  
## Syntax  
  
```  
void _aligned_free (  
   void *memblock  
);  
```  
  
#### Parameter  
 `memblock`  
 Ein Zeiger auf den Speicherblock, der der `_aligned_malloc``_aligned_offset_malloc` oder Funktion zurückgegeben wurde.  
  
## Hinweise  
 `_aligned_free` ist als `__declspec(noalias)` gekennzeichnet und bedeutet, dass die Funktion, die gewährleistet sind globale Variablen nicht zu ändern.  Weitere Informationen finden Sie unter [noalias](../../cpp/noalias.md).  
  
 Diese Funktion liest nicht ihren Parameter, von den anderen \_aligned CRT\-Funktionen.  Wenn `memblock` ein `NULL` Zeiger ist, wird diese Funktion einfach keine Aktionen aus.  Sie wird `errno` nicht und sie ruft nicht void Parameterhandler auf.  Wenn ein Fehler in der Funktion aufgrund nicht mit der \_aligned Funktionen zuvor auftritt, um den Speicherblock zuzuordnen, oder eine unzulässige Ausrichtung des Arbeitsspeichers aufgrund eines Unglücks unvorhergesehenen auftritt, generiert die Funktion ein Debugbericht von [\_RPT\-, \_RPTF\-, \_RPTW\- und \_RPTFW\-Makros](../../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_aligned_free`|\<malloc.h\>|  
  
## Beispiel  
 Weitere Informationen finden Sie unter [\_aligned\_malloc](../../c-runtime-library/reference/aligned-malloc.md).  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Datenausrichtung](../../c-runtime-library/data-alignment.md)