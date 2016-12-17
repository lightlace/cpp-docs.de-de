---
title: "_ismbclegal, _ismbclegal_l, _ismbcsymbol, _ismbcsymbol_l"
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
  - "_ismbclegal_l"
  - "_ismbclegal"
  - "_ismbcsymbol"
  - "_ismbcsymbol_l"
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
  - "ismbcsymbol_l"
  - "_ismbcsymbol_l"
  - "_ismbcsymbol"
  - "_ismbclegal_l"
  - "_ismbclegal"
  - "ismbclegal_l"
  - "ismbcsymbol"
  - "ismbclegal"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ismbclegal-Funktion"
  - "_ismbclegal_l-Funktion"
  - "_ismbcsymbol-Funktion"
  - "_ismbcsymbol_l-Funktion"
  - "_istlegal-Funktion"
  - "_istlegal_l-Funktion"
  - "ismbclegal-Funktion"
  - "ismbclegal_l-Funktion"
  - "ismbcsymbol-Funktion"
  - "ismbcsymbol_l-Funktion"
  - "istlegal-Funktion"
  - "istlegal_l-Funktion"
ms.assetid: 31bf1ea5-b56f-4e28-b21e-b49a2cf93ffc
caps.latest.revision: 18
caps.handback.revision: "18"
ms.author: "corob"
manager: "ghogen"
---
# _ismbclegal, _ismbclegal_l, _ismbcsymbol, _ismbcsymbol_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Überprüft, ob ein Multibytezeichen ein gültiges Zeichen oder ein Symbolzeichen ist.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows\-Runtime ausgeführt werden.  Weitere Informationen finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
int _ismbclegal(  
   unsigned int c   
);  
int _ismbclegal_l(  
   unsigned int c,   
   _locale_t locale  
);  
int _ismbcsymbol(  
   unsigned int c   
);  
int _ismbcsymbol_l(  
   unsigned int c,  
   _locale_t locale  
);  
```  
  
#### Parameter  
 `c`  
 Zu testende Zeichen.  
  
 `locale`  
 Zu verwendendes Gebietsschema.  
  
## Rückgabewert  
 Jede dieser Routinen gibt einen Wert ungleich 0 zurück, wenn das Zeichen die Testbedingung erfüllt, bzw. 0, wenn es sie nicht erfüllt.  Wenn `c`\<\= 255 und gibt eine entsprechende `_ismbb` Routine \(beispielsweise, entspricht `_ismbcalnum` in `_ismbbalnum`\), ist, ist das Ergebnis der Rückgabewert der entsprechenden `_ismbb` Routine.  
  
## Hinweise  
 Jede dieser Funktionen testet ein angegebenes Mehrbytezeichen auf eine angegebene Bedingung.  
  
 Die Versionen dieser Funktionen mit dem `_l`\-Suffix sind beinahe identisch, verwenden jedoch das ihnen übergebene Gebietsschema anstelle des aktuellen Gebietsschemas für ihr vom Gebietsschema abhängiges Verhalten.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
|Routine|Testbedingung|Beispiel für Codepage 932|  
|-------------|-------------------|-------------------------------|  
|`_ismbclegal`|Gültiges Multibyte|Gibt einen Wert ungleich 0 \(null\) nur dann zurück, wenn das erste Byte von `c` im Bereich 0x81 \- 0x9F oder 0xE0 \- 0xFC liegt, während das zweite Byte im Bereich 0x40 \- 0x7E oder 0x80 \- FC liegt.|  
|`_ismbcsymbol`|Multibytesymbol|Gibt nur dann einen Wert ungleich 0 \(null\) zurück, wenn 0x8141\=\<`c`\<\=0x81AC ist.|  
  
### Zuordnung generischer Textroutinen  
  
|Tchar.h\-Routine|\_UNICODE und \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|------------------------------------------|----------------------|-------------------------|  
|`_istlegal`|Gibt immer "false" zurück|`_ismbclegal`|Gibt immer false zurück.|  
|`_istlegal_l`|Gibt immer "false" zurück|`_ismbclegal_l`|Gibt immer false zurück.|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_ismbclegal,_ismbclegal_l`|\<mbstring.h\>|  
|`_ismbcsymbol,_ismbcsymbol_l`|\<mbstring.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Zeichenklassifizierung](../../c-runtime-library/character-classification.md)   
 [\_ismbc\-Routinen](../../c-runtime-library/ismbc-routines.md)   
 [is\- und isw\-Routinen](../../c-runtime-library/is-isw-routines.md)   
 [\_ismbb\-Routinen](../../c-runtime-library/ismbb-routines.md)