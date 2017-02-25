---
title: "_strdup, _wcsdup, _mbsdup | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_strdup"
  - "_mbsdup"
  - "_wcsdup"
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
  - "api-ms-win-crt-string-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_tcsdup"
  - "mbsdup"
  - "_mbsdup"
  - "_strdup"
  - "_ftcsdup"
  - "_wcsdup"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "wcsdup-Funktion"
  - "ftcsdup-Funktion"
  - "_ftcsdup-Funktion"
  - "mbsdup-Funktion"
  - "strdup-Funktion"
  - "_strdup-Funktion"
  - "_wcsdup-Funktion"
  - "Kopieren von Zeichenfolgen"
  - "Verdoppeln von Zeichenfolgen"
  - "Zeichenfolgen [C++], kopieren"
  - "_mbsdup-Funktion"
  - "Zeichenfolgen [C++], duplizieren"
  - "tcsdup-Funktion"
  - "_tcsdup-Funktion"
ms.assetid: 8604f8bb-95e9-45d3-93ef-20397ebf247a
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# _strdup, _wcsdup, _mbsdup
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dupliziert Zeichenfolgen.  
  
> [!IMPORTANT]
>  `_mbsdup` kann in Anwendungen nicht verwendet werden, die im [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausgeführt werden. Weitere Informationen finden Sie unter [In \/ZW nicht unterstützte CRT\-Funktionen](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
char *_strdup(  
   const char *strSource   
);  
wchar_t *_wcsdup(  
   const wchar_t *strSource   
);  
unsigned char *_mbsdup(  
   const unsigned char *strSource   
);  
```  
  
#### Parameter  
 `strSource`  
 Mit NULL endende Quellzeichenfolge.  
  
## Rückgabewert  
 Jede dieser Funktionen gibt einen Zeiger auf den Speicherort für die kopierte Zeichenfolge oder `NULL` zurück, wenn der Speicher nicht belegt werden kann.  
  
## Hinweise  
 Die `_strdup`\-Funktion ruft [malloc](../../c-runtime-library/reference/malloc.md) auf, um einer Kopie von `strSource` Speicherplatz zuzuweisen, und kopiert dann `strSource` in den zugewiesenen Platz.  
  
 `_wcsdup` und `_mbsdup` sind Breitzeichen\- und Multibytezeichenversionen von `_strdup`. Die Argumente und der Rückgabewert von `_wcsdup` sind Breitzeichen\-Zeichenfolgen; die von `_mbsdup` sind Mehrbyte\-Zeichenfolgen. Diese drei Funktionen verhalten sich andernfalls identisch.  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE und \_MBCS nicht definiert.|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|-------------------------------------------|----------------------|-------------------------|  
|`_tcsdup`|`_strdup`|`_mbsdup`|`_wcsdup`|  
  
 Da `_strdup``malloc` aufruft, um der Kopie von `strSource` Speicherplatz zuzuweisen, wird empfohlen, diesen Speicher durch Aufrufen der [free](../../c-runtime-library/reference/free.md)\-Routine für den durch den Aufruf von `_strdup` zurückgegebenen Zeiger freizugeben.  
  
 Wenn `_DEBUG` und `_CRTDBG_MAP_ALLOC` definiert sind, werden `_strdup` und `_wcsdup` durch Aufrufe von `_strdup_dbg` und `_wcsdup_dbg` ersetzt, um das Debuggen von Speicherbelegungen zuzulassen. Weitere Informationen finden Sie unter [\_strdup\_dbg, \_wcsdup\_dbg](../../c-runtime-library/reference/strdup-dbg-wcsdup-dbg.md).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_strdup`|\<string.h\>|  
|`_wcsdup`|\<string.h\> oder \<wchar.h\>|  
|`_mbsdup`|\<mbstring.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
  
```  
// crt_strdup.c  
  
#include <string.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char buffer[] = "This is the buffer text";  
   char *newstring;  
   printf( "Original: %s\n", buffer );  
   newstring = _strdup( buffer );  
   printf( "Copy:     %s\n", newstring );  
   free( newstring );  
}  
```  
  
```Output  
Original: Dies ist der Puffertext Kopie:     Dies ist der Puffertext  
```  
  
## .NET Framework-Entsprechung  
 [System::String::Clone](https://msdn.microsoft.com/en-us/library/system.string.clone.aspx)  
  
## Siehe auch  
 [Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)   
 [memset, wmemset](../../c-runtime-library/reference/memset-wmemset.md)   
 [strcat, wcscat, \_mbscat](../../c-runtime-library/reference/strcat-wcscat-mbscat.md)   
 [strcmp, wcscmp, \_mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [strncat, \_strncat\_l, wcsncat, \_wcsncat\_l, \_mbsncat, \_mbsncat\_l](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)   
 [strncmp, wcsncmp, \_mbsncmp, \_mbsncmp\_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [strncpy, \_strncpy\_l, wcsncpy, \_wcsncpy\_l, \_mbsncpy, \_mbsncpy\_l](../../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)   
 [\_strnicmp, \_wcsnicmp, \_mbsnicmp, \_strnicmp\_l, \_wcsnicmp\_l, \_mbsnicmp\_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strrchr, wcsrchr, \_mbsrchr, \_mbsrchr\_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [strspn, wcsspn, \_mbsspn, \_mbsspn\_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)