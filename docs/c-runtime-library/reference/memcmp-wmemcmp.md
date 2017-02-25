---
title: "memcmp, wmemcmp | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "memcmp"
  - "wmemcmp"
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
  - "ntdll.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "memcmp"
  - "wmemcmp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "memcmp-Funktion"
  - "wmemcmp-Funktion"
ms.assetid: 0c21c3e3-8ee4-40e5-add1-eb26d225fd8d
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# memcmp, wmemcmp
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vergleicht Zeichen in zwei Puffern.  
  
## Syntax  
  
```  
  
      int memcmp(  
   const void *buf1,  
   const void *buf2,  
   size_t count  
);  
int wmemcmp(  
   const wchar_t * buf1,  
   const wchar_t * buf2,  
   size_t count  
);  
```  
  
#### Parameter  
 `buf1`  
 Erster Puffer.  
  
 `buf2`  
 Zweite Puffer.  
  
 `count`  
 Anzahl der zu vergleichenden Zeichen. \(Vergleicht Bytes für `memcmp`, Breitzeichen für `wmemcmp`\).  
  
## Rückgabewert  
 Der Rückgabewert gibt die Beziehung zwischen den Puffern an.  
  
|Rückgabewert|Beziehung der ersten `count`\-Zeichen von buf1 und buf2|  
|------------------|-------------------------------------------------------------|  
|\< 0|`buf1` kleiner als `buf2`|  
|0|`buf1` identisch mit `buf2`|  
|\> 0|`buf1` größer als `buf2`|  
  
## Hinweise  
 Vergleicht die ersten `count` Zeichen von `buf1` und `buf2` und gibt einen Wert zurück, der die Beziehung angibt.  Das Zeichen eines Rückgabewerts ungleich Null ist das Zeichen des Unterschieds zwischen dem ersten unterschiedlichen Wertpaar in den Puffern.  Die Werte werden als `unsigned char` für `memcmp` und als `wchar_t` für `wmemcmp` interpretiert.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`memcmp`|\<memory.h\> oder \<string.h\>|  
|`wmemcmp`|\<wchar.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Bibliotheken  
 Alle Versionen der [C\-Laufzeitbibliothek](../../c-runtime-library/crt-library-features.md).  
  
## Beispiel  
  
```  
// crt_memcmp.c  
/* This program uses memcmp to compare  
 * the strings named first and second. If the first  
 * 19 bytes of the strings are equal, the program  
 * considers the strings to be equal.  
 */  
  
#include <string.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char first[]  = "12345678901234567890";  
   char second[] = "12345678901234567891";  
   int int_arr1[] = {1,2,3,4};  
   int int_arr2[] = {1,2,3,4};  
   int result;  
  
   printf( "Compare '%.19s' to '%.19s':\n", first, second );  
   result = memcmp( first, second, 19 );  
   if( result < 0 )  
      printf( "First is less than second.\n" );  
   else if( result == 0 )  
      printf( "First is equal to second.\n" );  
   else  
      printf( "First is greater than second.\n" );  
  
   printf( "Compare '%d,%d' to '%d,%d':\n", int_arr1[0], int_arr1[1], int_arr2[0], int_arr2[1]);  
   result = memcmp( int_arr1, int_arr2, sizeof(int) * 2 );  
   if( result < 0 )  
      printf( "int_arr1 is less than int_arr2.\n" );  
   else if( result == 0 )  
      printf( "int_arr1 is equal to int_arr2.\n" );  
   else   
      printf( "int_arr1 is greater than int_arr2.\n" );  
}  
```  
  
## Ausgabe  
  
```  
Compare '1234567890123456789' to '1234567890123456789':  
First is equal to second.  
Compare '1,2' to '1,2':  
int_arr1 is equal to int_arr2.  
```  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Pufferbearbeitung](../../c-runtime-library/buffer-manipulation.md)   
 [\_memccpy](../../c-runtime-library/reference/memccpy.md)   
 [memchr, wmemchr](../../c-runtime-library/reference/memchr-wmemchr.md)   
 [memcpy, wmemcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md)   
 [memset, wmemset](../../c-runtime-library/reference/memset-wmemset.md)   
 [strcmp, wcscmp, \_mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [strncmp, wcsncmp, \_mbsncmp, \_mbsncmp\_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)