---
title: "_ismbbkprint, _ismbbkprint_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_ismbbkprint"
  - "_ismbbkprint_l"
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
f1_keywords: 
  - "_ismbbkprint_l"
  - "ismbbkprint"
  - "_ismbbkprint"
  - "ismbbkprint_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ismbbkprint-Funktion"
  - "ismbbkprint_l-Funktion"
  - "ismbbkprint-Funktion"
  - "_ismbbkprint_l-Funktion"
ms.assetid: 8d1d3258-1e34-4365-81ed-97c95de25475
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# _ismbbkprint, _ismbbkprint_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bestimmt, ob ein bestimmtes Multibytezeichen ein Interpunktionszeichen ist.  
  
## Syntax  
  
```  
int _ismbbkprint(  
   unsigned int c   
);  
int _ismbbkprint_l(  
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
 `_ismbbkprint` gibt einen Wert ungleich 0 \(null\) zurück, wenn die ganze Zahl `c` ein Nicht\-ASCII\-Text oder ein Nicht\-ASCII\-Interpunktionssymbol ist. Andernfalls wird 0 zurückgegeben. Beispielsweise testet in Codepage 932 `_ismbbkprint` nur auf alphanumerische Katakana\-Zeichen oder Katakana\-Interpunktion \(Bereich: 0xA1–0xDF\).`_ismbbkprint` verwendet das aktuelle Gebietsschema für gebietsschemaabhängige Zeicheneinstellungen.`_ismbbkprint_l`  ist nahezu identisch, verwendet jedoch stattdessen das übergebene Gebietsschema. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_ismbbkprint`|\<mbctype.h\>|  
|`_ismbbkprint_l`|\<mbctype.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Byteklassifizierung](../../c-runtime-library/byte-classification.md)   
 [\_ismbb\-Routinen](../../c-runtime-library/ismbb-routines.md)