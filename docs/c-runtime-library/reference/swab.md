---
title: "_swab | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_swab"
  - "stdlib/_swab"
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
  - "api-ms-win-crt-utility-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_swab"
  - "stdlib/_swab"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_swap-Funktion"
  - "Bytes, Austauschen"
  - "swab-Funktion"
  - "Austauschen von Bytes"
ms.assetid: 017142f2-050c-4f6a-8b49-6b094f58ec94
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# _swab
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vertauscht Bytes aus.  
  
## Syntax  
  
```  
void _swab(  
   char *src,  
   char *dest,  
   int n   
);  
```  
  
#### Parameter  
 `src`  
 Kopiert werden und Daten ausgetauscht wurde.  
  
 `dest`  
 Speicherort für ausgetauschte Daten.  
  
 `n`  
 Zahl kopiert werden und ausgetauscht wurde Bytes.  
  
## Hinweise  
 Wenn `n` gerade ist, kopiert die `_swab``n`\-Funktion von Bytes `src`, tauscht jedes Paar benachbarte Bytes aus und speichert das Ergebnis bei `dest`.  Wenn `n` ungerade ist, kopiert `_swab` und tauscht die ersten `n-1` Bytes von `src` aus.  `_swab` wird in der Regel verwendet, um Binärdaten für die Übertragung auf einen Computer vorbereiten, der eine andere Bytereihenfolge verwendet.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_swab`|\<stdlib.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_swab.c  
  
#include <stdlib.h>  
#include <stdio.h>  
  
char from[] = "BADCFEHGJILKNMPORQTSVUXWZY";  
char to[] =   "..........................";  
  
int main()  
{  
    printf( "Before: %s\n        %s\n\n", from, to );  
    _swab( from, to, sizeof( from ) );  
    printf( "After:  %s\n        %s\n\n", from, to );  
}  
```  
  
  **Vorher: BADCFEHGJILKNMPORQTSVUXWZY**  
 **..........................**  
**Nachher: BADCFEHGJILKNMPORQTSVUXWZY**  
 **ABCDEFGHIJKLMNOPQRSTUVWXYZ**   
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Pufferbearbeitung](../../c-runtime-library/buffer-manipulation.md)