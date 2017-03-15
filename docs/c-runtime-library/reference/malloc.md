---
title: malloc | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- malloc
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
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- malloc
dev_langs:
- C++
helpviewer_keywords:
- malloc function
- memory allocation
ms.assetid: 144fcee2-be34-4a03-bb7e-ed6d4b99eea0
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: f259e869535e00bf0dd4f18e6a4d8d02e4054685
ms.lasthandoff: 02/24/2017

---
# <a name="malloc"></a>malloc
Weist Speicherblöcke zu.  
  
## <a name="syntax"></a>Syntax  
  
```  
void *malloc(  
   size_t size   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `size`  
 Zuzuordnende Bytes.  
  
## <a name="return-value"></a>Rückgabewert  
 `malloc` gibt einen void-Zeiger auf den zugeordneten Speicherplatz oder `NULL` zurück, wenn nicht genügend Speicher verfügbar ist. Um einen Zeiger auf einen anderen Typ als `void` zurückzugeben, verwenden Sie eine Typumwandlung für den Rückgabewert. Es ist sichergestellt, dass der Speicherplatz, auf den der Rückgabewert zeigt, passend für einen Speicher von einem beliebigen Objekttyp ist, dessen Ausrichtungsanforderungen kleiner oder gleich der grundlegenden Ausrichtung sind. (In Visual C++ ist die grundlegende Ausrichtung die Ausrichtung, die für `double` oder 8 Bytes erforderlich ist. In einem Code, der auf 64-Bit-Plattformen ausgerichtet ist, sind es 16 Bytes.) Verwenden Sie [_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md), um Speicher für Objekte mit höheren Ausrichtungsanforderungen zuzuordnen, beispielsweise die SSE-Typen [__m128](../../cpp/m128.md) und `__m256` und Typen, die durch das Verwenden von `__declspec(align(``n``))` deklariert werden, wobei `n` größer ist als 8. Wenn `size` 0 ist, weist `malloc` ein Element der Länge 0 im Heap zu und gibt einen gültigen Zeiger auf dieses Element zurück. Überprüfen Sie immer die Rückgabe von `malloc`, auch wenn der angeforderte Speicherplatz klein ist.  
  
## <a name="remarks"></a>Hinweise  
 Die `malloc`-Funktion weist einen Speicherblock von mindestens `size` Bytes zu. Der Block kann aufgrund des Platzes, der für die Ausrichtung und die Wartungsinformationen benötigt wird, größer sein als `size` Bytes.  
  
 `malloc` setzt `errno` auf `ENOMEM`, wenn eine Speicherbelegung fehlschlägt oder wenn der benötigte Speicherplatz größer ist als `_HEAP_MAXREQ`. Informationen hierzu und über andere Fehlercodes finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Der Startcode verwendet `malloc`, um Speicher für die `_environ`-, `envp`- und `argv`-Variablen zuzuordnen. Die folgenden Funktionen und ihre Breitzeichenentsprechungen rufen auch `malloc` auf.  
  
|||||  
|-|-|-|-|  
|[calloc](../../c-runtime-library/reference/calloc.md)|[fscanf](../../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md)|[_getw](../../c-runtime-library/reference/getw.md)|[setvbuf](../../c-runtime-library/reference/setvbuf.md)|  
|[_exec functions](../../c-runtime-library/exec-wexec-functions.md)|[fseek](../../c-runtime-library/reference/fseek-fseeki64.md)|[_popen](../../c-runtime-library/reference/popen-wpopen.md)|[_spawn functions](../../c-runtime-library/spawn-wspawn-functions.md)|  
|[fgetc](../../c-runtime-library/reference/fgetc-fgetwc.md)|[fsetpos](../../c-runtime-library/reference/fsetpos.md)|[printf](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)|[_strdup](../../c-runtime-library/reference/strdup-wcsdup-mbsdup.md)|  
|[_fgetchar](../../c-runtime-library/reference/fgetc-fgetwc.md)|[_fullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)|[putc](../../c-runtime-library/reference/putc-putwc.md)|[system](../../c-runtime-library/reference/system-wsystem.md)|  
|[fgets](../../c-runtime-library/reference/fgets-fgetws.md)|[fwrite](../../c-runtime-library/reference/fwrite.md)|[putchar](../../c-runtime-library/reference/putc-putwc.md)|[_tempnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)|  
|[fprintf](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)|[getc](../../c-runtime-library/reference/getc-getwc.md)|[_putenv](../../c-runtime-library/reference/putenv-wputenv.md)|[ungetc](../../c-runtime-library/reference/ungetc-ungetwc.md)|  
|[fputc](../../c-runtime-library/reference/fputc-fputwc.md)|[getchar](../../c-runtime-library/reference/getc-getwc.md)|[puts](../../c-runtime-library/reference/puts-putws.md)|[vfprintf](../../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)|  
|[_fputchar](../../c-runtime-library/reference/fputc-fputwc.md)|[_getcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md)|[_putw](../../c-runtime-library/reference/putw.md)|[vprintf](../../c-runtime-library/reference/vprintf-vprintf-l-vwprintf-vwprintf-l.md)|  
|[fputs](../../c-runtime-library/reference/fputs-fputws.md)|[_getdcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md)|[scanf](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)||  
|[fread](../../c-runtime-library/reference/fread.md)|[gets](../../c-runtime-library/gets-getws.md)|[_searchenv](../../c-runtime-library/reference/searchenv-wsearchenv.md)||  
  
 Die [_set_new_mode](../../c-runtime-library/reference/set-new-mode.md)-Funktion von C++ legt den neuen Handlermodus für `malloc` fest. Der neue Handlermodus gibt an, ob bei einem Fehler `malloc` die neue Handlerroutine aufgerufen werden soll, wie dies von [_set_new_handler](../../c-runtime-library/reference/set-new-handler.md) festgelegt ist. Standardmäßig ruft `malloc` bei einem Speicherbelegungsfehler nicht die neue Handlerroutine auf. Sie können dieses Standardverhalten überschreiben, sodass, wenn `malloc` Speicher nicht belegen kann,`malloc` die neue Handlerroutine genauso aufruft wie der `new`-Operator, wenn dieser aus demselben Grund fehlschlägt. Um die Standardeinstellung zu überschreiben, rufen `_set_new_mode(1)` am Anfang Ihrer Anwendung oder eine Verknüpfung mit NEWMODE. OBJ (finden Sie unter [Verknüpfungsoptionen](../../c-runtime-library/link-options.md)).  
  
 Wenn die Anwendung mit einer Debugversion der C-Laufzeitbibliotheken verknüpft ist, wird `malloc` in [_malloc_dbg](../../c-runtime-library/reference/malloc-dbg.md) aufgelöst. Weitere Informationen dazu, wie der Heap während des Debugprozesses verwaltet wird, finden Sie unter [Details zum CRT-Debugheap](/visualstudio/debugger/crt-debug-heap-details).  
  
 `malloc` ist als `__declspec(noalias)` und `__declspec(restrict)` gekennzeichnet, das bedeutet, dass die Funktion globale Variablen definitiv nicht ändert und dass der zurückgegebene Zeiger keinen Alias hat. Weitere Informationen finden Sie unter [noalias](../../cpp/noalias.md) und [restrict](../../cpp/restrict.md).  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`malloc`|\<stdlib.h> und \<malloc.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Bibliotheken  
 Alle Versionen der [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Beispiel  
  
```C  
// crt_malloc.c  
// This program allocates memory with  
// malloc, then frees the memory with free.  
  
#include <stdlib.h>   // For _MAX_PATH definition  
#include <stdio.h>  
#include <malloc.h>  
  
int main( void )  
{  
   char *string;  
  
   // Allocate space for a path name  
   string = malloc( _MAX_PATH );  
  
   // In a C++ file, explicitly cast malloc's return.  For example,   
   // string = (char *)malloc( _MAX_PATH );  
  
   if( string == NULL )  
      printf( "Insufficient memory available\n" );  
   else  
   {  
      printf( "Memory space allocated for path name\n" );  
      free( string );  
      printf( "Memory freed\n" );  
   }  
}  
```  
  
```Output  
Memory space allocated for path name  
Memory freed  
```  
  
## <a name="net-framework-equivalent"></a>Entsprechung in .NET Framework  
 Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Siehe auch  
 [Speicherbelegung](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md)

