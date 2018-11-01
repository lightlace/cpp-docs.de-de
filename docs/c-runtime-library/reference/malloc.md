---
title: malloc
ms.date: 11/04/2016
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
helpviewer_keywords:
- malloc function
- memory allocation
ms.assetid: 144fcee2-be34-4a03-bb7e-ed6d4b99eea0
ms.openlocfilehash: e6a007fb6f089ebf1c9f5fc9ce59cbcbf0b13888
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50520366"
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

**"malloc"** gibt einen void-Zeiger auf den zugeordneten Speicherplatz oder **NULL** ist nicht genügend Arbeitsspeicher verfügbar. Um einen Zeiger auf einen Typ zurückzugeben, anders als **"void"**, verwenden Sie eine Typumwandlung für den Rückgabewert. Es ist sichergestellt, dass der Speicherplatz, auf den der Rückgabewert zeigt, passend für einen Speicher von einem beliebigen Objekttyp ist, dessen Ausrichtungsanforderungen kleiner oder gleich der grundlegenden Ausrichtung sind. (In Visual C++ ist die grundlegende Ausrichtung die Ausrichtung, die benötigt wird, ist eine **doppelte**, oder 8 Bytes. In einem Code, der auf 64-Bit-Plattformen ausgerichtet ist, sind es 16 Bytes.) Verwendung [_aligned_malloc](aligned-malloc.md) um Speicher für Objekte zu belegen, die einen höheren ausrichtungsanforderungen – beispielsweise die SSE-Typen [__m128](../../cpp/m128.md) und **__m256**, und Typen deklariert, indem `__declspec(align( n ))` , in denen **n** ist größer als 8. Wenn *Größe* ist 0 (null) **Malloc** ordnet ein Element der Länge 0 (null) im Heap zu und gibt einen gültigen Zeiger auf das Element. Überprüfen Sie immer die Rückgabe von **Malloc**, auch wenn der angeforderte Speicherplatz klein ist.

## <a name="remarks"></a>Hinweise

Die **Malloc** Funktion weist einen Speicherblock von mindestens *Größe* Bytes. Der Block kann größer sein als *Größe* Bytes aufgrund des Platzes, der Informationen zu Ausrichtung und die Wartung erforderlich ist.

**"malloc"** legt **Errno** zu **ENOMEM** , wenn eine speicherbelegung fehlschlägt oder gegebenenfalls die Größe des Arbeitsspeichers übersteigt **_HEAP_MAXREQ**. Informationen hierzu und über andere Fehlercodes finden Sie unter [errno, _doserrno, _sys_errlist and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Der Startcode verwendet **Malloc** zur speicherzuweisung für die **_environ**, *Envp*, und *Argv* Variablen. Rufen Sie die folgenden Funktionen und ihre breitzeichenentsprechungen auch **Malloc**.

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

Die C++-Funktion [_set_new_mode](set-new-mode.md) legt den neuen Handlermodus für **malloc** fest. Der neue handlermodus gibt an, ob bei einem Fehler **Malloc** besteht darin, rufen Sie die neue Handlerroutine mit [_set_new_handler](set-new-handler.md). In der Standardeinstellung **Malloc** Ruft die neue Handlerroutine nicht bei einem Fehler, um Speicher zu belegen. Sie können dieses Standardverhalten überschreiben, damit, wenn **"malloc"** ein Fehler auftritt, bei der speicherbelegung **"malloc"** die neue Handlerroutine aufruft, in der gleichen Weise wie die **neue** Operator ist Wenn dieser aus demselben Grund fehlschlägt. Um die Standardeinstellung zu überschreiben, rufen `_set_new_mode(1)` rechtzeitig im Programm auf oder mit NEWMODE verknüpfen. OBJ (finden Sie unter [Linkoptionen](../../c-runtime-library/link-options.md)).

Wenn die Anwendung mit einer Debugversion der C-Laufzeitbibliotheken verknüpft ist **Malloc** löst in [_malloc_dbg](malloc-dbg.md). Weitere Informationen dazu, wie der Heap während des Debugprozesses verwaltet wird, finden Sie unter [Details zum CRT-Debugheap](/visualstudio/debugger/crt-debug-heap-details).

**"malloc"** RuntimeCompatibility `__declspec(noalias)` und `__declspec(restrict)`; Dies bedeutet, dass die Funktion nicht, so ändern Sie globale Variablen definitiv, und dass der zurückgegebene Zeiger keinen Alias hat. Weitere Informationen finden Sie unter [noalias](../../cpp/noalias.md) und [restrict](../../cpp/restrict.md).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
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
