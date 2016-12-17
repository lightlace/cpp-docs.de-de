---
title: "_mbbtombc, _mbbtombc_l"
ms.custom: na
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "_mbbtombc_l"
  - "_mbbtombc"
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
  - "_mbbtombc_l"
  - "_mbbtombc"
  - "mbbtombc_l"
  - "mbbtombc"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mbbtombc-Funktion"
  - "_mbbtombc_l-Funktion"
  - "mbbtombc-Funktion"
  - "mbbtombc_l-Funktion"
ms.assetid: 78593389-b0fc-43b6-8c1f-2a6bf702d64e
caps.latest.revision: 19
caps.handback.revision: "19"
ms.author: "corob"
manager: "ghogen"
---
# _mbbtombc, _mbbtombc_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Konvertiert ein Einzelbyte\-Multibytezeichen in ein entsprechendes Doppelbyte\-Multibytezeichen.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die im [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausgeführt werden.  Weitere Informationen finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
unsigned int _mbbtombc(  
   unsigned int c   
);  
unsigned int _mbbtombc_l(  
   unsigned int c,  
   _locale_t locale  
);  
```  
  
#### Parameter  
 `c`  
 Zu konvertierendes Einzelbytezeichen.  
  
 `locale`  
 Zu verwendendes Gebietsschema.  
  
## Rückgabewert  
 Wenn `c` erfolgreich von `_mbbtombc` konvertiert wird, wird ein Multibytezeichen zurückgegeben, andernfalls wird `c` zurückgegeben.  
  
## Hinweise  
 Die `_mbbtombc`\-Funktion konvertiert ein angegebenes Einzelbyte\-Multibytezeichen in ein entsprechendes Doppelbyte\-Multibytezeichen.  Die Zeichen müssen innerhalb des Bereichs 0x20–0x7E oder 0xA1–0xDF liegen, um konvertiert zu werden.  
  
 Der Ausgabewert ist von der `LC_CTYPE`\-Kategorieneinstellung des Gebietsschemas betroffen; weitere Informationen finden Sie unter [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).  Die Versionen dieser Funktion sind identisch, außer, dass diese `_mbbtombc`\-Version das aktuelle Gebietsschema für dieses vom Gebietsschema abhängige Verhalten verwendet und die `_mbbtombc_l`\-Version stattdessen den ihr übergebenen Gebietsschemaparameter verwendet.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
 In früheren Versionen hieß `_mbbtombc` `hantozen`.  Verwenden Sie bei neuem Code `_mbbtombc`.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_mbbtombc`|\<mbstring.h\>|  
|`_mbbtombc_l`|\<mbstring.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [\_mbctombb, \_mbctombb\_l](../../c-runtime-library/reference/mbctombb-mbctombb-l.md)