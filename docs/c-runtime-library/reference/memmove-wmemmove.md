---
title: "memmove, wmemmove | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "memmove"
  - "wmemmove"
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
  - "memmove"
  - "wmemmove"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "memmove-Funktion"
  - "wmemmove-Funktion"
ms.assetid: 3a906114-9cf3-40d7-bd99-ee452004f218
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# memmove, wmemmove
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wechselt ein Puffer zu anderen.  Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [memmove\_s, wmemmove\_s](../../c-runtime-library/reference/memmove-s-wmemmove-s.md).  
  
## Syntax  
  
```  
void *memmove(  
   void *dest,  
   const void *src,  
   size_t count   
);  
wchar_t *wmemmove(  
   wchar_t *dest,  
   const wchar_t *src,  
   size_t count  
);  
```  
  
#### Parameter  
 `dest`  
 Zielobjekt.  
  
 `src`  
 Quellobjekt.  
  
 `count`  
 Anzahl Bytes \(`memmove`\) oder \(`wmemmove`\) zu kopieren.  
  
## Rückgabewert  
 Der Wert von `dest`*.*  
  
## Hinweise  
 Kopien `count` Bytes \(`memmove`\) oder \(`wmemmove`\) von `src` in `dest`*.* Wenn einige Bereiche des Ursprungsbereichs und des Ziels überschneiden, sicherstellen beide Features, dass die ursprüngliche Quellbytes im überlappenden Bereich kopiert werden, bevor sie überschrieben wird.  
  
 **Sicherheitshinweis**  Überprüfen, ob der Zielpuffer die gleiche Größe oder das größer als Quellpuffer ist.  Weitere Informationen finden Sie unter [Vermeiden von Pufferüberläufen](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
 Die Funktionen `memmove` und `wmemmove` werden nur, wenn die Konstante `_CRT_SECURE_DEPRECATE_MEMORY` vor der Inklusionsanweisung definiert wird, damit die Funktionen veraltet sein können, wie im nachfolgenden Beispiel veraltet:  
  
```  
#define _CRT_SECURE_DEPRECATE_MEMORY  
#include <string.h>  
or  
#define _CRT_SECURE_DEPRECATE_MEMORY  
#include <wchar.h>  
```  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`memmove`|\<string.h\>|  
|`wmemmove`|\<wchar.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_memcpy.c  
// Illustrate overlapping copy: memmove  
// always handles it correctly; memcpy may handle  
// it correctly.  
//  
  
#include <memory.h>  
#include <string.h>  
#include <stdio.h>  
  
char str1[7] = "aabbcc";  
  
int main( void )  
{  
   printf( "The string: %s\n", str1 );  
   memcpy( str1 + 2, str1, 4 );  
   printf( "New string: %s\n", str1 );  
  
   strcpy_s( str1, sizeof(str1), "aabbcc" );   // reset string  
  
   printf( "The string: %s\n", str1 );  
   memmove( str1 + 2, str1, 4 );  
   printf( "New string: %s\n", str1 );  
}  
```  
  
  **Die Zeichenfolge: aabbcc**  
**Neue Zeichenfolge: aaaabb**  
**Die Zeichenfolge: aabbcc**  
**Neue Zeichenfolge: aaaabb**   
## .NET Framework-Entsprechung  
 [System::Buffer::BlockCopy](https://msdn.microsoft.com/en-us/library/system.buffer.blockcopy.aspx)  
  
## Siehe auch  
 [Pufferbearbeitung](../../c-runtime-library/buffer-manipulation.md)   
 [\_memccpy](../../c-runtime-library/reference/memccpy.md)   
 [memcpy, wmemcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md)   
 [strcpy, wcscpy, \_mbscpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)   
 [strncpy, \_strncpy\_l, wcsncpy, \_wcsncpy\_l, \_mbsncpy, \_mbsncpy\_l](../../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)