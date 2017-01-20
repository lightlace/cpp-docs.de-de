---
title: "_mbsnbset_s, _mbsnbset_s_l"
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
  - "_mbsnbset_s_l"
  - "_mbsnbset_s"
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
  - "mbsnbset_s"
  - "_mbsnbset_s_l"
  - "_mbsnbset_s"
  - "mbsnbset_s_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mbsnbset_s-Funktion"
  - "_mbsnbset_s_l-Funktion"
  - "_tcsnset_s-Funktion"
  - "_tcsnset_s_l-Funktion"
  - "mbsnbset_s-Funktion"
  - "mbsnbset_s_l-Funktion"
  - "tcsnset_s-Funktion"
  - "tcsnset_s_l-Funktion"
ms.assetid: 811f92c9-cc31-4bbd-8017-2d1bfc6fb96f
caps.latest.revision: 21
caps.handback.revision: "19"
ms.author: "corob"
manager: "ghogen"
---
# _mbsnbset_s, _mbsnbset_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Legt die ersten `n` Bytes einer Multibyte\-Zeichenfolge auf ein bestimmtes Zeichen fest.  Diese Versionen von [\_mbsnbset, \_mbsnbset\_l](../../c-runtime-library/reference/mbsnbset-mbsnbset-l.md) enthalten Sicherheitserweiterungen wie unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die im [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausgeführt werden.  Weitere Informationen finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
errno_t _mbsnbset_s(  
   unsigned char *str,  
   size_t size,  
   unsigned int c,  
   size_t count   
);  
errno_t _mbsnbset_s_l(  
   unsigned char *str,  
   size_t size,  
   unsigned int c,  
   size_t count,  
   _locale_t locale  
);  
template <size_t size>  
errno_t _mbsnbset_s(  
   unsigned char (&str)[size],  
   unsigned int c,  
   size_t count   
); // C++ only  
template <size_t size>  
errno_t _mbsnbset_s_l(  
   unsigned char (&str)[size],  
   unsigned int c,  
   size_t count,  
   _locale_t locale  
); // C++ only  
```  
  
#### Parameter  
 `str`  
 Zu ändernde Zeichenfolge.  
  
 `size`  
 Die Größe des Zeichenfolgenpuffers.  
  
 `c`  
 Einzelbyte\- oder Multibytezeicheneinstellung.  
  
 `count`  
 Zahl der festzulegenden Bytes.  
  
 `locale`  
 Zu verwendendes Gebietsschema.  
  
## Rückgabewert  
 Null, wenn erfolgreich, andernfalls ein Fehlercode.  
  
## Hinweise  
 Die Funktionen `_mbsnbset_s` und `_mbsnbset_s_l` legen höchstens die ersten `count` Bytes von `str` auf `c` fest.  Wenn `count` größer als die Länge von `str` ist, wird die Länge von `str` anstelle von `count` verwendet.  Wenn `c` ein Multibytezeichen ist und nicht vollständig auf das von `count` angegebene letzte Byte festgelegt werden kann, dann wird das letzte Byte mit einem Leerzeichen aufgefüllt.  `_mbsnbset_s` und `_mbsnbset_s_l` platzieren am Ende von `str` kein abschließendes NULL\-Zeichen.  
  
 `_mbsnbset_s` und `_mbsnbset_s_l` ähneln `_mbsnset` mit der Ausnahme, dass sie `count`\-Bytes statt `count`\-Zeichen von `c` festlegen.  
  
 Wenn `str``NULL` oder `count` Null ist, generiert diese Funktion eine Ausnahme wegen eines ungültigen Parameters, wie in[Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, wird `errno` auf `EINVAL` gesetzt, und die Funktion gibt `NULL` zurück.  Wenn `c` kein gültiges Multibytezeichen ist, wird `errno` auf `EINVAL` festgelegt und ein Leerzeichen wird stattdessen verwendet.  
  
 Der Ausgabewert ist von der `LC_CTYPE`\-Kategorieneinstellung des Gebietsschemas betroffen; weitere Informationen finden Sie unter [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).  Die `_mbsnbset_s`\-Version dieser Funktion verwendet das aktuelle Gebietsschema auf dieses vom Gebietsschema abhängige Verhalten. Die `_mbsnbset_s_l`\-Version ist beinahe identisch, abgesehen davon, dass es stattdessen den ihr übergebenen Gebietsschemaparameter verwendet.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
 Die Verwendung dieser Funktionen in C\+\+ wird durch Vorlagenüberladungen vereinfacht. Überladungen können automatisch die Pufferlänge ableiten, sodass kein Größenargument angegeben werden muss.  Weitere Informationen finden Sie unter [Sichere Vorlagenüberladungen](../../c-runtime-library/secure-template-overloads.md).  
  
 Die Debugversionen dieser Funktionen füllen zunächst den Puffer mit "0xFD" auf.  Um dieses Verhalten zu deaktivieren, verwenden Sie [\_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md).  
  
### Zuordnung generischer Textroutinen  
  
|Tchar.h\-Routine|\_UNICODE und \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|------------------------------------------|----------------------|-------------------------|  
|`_tcsnset_s`|`_strnset_s`|`_mbsnbset_s`|`_wcsnset_s`|  
|`_tcsnset_s_l`|`_strnset_s _l`|`_mbsnbset_s_l`|`_wcsnset_s_l`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_mbsnbset_s`|\<mbstring.h\>|  
|`_mbsnbset_s_l`|\<mbstring.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
  
```  
// crt_mbsnbset_s.c  
#include <mbstring.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char string[15] = "This is a test";  
   /* Set not more than 4 bytes of string to be *'s */  
   printf( "Before: %s\n", string );  
   _mbsnbset_s( string, sizeof(string), '*', 4 );  
   printf( "After:  %s\n", string );  
}  
```  
  
## Ausgabe  
  **Vorher: Dies ist ein Test**  
**Nachher: \*\*\*\* ist ein Test**   
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)   
 [\_mbsnbcat, \_mbsnbcat\_l](../../c-runtime-library/reference/mbsnbcat-mbsnbcat-l.md)   
 [\_strnset, \_strnset\_l, \_wcsnset, \_wcsnset\_l, \_mbsnset, \_mbsnset\_l](../../c-runtime-library/reference/strnset-strnset-l-wcsnset-wcsnset-l-mbsnset-mbsnset-l.md)   
 [\_strset, \_strset\_l, \_wcsset, \_wcsset\_l, \_mbsset, \_mbsset\_l](../../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)