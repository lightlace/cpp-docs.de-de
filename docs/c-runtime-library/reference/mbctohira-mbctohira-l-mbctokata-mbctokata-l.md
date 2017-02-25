---
title: "_mbctohira, _mbctohira_l, _mbctokata, _mbctokata_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mbctohira"
  - "_mbctohira_l"
  - "_mbctokata"
  - "_mbctokata_l"
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
  - "_mbctokata"
  - "mbctohira"
  - "_mbctohira"
  - "_mbctohira_l"
  - "mbctokata"
  - "mbctokata_l"
  - "mbctohira_l"
  - "_mbctokata_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_mbctohira-Funktion"
  - "_mbctohira_l-Funktion"
  - "_mbctokata-Funktion"
  - "_mbctokata_l-Funktion"
  - "mbctohira-Funktion"
  - "mbctohira_l-Funktion"
  - "mbctokata-Funktion"
  - "mbctokata_l-Funktion"
ms.assetid: f949afd7-44d4-4f08-ac8f-1fef2c915a1c
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# _mbctohira, _mbctohira_l, _mbctokata, _mbctokata_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Konvertiert zwischen Hiragana\- und Katakana\-Zeichen.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die im [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausgeführt werden.  Weitere Informationen finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
unsigned int _mbctohira(  
   unsigned int c   
);  
unsigned int _mbctohira_l(  
   unsigned int c,  
   _locale_t locale  
);  
unsigned int _mbctokata(  
   unsigned int c   
);  
unsigned int _mbctokata_l(  
   unsigned int c,  
   _locale_t locale  
);  
```  
  
#### Parameter  
 `c`  
 Zu konvertierendes Multibytezeichen.  
  
 `locale`  
 Zu verwendendes Gebietsschema.  
  
## Rückgabewert  
 Jede dieser Funktionen gibt das konvertierte Zeichen `c` zurück, sofern dies möglich ist.  Andernfalls wird das Zeichen `c` unverändert zurückgegeben.  
  
## Hinweise  
 Die `_mbctohira`\- und `_mbctokata`\-Funktionen testen ein Zeichen `c` und geben, falls möglich, eine der folgenden Konvertierungen zurück.  
  
|Routinen|Konvertiert|  
|--------------|-----------------|  
|`_mbctohira,_mbctohira_l`|Multibyte\-Katakana in Multibyte\-Hiragana.|  
|`_mbctokata,_mbctokata_l`|Multibyte\-Hiragana in Multibyte\-Katakana.|  
  
 Der Ausgabewert ist von der `LC_CTYPE`\-Kategorieneinstellung des Gebietsschemas betroffen; weitere Informationen finden Sie unter [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).  Die Versionen dieser Funktionen sind nahezu identisch, außer dass diejenigen ohne das `_l`\-Suffix für dieses Gebietsschema\-abhängige Verhalten das aktuelle Gebietsschema verwenden, und diejenigen mit `_l`\-Suffix den übergebenen Gebietsschemaparameter.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
 In früheren Versionen hieß `_mbctohira` `jtohira` und `_mbctokata` `jtokata`.  Verwenden Sie bei neuem Code die neuen Namen.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_mbctohira`|\<mbstring.h\>|  
|`_mbctohira_l`|\<mbstring.h\>|  
|`_mbctokata`|\<mbstring.h\>|  
|`_mbctokata_l`|\<mbstring.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [\_mbcjistojms, \_mbcjistojms\_l, \_mbcjmstojis, \_mbcjmstojis\_l](../../c-runtime-library/reference/mbcjistojms-mbcjistojms-l-mbcjmstojis-mbcjmstojis-l.md)   
 [\_mbctolower, \_mbctolower\_l, \_mbctoupper, \_mbctoupper\_l](../../c-runtime-library/reference/mbctolower-mbctolower-l-mbctoupper-mbctoupper-l.md)   
 [\_mbctombb, \_mbctombb\_l](../../c-runtime-library/reference/mbctombb-mbctombb-l.md)