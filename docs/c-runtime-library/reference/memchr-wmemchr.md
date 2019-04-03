---
title: memchr, wmemchr
ms.date: 03/31/2019
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
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- memchr
- wmemchr
helpviewer_keywords:
- memchr function
- wmemchr function
ms.assetid: 5a348581-28f1-4256-8434-687245f7fc9f
ms.openlocfilehash: 00a1f0d12047cc388b56074a657ffd739e986827
ms.sourcegitcommit: 489c0b998f2360317701f7a4a97b2b8ad96052d7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58866915"
---
# <a name="memchr-wmemchr"></a>memchr, wmemchr

Suchen nach Zeichen in einem Puffer.

## <a name="syntax"></a>Syntax

```C
void *memchr(
   const void *buffer,
   int c,
   size_t count
); // C only
void *memchr(
   void *buffer,
   int c,
   size_t count
); // C++ only
const void *memchr(
   const void *buffer,
   int c,
   size_t count
); // C++ only
wchar_t *wmemchr(
   const wchar_t * buffer,
   wchar_t c,
   size_t count
); // C only
wchar_t *wmemchr(
   wchar_t * buffer,
   wchar_t c,
   size_t count
); // C++ only
const wchar_t *wmemchr(
   const wchar_t * buffer,
   wchar_t c,
   size_t count
); // C++ only
```

### <a name="parameters"></a>Parameter

*buffer*<br/>
Ein Zeiger auf einen Puffer.

*c*<br/>
Zu suchendes Zeichen.

*count*<br/>
Anzahl der zu prüfenden Zeichen.

## <a name="return-value"></a>Rückgabewert

Wenn erfolgreich, gibt Sie einen Zeiger auf den ersten Speicherort der *c* in *Puffer*. Andernfalls wird NULL zurückgegeben.

## <a name="remarks"></a>Hinweise

`memchr` und `wmemchr` suchen Sie nach dem ersten Vorkommen des *c* in der ersten *Anzahl* Zeichen *Puffer*. Es wird beendet, wenn er findet *c* oder wenn sie die erste aktiviert hat *Anzahl* Zeichen.

In C akzeptieren diese Funktionen eine **const** Zeiger für das erste Argument. In C++ sind zwei Überladungen verfügbar. Die Überladung, die einen Zeiger auf **const** gibt einen Zeiger auf **const**; die Version, die einen Zeiger auf nicht-akzeptiert**const** gibt einen Zeiger auf nicht-**const** . Das Makro \_CRT\_CONST\_richtig\_ÜBERLADUNGEN definiert ist, wenn sowohl die **const** und nicht-**const** Versionen dieser Funktionen sind verfügbar. Wenn Sie nicht benötigen**const** Verhalten für beide C++-Überladungen in C++, definieren Sie das Symbol \_CONST\_zurück.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|`memchr`|\<memory.h> oder \<string.h>|
|`wmemchr`|\<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Alle Versionen [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Beispiel

```C
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

### <a name="output"></a>Output

```Output
String to be searched:
             The quick brown dog jumps over the lazy fox
                      1         2         3         4         5
             12345678901234567890123456789012345678901234567890

Search char: r
Result:      r found at position 12
```

## <a name="see-also"></a>Siehe auch

[Pufferbearbeitung](../../c-runtime-library/buffer-manipulation.md)<br/>
[_memccpy](memccpy.md)<br/>
[memcmp, wmemcmp](memcmp-wmemcmp.md)<br/>
[memcpy, wmemcpy](memcpy-wmemcpy.md)<br/>
[memset, wmemset](memset-wmemset.md)<br/>
[strchr, wcschr, _mbschr, _mbschr_l](strchr-wcschr-mbschr-mbschr-l.md)<br/>
