---
title: "_ismbslead, _ismbstrail, _ismbslead_l, _ismbstrail_l"
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
  - "_ismbstrail"
  - "_ismbslead_l"
  - "_ismbslead"
  - "_ismbstrail_l"
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
  - "_ismbslead"
  - "ismbs"
  - "ismbslead_l"
  - "_ismbs"
  - "ismbstrail_l"
  - "ismbslead"
  - "_ismbstrail"
  - "_ismbstrail_l"
  - "ismbstrail"
  - "_ismbslead_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ismbslead-Funktion"
  - "_ismbslead_l-Funktion"
  - "_ismbstrail-Funktion"
  - "_ismbstrail_l-Funktion"
  - "ismbslead-Funktion"
  - "ismbslead_l-Funktion"
  - "ismbstrail-Funktion"
  - "ismbstrail_l-Funktion"
ms.assetid: 86d2cd7a-3cff-443a-b713-14cc17a231e9
caps.latest.revision: 22
caps.handback.revision: "22"
ms.author: "corob"
manager: "ghogen"
---
# _ismbslead, _ismbstrail, _ismbslead_l, _ismbstrail_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Führt kontextbezogene Tests für führende und nachfolgende Bytes mit Multibyte\-Zechenfolgen aus und bestimmt, ob ein angegebener Teilzeichenfolgenzeiger auf ein führendes Byte oder ein nachfolgendes Byte zeigt.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die im [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausgeführt werden.  Weitere Informationen finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
int _ismbslead(  
   const unsigned char *str,  
   const unsigned char *current   
);  
int _ismbstrail(  
   const unsigned char *str,  
   const unsigned char *current   
);  
int _ismbslead_l(  
   const unsigned char *str,  
   const unsigned char *current,  
   _locale_t locale  
);  
int _ismbstrail_l(  
   const unsigned char *str,  
   const unsigned char *current,  
   _locale_t locale  
);  
```  
  
#### Parameter  
 `str`  
 Zeiger auf den Beginn der Zeichenfolge oder des vorherigen führenden Bytes.  
  
 `current`  
 Zeiger auf die zu testende Zeichenfolgenposition.  
  
 `locale`  
 Das zu verwendende Gebietsschema.  
  
## Rückgabewert  
 `_ismbslead` gibt \-1 zurück, wenn das Zeichen ein führendes Byte ist, und `_ismbstrail` gibt \-1 zurück, wenn das Zeichen ein nachfolgendes Byte ist.  Wenn die Eingabezeichenfolgen gültig sind, aber keine führenden oder nachfolgenden Bytes, geben diese Funktionen 0 zurück.  Wenn eines der Argumente `NULL` ist, wird der ungültige Parameterhandler wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben aufgerufen.  Wenn die weitere Ausführung zugelassen wird, geben diese Funktionen `NULL` zurück und stellen `errno` auf `EINVAL` ein.  
  
## Hinweise  
 `_ismbslead` und `_ismbstrail` sind langsamer als die `_ismbblead`\- und `_ismbbtrail`\-Versionen, da sie den Zeichenfolgenkontext berücksichtigen.  
  
 Die Versionen dieser Funktionen mit dem `_l`\-Suffix sind nahezu identisch, außer dass diejenigen mit dem Suffix anstelle des aktuellen Gebietsschemas das ihnen übergebene Gebietsschema für ihr vom Gebietsschema abhängiges Verhalten verwenden.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|Optionaler Header|  
|-------------|---------------------------|-----------------------|  
|`_ismbslead`|\<mbctype.h\> oder \<mbstring.h\>|\<ctype.h\>,\* \<limits.h\>, \<stdlib.h\>|  
|`_ismbstrail`|\<mbctype.h\> oder \<mbstring.h\>|\<ctype.h\>,\* \<limits.h\>, \<stdlib.h\>|  
|`_ismbslead_l`|\<mbctype.h\> oder \<mbstring.h\>|\<ctype.h\>,\* \<limits.h\>, \<stdlib.h\>|  
|`_ismbstrail_l`|\<mbctype.h\> oder \<mbstring.h\>|\<ctype.h\>,\* \<limits.h\>, \<stdlib.h\>|  
  
 \* Für Manifestkonstanten für die Testbedingungen.  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Zeichenklassifizierung](../../c-runtime-library/character-classification.md)   
 [\_ismbc\-Routinen](../../c-runtime-library/ismbc-routines.md)   
 [is\- und isw\-Routinen](../../c-runtime-library/is-isw-routines.md)   
 [\_ismbb\-Routinen](../../c-runtime-library/ismbb-routines.md)