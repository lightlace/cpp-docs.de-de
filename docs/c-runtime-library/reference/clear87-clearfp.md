---
title: "_clear87, _clearfp"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "_clearfp"
  - "_clear87"
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
  - "clearfp"
  - "_clearfp"
  - "_clear87"
  - "clear87"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_clear87-Funktion"
  - "_clearfp-Funktion"
  - "clear87-Funktion"
  - "clearfp-Funktion"
  - "Löschen des Gleitkommastatusworts"
ms.assetid: 72d24a70-7688-4793-ae09-c96d33fcca52
caps.latest.revision: 17
caps.handback.revision: "15"
ms.author: "corob"
manager: "ghogen"
---
# _clear87, _clearfp
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft das Gleitkommastatuswort ab und löscht dieses.  
  
## Syntax  
  
```  
unsigned int _clear87( void );  
unsigned int _clearfp( void );  
```  
  
## Rückgabewert  
 Die Bits im zurückgegebenen Wert geben vor dem Aufruf von `_clear87` und `_clearfp` den Gleitkommastatus an.  Eine vollständige Definition der Bits, die von `_clear87` zurückgegeben werden, finden Sie in Float.h.  Viele Funktionen der mathematischen Bibliothek ändern das 8087\/80287\-Statuswort, was zu unvorhersehbaren Ergebnissen führt.  Die Rückgabewerte von `_clear87` und `_status87` sind zuverlässiger, wenn weniger Gleitkommavorgänge zwischen den bekannten Zuständen des Gleitkommastatusworts ausgeführt werden.  
  
## Hinweise  
 Die `_clear87`\-Funktion löscht die Ausnahmeflags im Gleitkommastatuswort, legt den BUSY\-Bit auf 0 fest und gibt das Statuswort zurück.  Das Gleitkommastatuswort ist eine Kombination aus dem 8087\/80287\-Statuswort und anderen Bedingungen, die von dem Handler für 8087\/80287\-Ausnahmen erkannt werden, z. B. ein Gleitkomma\-Stapelüberlauf und \-Stapelunterlauf.  
  
 `_clearfp` ist eine plattformunabhängige, portable Version der `_clear87`\-Routine.  Sie ist identisch mit `_clear87` auf Intel \(x86\)\-Plattformen und wird auch von den x64\- und ARM\-Plattformen unterstützt.  Um sicherzustellen, dass Ihr Gleitkommacode für x64 und ARM portabel ist, verwenden Sie `_clearfp`.  Wenn Ihre Zielobjekte nur x86\-Plattformen sind, können Sie entweder `_clear87` oder `_clearfp` verwenden.  
  
 Diese Funktionen sind für die Kompilierung mit [\/clr \(Common Language Runtime\-Kompilierung\)](../../build/reference/clr-common-language-runtime-compilation.md) oder `/clr:pure` veraltet, da die Common Language Runtime nur die standardmäßige Genauigkeit von Gleitkommawerten unterstützt.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_clear87`|\<float.h\>|  
|`_clearfp`|\<float.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_clear87.c  
// compile with: /Od  
  
// This program creates various floating-point   
// problems, then uses _clear87 to report on these problems.  
// Compile this program with Optimizations disabled (/Od).   
// Otherwise the optimizer will remove the code associated with   
// the unused floating-point values.  
//  
  
#include <stdio.h>  
#include <float.h>  
  
int main( void )  
{  
   double a = 1e-40, b;  
   float x, y;  
  
   printf( "Status: %.4x - clear\n", _clear87()  );  
  
   // Store into y is inexact and underflows:  
   y = a;  
   printf( "Status: %.4x - inexact, underflow\n", _clear87() );  
  
   // y is denormal:   
   b = y;  
   printf( "Status: %.4x - denormal\n", _clear87() );  
}  
```  
  
  **Status: 0000 – eindeutig**  
**Status: 0003 – ungenau, Unterlauf**  
**Status: 80000 – nicht normal**   
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [\_control87, \_controlfp, \_\_control87\_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md)   
 [\_status87, \_statusfp, \_statusfp2](../../c-runtime-library/reference/status87-statusfp-statusfp2.md)