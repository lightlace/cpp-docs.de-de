---
title: "_set_SSE2_enable"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "_set_SSE2_enable"
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
  - "api-ms-win-crt-math-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_set_SSE2_enable"
  - "set_SSE2_enable"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_set_SSE2_enable-Funktion"
  - "Streaming SIMD Extensions 2-Anweisungen"
  - "set_SSE2_enable-Funktion"
ms.assetid: 55db895d-fc1e-475a-9110-b781a9bb51c5
caps.latest.revision: 19
caps.handback.revision: "19"
ms.author: "corob"
manager: "ghogen"
---
# _set_SSE2_enable
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Aktiviert oder deaktiviert die Verwendung von Anweisungen [SIMD\-Streamingerweiterungen 2](assetId:///f98440eb-73a9-4f96-b203-ac41bb6701ea) \(SSE2\-Anweisungen\) in den CRT\-Matheroutinen. \(Dieses Feature ist nicht auf x64\-Architekturen verfügbar, da SSE2\-Anweisungen standardmäßig aktiviert wird.\)  
  
## Syntax  
  
```  
int _set_SSE2_enable(  
   int flag  
);  
```  
  
#### Parameter  
 `flag`  
 1, um der Implementierung SSE2\-Anweisungen zu aktivieren; 0, um der Implementierung SSE2\-Anweisungen zu deaktivieren.  Standardmäßig wird Implementierung SSE2\-Anweisungen in Prozessoren aktiviert, die sie unterstützen.  
  
## Rückgabewert  
 Wert ungleich 0 \(null\), wenn Implementierung SSE2\-Anweisungen aktiviert wird; null wenn Implementierung SSE2\-Anweisungen deaktiviert wird.  
  
## Hinweise  
 Die folgenden Funktionen sind Implementierungen SSE2\-Anweisungen, die aktiviert werden können, indem `_set_SSE2_enable` verwendet:  
  
-   [atan](../../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)  
  
-   [ceil](../../c-runtime-library/reference/ceil-ceilf-ceill.md)  
  
-   [exp](../../c-runtime-library/reference/exp-expf.md)  
  
-   [floor](../../c-runtime-library/reference/floor-floorf-floorl.md)  
  
-   [log](../../c-runtime-library/reference/log-logf-log10-log10f.md)  
  
-   [log10](../../c-runtime-library/reference/log-logf-log10-log10f.md)  
  
-   [modf](../../c-runtime-library/reference/modf-modff-modfl.md)  
  
-   [pow](../../c-runtime-library/reference/pow-powf-powl.md)  
  
 Die Implementierungen SSE2\-Anweisungen dieser Funktionen können möglicherweise etwas unterschiedliche Antworten als die Standardimplementierungen, da Zwischenwerte SSE2\-Anweisungen 64\-Bit\-Gleitkommamengen sind, die Standardimplementierungszwischenwerte 80 Bitgleitkommamengen sind.  
  
> [!NOTE]
>  Wenn die Compileroption [\/Oi \(Generieren Sie systeminterne Funktionen\)](../../build/reference/oi-generate-intrinsic-functions.md) verwenden, das Projekt zu kompilieren, wird es möglicherweise, dass `_set_SSE2_enable` keine Auswirkungen.  Die Compileroption `/Oi` erteilt den Compiler der geringer, dass systeminterne Funktionen verwenden, um CRT\-Aufrufe ersetzen; dieses Verhalten hebt die Auswirkungen von `_set_SSE2_enable` auf.  Wenn Sie sicherstellen möchten, dass `/Oi` nicht `_set_SSE2_enable` überschreibt, verwenden Sie `/Oi-`, das Projekt zu kompilieren.  Dies kann außerdem ratsam, wenn Sie andere Compilerschalter verwenden, die `/Oi` haben.  
  
 Die Implementierung SSE2\-Anweisungen wird nur verwendet, wenn alle Ausnahmen maskiert werden.  Verwenden Sie [\_control87, \_controlfp](../../c-runtime-library/reference/control87-controlfp-control87-2.md), Ausnahmen zum Ausblenden.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_set_SSE2_enable`|\<math.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_set_SSE2_enable.c  
// processor: x86  
#include <math.h>  
#include <stdio.h>  
  
int main()  
{  
   int i = _set_SSE2_enable(1);  
  
   if (i)  
      printf("SSE2 enabled.\n");  
   else  
      printf("SSE2 not enabled; processor does not support SSE2.\n");  
}  
```  
  
 **Ausgabe**  
  
 `SSE2 enabled.`  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [CRT\-Bibliotheksfunktionen](../../c-runtime-library/crt-library-features.md)