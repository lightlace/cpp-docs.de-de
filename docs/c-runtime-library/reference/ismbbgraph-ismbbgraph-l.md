---
title: "_ismbbgraph, _ismbbgraph_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_ismbbgraph_l"
  - "_ismbbgraph"
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
  - "_ismbbgraph"
  - "_ismbbgraph_l"
  - "ismbbgraph"
  - "ismbbgraph_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ismbbgraph_l-Funktion"
  - "ismbbgraph_l-Funktion"
  - "_ismbbgraph-Funktion"
  - "ismbbgraph-Funktion"
ms.assetid: b60db718-134f-4796-acc1-592d0b9efbb7
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# _ismbbgraph, _ismbbgraph_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bestimmt, ob ein bestimmtes Multibytezeichen ein Grafikzeichen ist.  
  
## Syntax  
  
```  
int _ismbbgraph (  
   unsigned int c   
);  
int _ismbbgraph_l (  
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
 Gibt einen Wert ungleich 0 \(null\) zurück, wenn diese Bedingung zutrifft. Der Ausdruck:  
  
```  
( _PUNCT | _UPPER | _LOWER | _DIGIT ) || _ismbbkprint  
```  
  
 ist für `c` ungleich 0, bzw. andernfalls 0.`_ismbbgraph` verwendet das aktuelle Gebietsschema für jedes gebietsschemaabhängige Verhalten.`_ismbbgraph_l` ist identisch, verwendet jedoch stattdessen das übergebene Gebietsschema. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_ismbbgraph`|\<mbctype.h\>|  
|`_ismbbgraph_l`|\<mbctype.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Bibliotheken  
 Alle Versionen [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Byteklassifizierung](../../c-runtime-library/byte-classification.md)   
 [\_ismbb\-Routinen](../../c-runtime-library/ismbb-routines.md)