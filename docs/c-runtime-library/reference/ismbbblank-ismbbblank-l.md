---
title: "_ismbbblank, _ismbbblank_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_ismbbblank_l"
  - "_ismbbblank"
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
  - "api-ms-win-crt-multibyte-l1-1-0.dll"
apitype: "DLLExport"
dev_langs: 
  - "C++"
ms.assetid: d21b2e41-7206-41f5-85bb-9c9ab4f3e21b
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# _ismbbblank, _ismbbblank_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bestimmt, ob ein angegebenes Multibytezeichen ein Leerzeichen ist.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows\-Runtime ausgeführt werden.  Weitere Informationen finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
int _ismbbblank(  
   unsigned int c   
);  
int _ismbbblank_l(  
   unsigned int c,  
   _locale_t locale  
);  
```  
  
#### Parameter  
 `c`  
 Die zu testende ganze Zahl.  
  
 `locale`  
 Zu verwendendes Gebietsschema.  
  
## Rückgabewert  
 `_ismbbblank` gibt einen Wert ungleich 0 \(null\) zurück, wenn `c` ein Leerzeichen \(0x20\), einen horizontalen Tabulator \(0x09\) oder ein gebietsschemaspezifisches Zeichen darstellt, das verwendet wird, um Wörter in einem Text voneinander zu trennen, für den `isspace` true ist; gibt andernfalls 0 \(null\) zurück.  `_ismbbblank` verwendet das aktuelle Gebietsschema für jedes gebietsschemaabhängige Verhalten.  `_ismbbblank_l` ist nahezu identisch, verwendet jedoch stattdessen den übergebenen Gebietsschemaparameter.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_ismbbblank`|\<mbctype.h\>|  
|`_ismbbblank_l`|\<mbctype.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Byteklassifizierung](../../c-runtime-library/byte-classification.md)   
 [\_ismbb\-Routinen](../../c-runtime-library/ismbb-routines.md)