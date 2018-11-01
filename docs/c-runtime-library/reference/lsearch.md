---
title: _lsearch
ms.date: 11/04/2016
apiname:
- _lsearch
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
- _lsearch
- lsearch
helpviewer_keywords:
- _lsearch function
- values, searching for
- keys, finding in arrays
- arrays [CRT], searching
- linear searches
- searching, linear
- lsearch function
ms.assetid: 8200f608-159a-46f0-923b-1a37ee1af7e0
ms.openlocfilehash: 340e8ac382972b15acc52013d5d6a51352db969c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50532810"
---
# <a name="lsearch"></a>_lsearch

Führt eine lineare Suche nach einem Wert aus. Fügt ihn am Ende der Liste hinzu, falls nicht gefunden. Es ist eine sicherere Version dieser Funktion verfügbar. Informationen dazu finden Sie unter [_lsearch_s](lsearch-s.md).

## <a name="syntax"></a>Syntax

```C
void *_lsearch(
   const void *key,
   void *base,
   unsigned int *num,
   unsigned int width,
   int (__cdecl *compare)(const void *, const void *)
);
```

### <a name="parameters"></a>Parameter

*key*<br/>
Das Objekt, nach dem gesucht werden soll.

*base*<br/>
Zeiger auf der Basis des zu durchsuchenden Arrays.

*Anzahl*<br/>
Anzahl der Elemente.

*width*<br/>
Die Breite jedes Array-Elements.

*compare*<br/>
Ein Zeiger auf die Vergleichsroutine. Der erste Parameter ist ein Zeiger auf den Schlüssel für die Suche. Der zweite Parameter ist ein Zeiger auf das Arrayelement, das mit dem Schlüssel verglichen werden soll.

## <a name="return-value"></a>Rückgabewert

Wenn der Schlüssel gefunden wird, **_lsearch** gibt einen Zeiger auf das Element des Arrays, an *Basis* entspricht *Schlüssel*. Wenn der Schlüssel nicht gefunden wird, **_lsearch** gibt einen Zeiger auf das neu hinzugefügte Element am Ende des Arrays zurück.

## <a name="remarks"></a>Hinweise

Die **_lsearch** Funktion führt eine lineare Suche für den Wert *Schlüssel* in ein Array von *Anzahl* Elementen, die jeweils von *Breite* Bytes. Im Gegensatz zu **Bsearch**, **_lsearch** erfordert keine Arrays, das sortiert werden. Wenn *Schlüssel* nicht gefunden wird, **_lsearch** fügt es am Ende des Arrays und Schritten *Anzahl*.

Die *vergleichen* Argument ist ein Zeiger auf eine benutzerdefinierte Routine, die zwei Elemente des Arrays vergleicht und gibt einen Wert, der ihre Beziehung angibt. **_lsearch** Aufrufe der *vergleichen* -Routine einmal oder mehrere Male während der Suche, die Übergabe von Zeigern auf zwei Arrayelemente bei jedem Aufruf. *Vergleichen Sie* die Elemente vergleichen und zurückgeben muss ungleich Null (d.h. die Elemente unterscheiden sich) oder 0 (d.h. die Elemente sind identisch).

Diese Funktion überprüft ihre Parameter. Wenn *vergleichen*, *Schlüssel* oder *Anzahl* ist **NULL**, oder wenn *Basis* ist **NULL**und *Anzahl* ungleich NULL ist, oder wenn *Breite* ist kleiner als 0 (null), Handler für ungültige Parameter aufgerufen wird, der unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, **Errno** nastaven NA hodnotu **EINVAL** und die Funktion gibt **NULL**.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_lsearch**|\<search.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_lsearch.c
#include <search.h>
#include <string.h>
#include <stdio.h>

int compare( const void *arg1, const void *arg2 );

int main(void)
{
   char * wordlist[4] = { "hello", "thanks", "bye" };
                            // leave room to grow...
   int n = 3;
   char **result;
   char *key = "extra";
   int i;

   printf( "wordlist before _lsearch:" );
   for( i=0; i<n; ++i ) printf( " %s", wordlist[i] );
   printf( "\n" );

   result = (char **)_lsearch( &key, wordlist,
                      &n, sizeof(char *), compare );

   printf( "wordlist after _lsearch:" );
   for( i=0; i<n; ++i ) printf( " %s", wordlist[i] );
   printf( "\n" );
}

int compare(const void *arg1, const void *arg2 )
{
   return( _stricmp( * (char**)arg1, * (char**)arg2 ) );
}
```

```Output
wordlist before _lsearch: hello thanks bye
wordlist after _lsearch: hello thanks bye extra
```

## <a name="see-also"></a>Siehe auch

[Suchen und Sortieren](../../c-runtime-library/searching-and-sorting.md)<br/>
[bsearch](bsearch.md)<br/>
[_lfind](lfind.md)<br/>
[_lsearch_s](lsearch-s.md)<br/>
