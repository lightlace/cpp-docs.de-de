---
title: malloc | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f600deb7bfa9b65ed9bdf784f2a16bd037729a51
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="malloc"></a>malloc

Weist Speicherblöcke zu.

## <a name="syntax"></a>Syntax

```C
void *malloc(
   size_t size
);
```

### <a name="parameters"></a>Parameter

*size*<br/>
Zuzuordnende Bytes.

## <a name="return-value"></a>Rückgabewert

**"malloc"** gibt einen void-Zeiger auf den zugeordneten Speicherplatz oder **NULL** Wenn nicht genügend Arbeitsspeicher verfügbar ist. Einen Zeiger auf einen Typ zurückgegeben, außer **"void"**, verwenden Sie eine Typumwandlung für den Rückgabewert. Es ist sichergestellt, dass der Speicherplatz, auf den der Rückgabewert zeigt, passend für einen Speicher von einem beliebigen Objekttyp ist, dessen Ausrichtungsanforderungen kleiner oder gleich der grundlegenden Ausrichtung sind. (In Visual C++ wird die grundlegende Ausrichtung die Ausrichtung, das erforderlich ist eine **doppelte**, oder 8 Bytes. In einem Code, der auf 64-Bit-Plattformen ausgerichtet ist, sind es 16 Bytes.) Verwendung [_aligned_malloc](aligned-malloc.md) beim Zuweisen von Speicher für Objekte, die einen größeren ausrichtungsanforderung haben – z. B. die SSE-Typen [__m128](../../cpp/m128.md) und **__m256**, und Typen deklariert, indem `__declspec(align( n ))` , in denen **n** ist größer als 8. Wenn *Größe* ist 0, **"malloc"** ein Element der Länge 0 im Heap belegt und gibt einen gültigen Zeiger auf dieses Element zurück. Überprüfen Sie immer die Rückgabe von **"malloc"**, selbst wenn die Größe des angeforderten Arbeitsspeichers klein ist.

## <a name="remarks"></a>Hinweise

Die **"malloc"** Funktion weist einen Speicherblock von mindestens *Größe* Bytes. Der Block kann größer sein als *Größe* Bytes aufgrund der Speicherplatz für die Ausrichtung und die Wartungsinformationen benötigt.

**"malloc"** legt **Errno** auf **ENOMEM** , wenn eine speicherbelegung fehlschlägt oder wenn die Größe des Arbeitsspeichers größer ist als **_HEAP_MAXREQ**. Informationen hierzu und über andere Fehlercodes finden Sie unter [errno, _doserrno, _sys_errlist and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Der Startcode verwendet **"malloc"** beim Zuweisen von Speicher für die **_environ**, *Envp*, und *Argv* Variablen. Rufen Sie die folgenden Funktionen und ihre breitzeichenentsprechungen auch **"malloc"**.

|||||
|-|-|-|-|
|[calloc](calloc.md)|[fscanf](fscanf-fscanf-l-fwscanf-fwscanf-l.md)|[_getw](getw.md)|[setvbuf](setvbuf.md)|
|[_exec functions](../../c-runtime-library/exec-wexec-functions.md)|[fseek](fseek-fseeki64.md)|[_popen](popen-wpopen.md)|[_spawn functions](../../c-runtime-library/spawn-wspawn-functions.md)|
|[fgetc](fgetc-fgetwc.md)|[fsetpos](fsetpos.md)|[printf](printf-printf-l-wprintf-wprintf-l.md)|[_strdup](strdup-wcsdup-mbsdup.md)|
|[_fgetchar](fgetc-fgetwc.md)|[_fullpath](fullpath-wfullpath.md)|[putc](putc-putwc.md)|[system](system-wsystem.md)|
|[fgets](fgets-fgetws.md)|[fwrite](fwrite.md)|[putchar](putc-putwc.md)|[_tempnam](tempnam-wtempnam-tmpnam-wtmpnam.md)|
|[fprintf](fprintf-fprintf-l-fwprintf-fwprintf-l.md)|[getc](getc-getwc.md)|[_putenv](putenv-wputenv.md)|[ungetc](ungetc-ungetwc.md)|
|[fputc](fputc-fputwc.md)|[getchar](getc-getwc.md)|[puts](puts-putws.md)|[vfprintf](vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)|
|[_fputchar](fputc-fputwc.md)|[_getcwd](getcwd-wgetcwd.md)|[_putw](putw.md)|[vprintf](vprintf-vprintf-l-vwprintf-vwprintf-l.md)|
|[fputs](fputs-fputws.md)|[_getdcwd](getcwd-wgetcwd.md)|[scanf](scanf-scanf-l-wscanf-wscanf-l.md)||
|[fread](fread.md)|[gets](../../c-runtime-library/gets-getws.md)|[_searchenv](searchenv-wsearchenv.md)||

Die C++-Funktion [_set_new_mode](set-new-mode.md) legt den neuen Handlermodus für **malloc** fest. Der neue handlermodus gibt an, ob bei einem Fehler **"malloc"** ist, rufen Sie die neue Handlerroutine Isolationstransaktionen gemäß [_set_new_handler](set-new-handler.md). Standardmäßig **"malloc"** auf bei einem speicherbelegungsfehler nicht die neue Handlerroutine aufgerufen. Sie können dieses Standardverhalten überschreiben, damit, wenn **"malloc"** Arbeitsspeicher nicht belegen kann **"malloc"** die neue Handlerroutine genauso aufruft wie der **neue** Operator ist. Wenn dieser aus demselben Grund fehlschlägt. Um die Standardeinstellung zu überschreiben, rufen `_set_new_mode(1)` frühen in Ihrer Anwendung oder eine Verknüpfung mit NEWMODE. OBJ (finden Sie unter [Linkoptionen](../../c-runtime-library/link-options.md)).

Wenn die Anwendung mit einer Debugversion der C-Laufzeitbibliotheken verknüpft ist **"malloc"** löst in [_malloc_dbg](malloc-dbg.md). Weitere Informationen dazu, wie der Heap während des Debugprozesses verwaltet wird, finden Sie unter [Details zum CRT-Debugheap](/visualstudio/debugger/crt-debug-heap-details).

**"malloc"** RuntimeCompatibility `__declspec(noalias)` und `__declspec(restrict)`; Dies bedeutet, dass die Funktion wird sichergestellt, dass keine globalen Variablen zu ändern, und dass der zurückgegebene Zeiger nicht als Alias ist. Weitere Informationen finden Sie unter [noalias](../../cpp/noalias.md) und [restrict](../../cpp/restrict.md).

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**malloc**|\<stdlib.h> und \<malloc.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Alle Versionen [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

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

## <a name="see-also"></a>Siehe auch

[Speicherreservierung](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[free](free.md)<br/>
[realloc](realloc.md)<br/>
[_aligned_malloc](aligned-malloc.md)<br/>
