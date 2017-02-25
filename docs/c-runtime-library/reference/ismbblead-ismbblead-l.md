---
title: "_ismbblead, _ismbblead_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_ismbblead_l"
  - "_ismbblead"
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
  - "ismbblead_l"
  - "istlead"
  - "_ismbblead"
  - "_ismbblead_l"
  - "ismbblead"
  - "_istlead"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ismbblead_l-Funktion"
  - "ismbblead-Funktion"
  - "_ismbblead-Funktion"
  - "istlead-Funktion"
  - "ismbblead_l-Funktion"
  - "_istlead-Funktion"
ms.assetid: 2abc6f75-ed5c-472e-bfd0-e905a1835ccf
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# _ismbblead, _ismbblead_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Testet ein Zeichen, um festzustellen, ob es sich um ein führendes Byte eines Multibytezeichens handelt.  
  
## Syntax  
  
```  
int _ismbblead(  
   unsigned int c   
);  
int _ismbblead_l(  
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
 Gibt einen Wert ungleich 0 \(null\) zurück, wenn die ganze Zahl `c` das erste Byte eines Multibytezeichens ist.  
  
## Hinweise  
 Multibytezeichen bestehen aus einem führenden Byte gefolgt von einem nachfolgendem Byte. Führende Bytes werden anhand ihrer Zugehörigkeit zu einem bestimmten Bereich für einen gegebenen Zeichensatz unterschieden. Auf der Codepage 932 reichen die führenden Bytes von 0x81 \- 0x9F und 0xE0 \- 0xFC.  
  
 `_ismbblead` verwendet das aktuelle Gebietsschema für ein gebietsschemaabhängiges Verhalten.`_ismbblead_l` ist identisch, verwendet jedoch stattdessen das übergebene Gebietsschema. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
### Zuordnung generischer Textroutinen  
  
|Tchar.h\-Routine|\_UNICODE und \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|------------------------------------------|----------------------|-------------------------|  
|`_istlead`|Gibt immer "false" zurück|`_ismbblead`|Gibt immer "false" zurück|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|Optionaler Header|  
|-------------|---------------------------|-----------------------|  
|`_ismbblead`|\<mbctype.h\> oder \<mbstring.h\>|\<ctype.h\>,\* \<limits.h\>, \<stdlib.h\>|  
|`_ismbblead_l`|\<mbctype.h\> oder \<mbstring.h\>|\<ctype.h\>,\* \<limits.h\>, \<stdlib.h\>|  
  
 \* Für Manifestkonstanten für die Testbedingungen.  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Byteklassifizierung](../../c-runtime-library/byte-classification.md)   
 [\_ismbb\-Routinen](../../c-runtime-library/ismbb-routines.md)