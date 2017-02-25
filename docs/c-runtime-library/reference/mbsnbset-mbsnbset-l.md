---
title: "_mbsnbset, _mbsnbset_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mbsnbset"
  - "_mbsnbset_l"
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
  - "mbsnbset"
  - "mbsnbset_l"
  - "_mbsnbset"
  - "_mbsnbset_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_mbsnbset-Funktion"
  - "_mbsnbset_l-Funktion"
  - "_tcsnset-Funktion"
  - "_tcsnset_l-Funktion"
  - "mbsnbset-Funktion"
  - "mbsnbset_l-Funktion"
  - "tcsnset-Funktion"
  - "tcsnset_l-Funktion"
ms.assetid: 8e46ef75-9a56-42d2-a522-a08450c67c19
caps.latest.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 24
---
# _mbsnbset, _mbsnbset_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Legt die ersten `n` Bytes einer Multibyte\-Zeichenfolge auf ein bestimmtes Zeichen fest.  Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [\_mbsnbset\_s, \_mbsnbset\_s\_l](../../c-runtime-library/reference/mbsnbset-s-mbsnbset-s-l.md).  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows\-Runtime ausgeführt werden.  Weitere Informationen finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
unsigned char *_mbsnbset(  
   unsigned char *str,  
   unsigned int c,  
   size_t count   
);  
unsigned char *_mbsnbset_l(  
   unsigned char *str,  
   unsigned int c,  
   size_t count,  
   _locale_t locale  
);  
```  
  
#### Parameter  
 `str`  
 Zu ändernde Zeichenfolge.  
  
 `c`  
 Einzelbyte\- oder Multibytezeicheneinstellung.  
  
 `count`  
 Zahl der festzulegenden Bytes.  
  
 `locale`  
 Zu verwendendes Gebietsschema.  
  
## Rückgabewert  
 `_mbsnbset` gibt einen Zeiger auf die geänderte Zeichenfolge zurück.  
  
## Hinweise  
 Die Funktionen `_mbsnbset` und `_mbsnbset_l` legen höchstens die ersten `count` Bytes von `str` auf `c` fest.  Wenn `count` größer als die Länge von `str` ist, wird die Länge von `str` anstelle von `count` verwendet.  Wenn `c` ein Multibytezeichen ist und nicht vollständig auf das von `count` angegebene letzte Byte festgelegt werden kann, dann wird das letzte Byte mit einem Leerzeichen aufgefüllt.  `_mbsnbset` und `_mbsnbset_l` abgelegt ein abschließendes NULL\-Zeichen nicht am Ende von `str`.  
  
 `_mbsnbset` und `_mbsnbset_l` ähnelt `_mbsnset`, allerdings wird legt `count` Bytes statt `count` Zeichen von `c` fest.  
  
 Wenn `str``NULL` oder `count` Null ist, generiert diese Funktion eine Ausnahme wegen eines ungültigen Parameters, wie in[Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, wird `errno` auf `EINVAL` gesetzt, und die Funktion gibt `NULL` zurück.  Wenn `c` kein gültiges Multibytezeichen ist, wird `errno` auf `EINVAL` festgelegt und ein Leerzeichen wird stattdessen verwendet.  
  
 Der Ausgabewert ist von der `LC_CTYPE`\-Kategorieneinstellung des Gebietsschemas betroffen; weitere Informationen finden Sie unter [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).  Die `_mbsnbset`\-Version dieser Funktion verwendet das aktuelle Gebietsschema für dieses vom Gebietsschema abhängige Verhalten. Die `_mbsnbset_l`\-Version ist beinahe identisch, verwendet jedoch stattdessen den ihr übergebenen Gebietsschemaparameter.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
 **Sicherheitshinweis** Diese API stellt eine mögliche Bedrohung aufgrund eines Pufferüberlaufproblems dar.  Pufferüberlaufprobleme werden häufig bei Systemangriffen eingesetzt, da sie zu einer unbefugten Ausweitung der Berechtigungen führen.  Weitere Informationen finden Sie unter [Vermeiden von Pufferüberläufen](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
### Zuordnung generischer Textroutinen  
  
|Tchar.h\-Routine|\_UNICODE und \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|------------------------------------------|----------------------|-------------------------|  
|`_tcsnset`|`_strnset`|`_mbsnbset`|`_wcsnset`|  
|`_tcsnset_l`|`_strnset_l`|`_mbsnbset_l`|`_wcsnset_l`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_mbsnbset`|\<mbstring.h\>|  
|`_mbsnbset_l`|\<mbstring.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
  
```  
// crt_mbsnbset.c  
// compile with: /W3  
#include <mbstring.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char string[15] = "This is a test";  
   /* Set not more than 4 bytes of string to be *'s */  
   printf( "Before: %s\n", string );  
   _mbsnbset( string, '*', 4 ); // C4996  
   // Note; _mbsnbset is deprecated; consider _mbsnbset_s  
   printf( "After:  %s\n", string );  
}  
```  
  
## Ausgabe  
  
```  
Before: This is a test  
After:  **** is a test  
```  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)   
 [\_mbsnbcat, \_mbsnbcat\_l](../../c-runtime-library/reference/mbsnbcat-mbsnbcat-l.md)   
 [\_strnset, \_strnset\_l, \_wcsnset, \_wcsnset\_l, \_mbsnset, \_mbsnset\_l](../../c-runtime-library/reference/strnset-strnset-l-wcsnset-wcsnset-l-mbsnset-mbsnset-l.md)   
 [\_strset, \_strset\_l, \_wcsset, \_wcsset\_l, \_mbsset, \_mbsset\_l](../../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)