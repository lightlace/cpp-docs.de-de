---
title: _lsearch | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- _lsearch function
- values, searching for
- keys, finding in arrays
- arrays [CRT], searching
- linear searches
- searching, linear
- lsearch function
ms.assetid: 8200f608-159a-46f0-923b-1a37ee1af7e0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2aaf6626b2f7005181640f77026b6924c39cd325
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2018
ms.locfileid: "34451298"
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

Wenn der Schlüssel gefunden wird, **_lsearch** gibt einen Zeiger auf das Element des Arrays bei *Basis* entspricht *Schlüssel*. Wenn der Schlüssel nicht gefunden wird, **_lsearch** gibt einen Zeiger auf das neu hinzugefügte Element am Ende des Arrays.

## <a name="remarks"></a>Hinweise

Die **_lsearch** Funktion führt eine lineare Suche für den Wert *Schlüssel* in ein Array von *Anzahl* Elementen, von denen jedes *Breite* Bytes. Im Gegensatz zu **Bsearch**, **_lsearch** erfordert nicht das Array, das sortiert werden. Wenn *Schlüssel* wurde nicht gefunden, **_lsearch** fügt es am Ende des Arrays und Schritten *Anzahl*.

Die *vergleichen* Argument ist ein Zeiger auf eine vom Benutzer bereitgestellte Routine, die zwei Arrayelemente vergleicht und einen Wert, der Angabe ihrer Beziehung zurückgibt. **_lsearch** Aufrufe der *vergleichen* routinemäßige ein- oder mehrmals während der Suche, die Übergabe von Zeigern auf zwei Arrayelemente bei jedem Aufruf. *Vergleichen Sie* vergleichen Sie die Elemente und zurückgeben muss ungleich Null (d. h., die Elemente sind unterschiedlich) oder 0 (d. h., die Elemente sind identisch).

Diese Funktion überprüft ihre Parameter. Wenn *vergleichen*, *Schlüssel* oder *Anzahl* ist **NULL**, oder wenn *Basis* ist **NULL**und *Anzahl* ungleich NULL ist oder wenn *Breite* ist kleiner als 0 (null), die Handler für ungültige Parameter aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, **Errno** festgelegt ist, um **EINVAL** und die Funktion gibt **NULL**.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
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
