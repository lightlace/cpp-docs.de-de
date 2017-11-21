---
title: memchr, wmemchr | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- wmemchr
- memchr
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- memchr
- wmemchr
dev_langs: C++
helpviewer_keywords:
- memchr function
- wmemchr function
ms.assetid: 5a348581-28f1-4256-8434-687245f7fc9f
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: dd7a16cb35257104b79d0347fe415c5b17cd4bb4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="memchr-wmemchr"></a>memchr, wmemchr
Suchen nach Zeichen in einem Puffer.  
  
## <a name="syntax"></a>Syntax  
  
```  
void *memchr(  
   const void *buf,  
   int c,  
   size_t count  
); // C only  
void *memchr(  
   void *buf,  
   int c,  
   size_t count  
); // C++ only  
const void *memchr(  
   const void *buf,  
   int c,  
   size_t count  
); // C++ only  
wchar_t *wmemchr(  
   const wchar_t * buf,   
   wchar_t c,  
   size_t count  
); // C only  
wchar_t *wmemchr(  
   wchar_t * buf,   
   wchar_t c,  
   size_t count  
); // C++ only  
const wchar_t *wmemchr(  
   const wchar_t * buf,   
   wchar_t c,  
   size_t count  
); // C++ only  
```  
  
#### <a name="parameters"></a>Parameter  
 `buf`  
 Ein Zeiger auf einen Puffer.  
  
 `c`  
 Zu suchendes Zeichen.  
  
 `count`  
 Anzahl der zu prüfenden Zeichen.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg einen Zeiger auf die erste Position von `c` in `buf` zurück. Andernfalls wird `NULL` zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 `memchr` und `wmemchr` suchen nach dem ersten Vorkommen von `c` in den ersten `count`-Bytes von `buf`. Es hält an, wenn es `c` findet, oder wenn es die ersten `count`-Bytes geprüft hat.  
  
 In C akzeptieren diese Funktionen einen `const`-Zeiger als erstes Argument. In C++ sind zwei Überladungen verfügbar. Die Überladung, die einen Zeiger zu `const` akzeptiert, gibt einen Zeiger zu `const` zurück; die Version, die einen Zeiger auf Nicht-`const` akzeptiert, gibt einen Zeiger auf Nicht-`const` zurück. Das Makro _CRT_CONST_CORRECT_OVERLOADS wird definiert, wenn sowohl die `const` und nicht-`const` Versionen dieser Funktionen sind verfügbar. Wenn Sie das Nicht-`const`-Verhalten für beide C++-Überladungen in C++ benötigen, definieren Sie das Symbol _CONST_RETURN.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`memchr`|\<memory.h> oder \<string.h>|  
|`wmemchr`|\<wchar.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Bibliotheken  
 Alle Versionen der [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_memchr.c  
  
#include <memory.h>  
#include <stdio.h>  
  
int  ch = 'r';  
char str[] =    "lazy";  
char string[] = "The quick brown dog jumps over the lazy fox";  
char fmt1[] =   "         1         2         3         4         5";  
char fmt2[] =   "12345678901234567890123456789012345678901234567890";  
  
int main( void )  
{  
   char *pdest;  
   int result;  
   printf( "String to be searched:\n             %s\n", string );  
   printf( "             %s\n             %s\n\n", fmt1, fmt2 );  
  
   printf( "Search char: %c\n", ch );  
   pdest = memchr( string, ch, sizeof( string ) );  
   result = (int)(pdest - string + 1);  
   if ( pdest != NULL )  
      printf( "Result:      %c found at position %d\n", ch, result );  
   else  
      printf( "Result:      %c not found\n" );  
}  
```  
  
## <a name="output"></a>Ausgabe  
  
```  
String to be searched:  
             The quick brown dog jumps over the lazy fox  
                      1         2         3         4         5  
             12345678901234567890123456789012345678901234567890  
  
Search char: r  
Result:      r found at position 12  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Pufferbearbeitung](../../c-runtime-library/buffer-manipulation.md)   
 [_memccpy](../../c-runtime-library/reference/memccpy.md)   
 [memcmp, wmemcmp](../../c-runtime-library/reference/memcmp-wmemcmp.md)   
 [memcpy, wmemcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md)   
 [memset, wmemset](../../c-runtime-library/reference/memset-wmemset.md)   
 [strchr, wcschr, _mbschr, _mbschr_l](../../c-runtime-library/reference/strchr-wcschr-mbschr-mbschr-l.md)