---
title: _lfind
ms.date: 11/04/2016
apiname:
- _lfind
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
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- lfind
- _lfind
helpviewer_keywords:
- linear searching
- lfind function
- arrays [CRT], searching
- searching, linear
- finding keys in arrays
- _lfind function
ms.assetid: a40ece70-1674-4b75-94bd-9f57cfff18f2
ms.openlocfilehash: 1508d54d6b2f2566e4aee3afef02af45b28e4f48
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62286491"
---
# <a name="lfind"></a>_lfind

Führt eine lineare Suche für den angegebenen Schlüssel aus. Es ist eine sicherere Version dieser Funktion verfügbar. Siehe [_lfind_s](lfind-s.md).

## <a name="syntax"></a>Syntax

```C
void *_lfind(
   const void *key,
   const void *base,
   unsigned int *num,
   unsigned int width,
   int (__cdecl *compare)(const void *, const void *)
);
```

### <a name="parameters"></a>Parameter

*key*<br/>
Das Objekt, nach dem gesucht werden soll.

*base*<br/>
Zeiger auf die Basis der Suchdaten.

*Anzahl*<br/>
Die Anzahl der Arrayelemente.

*width*<br/>
Die Breite von Arrayelementen.

*compare*<br/>
Zeiger auf die Vergleichsroutine. Der erste Parameter ist ein Zeiger auf den Schlüssel für die Suche. Der zweite Parameter ist ein Zeiger auf das Arrayelement, das mit dem Schlüssel verglichen werden soll.

## <a name="return-value"></a>Rückgabewert

Wenn der Schlüssel gefunden wird, **_lfind** gibt einen Zeiger auf das Element des Arrays, an *Basis* entspricht *Schlüssel*. Wenn der Schlüssel nicht gefunden wird, **_lfind** gibt **NULL**.

## <a name="remarks"></a>Hinweise

Die **_lfind** Funktion führt eine lineare Suche für den Wert *Schlüssel* in ein Array von *Anzahl* Elementen, die jeweils von *Breite* Bytes. Im Gegensatz zu **Bsearch**, **_lfind** erfordert keine Arrays, das sortiert werden. Die *Basis* Argument ist ein Zeiger auf die Basis des Arrays, das gesucht werden soll. Die *vergleichen* Argument ist ein Zeiger auf eine benutzerdefinierte Routine, die zwei Elemente des Arrays vergleicht und dann gibt einen Wert, der ihre Beziehung angibt. **_lfind** Aufrufe der *vergleichen* -Routine einmal oder mehrere Male während der Suche, die Übergabe von Zeigern auf zwei Arrayelemente bei jedem Aufruf. Die *vergleichen* Routine muss die Elemente vergleichen kann, und klicken Sie dann zurückgeben ungleich Null (d.h. die Elemente unterscheiden sich) oder 0 (d.h. die Elemente sind identisch).

Diese Funktion überprüft ihre Parameter. Wenn *vergleichen*, *Schlüssel* oder *Anzahl* ist **NULL**, oder wenn *Basis* ist **NULL**und *Anzahl* ungleich NULL ist, oder wenn *Breite* ist kleiner als 0 (null), Handler für ungültige Parameter aufgerufen wird, der unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, **Errno** nastaven NA hodnotu **EINVAL** und die Funktion gibt **NULL**.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_lfind**|\<search.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_lfind.c
// This program uses _lfind to search a string array
// for an occurrence of "hello".

#include <search.h>
#include <string.h>
#include <stdio.h>

int compare(const void *arg1, const void *arg2 )
{
   return( _stricmp( * (char**)arg1, * (char**)arg2 ) );
}

int main( )
{
   char *arr[] = {"Hi", "Hello", "Bye"};
   int n = sizeof(arr) / sizeof(char*);
   char **result;
   char *key = "hello";

   result = (char **)_lfind( &key, arr,
                      &n, sizeof(char *), compare );

   if( result )
      printf( "%s found\n", *result );
   else
      printf( "hello not found!\n" );
}
```

```Output
Hello found
```

## <a name="see-also"></a>Siehe auch

[Suchen und Sortieren](../../c-runtime-library/searching-and-sorting.md)<br/>
[_lfind_s](lfind-s.md)<br/>
[bsearch](bsearch.md)<br/>
[_lsearch](lsearch.md)<br/>
[qsort](qsort.md)<br/>
