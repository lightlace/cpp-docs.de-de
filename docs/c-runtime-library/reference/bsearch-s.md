---
title: bsearch_s
ms.date: 11/04/2016
apiname:
- bsearch_s
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
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- bsearch_s
helpviewer_keywords:
- arrays [CRT], binary search
- bsearch_s function
ms.assetid: d5690d5e-6be3-4f1d-aa0b-5ca6dbded276
ms.openlocfilehash: 56c5fa45a9d8f9ac9b22474601934d3994da55e4
ms.sourcegitcommit: e06648107065f3dea35f40c1ae5999391087b80b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/01/2019
ms.locfileid: "57210951"
---
# <a name="bsearchs"></a>bsearch_s

Führt eine binäre Suche eines sortierten Arrays aus. Dies ist eine Version von [bsearch](bsearch.md) mit Sicherheitsverbesserungen, wie dies unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben wird.

## <a name="syntax"></a>Syntax

```C
void *bsearch_s(
   const void *key,
   const void *base,
   size_t number,
   size_t width,
   int ( __cdecl *compare ) ( void *, const void *key, const void *datum),
   void * context
);
```

### <a name="parameters"></a>Parameter

*key*<br/>
Das Objekt, nach dem gesucht werden soll.

*base*<br/>
Zeiger auf die Basis der Suchdaten.

*Anzahl*<br/>
Anzahl der Elemente.

*width*<br/>
Breite der Elemente.

*compare*<br/>
Rückruffunktion, die zwei Elemente vergleicht. Das erste Argument ist der *Kontext* Zeiger. Das zweite Argument ist ein Zeiger auf die *Schlüssel* für die Suche. Das dritte Argument ist ein Zeiger auf das Arrayelement mit verglichen werden soll *Schlüssel*.

*context*<br/>
Ein Zeiger auf ein Objekt, auf das in der Vergleichsfunktion zugegriffen werden kann.

## <a name="return-value"></a>Rückgabewert

**Bsearch_s** gibt einen Zeiger auf ein Vorkommen von *Schlüssel* in das Array verweist *Basis*. Wenn *Schlüssel* nicht gefunden wird, wird die Funktion gibt **NULL**. Wenn das Array nicht in aufsteigender Reihenfolge sortiert ist oder doppelte Datensätze mit identischen Schlüsseln enthält, ist das Ergebnis nicht vorhersehbar.

Wenn ungültige Parameter an die Funktion übergeben werden, ruft sie den Handler für ungültige Parameter auf, wie in [Parameter Validation](../../c-runtime-library/parameter-validation.md)beschrieben. Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, **Errno** nastaven NA hodnotu **EINVAL** und die Funktion gibt **NULL**. Weitere Informationen finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

### <a name="error-conditions"></a>Fehlerbedingungen

|||||||
|-|-|-|-|-|-|
|*key*|*base*|*compare*|*Anzahl*|*width*|**errno**|
|**NULL**|any|any|any|any|**EINVAL**|
|any|**NULL**|any|!= 0|any|**EINVAL**|
|any|any|any|any|= 0|**EINVAL**|
|any|any|**NULL**|ein|any|**EINVAL**|

## <a name="remarks"></a>Hinweise

Die **Bsearch_s** Funktion führt eine binäre Suche eines sortierten Arrays von *Anzahl* Elementen, die jeweils von *Breite* Bytes groß. Die *Basis* Wert ist ein Zeiger auf die Basis des Arrays, das gesucht werden soll, und *Schlüssel* ist der Wert, der gesucht wird. Die *vergleichen* Parameter ist ein Zeiger auf eine benutzerdefinierte Routine, die den angeforderten Schlüssel auf ein Arrayelement vergleicht und gibt einen der folgenden Werte, der ihre Beziehung angibt:

|Rückgabewert von *vergleichen* Routine|Beschreibung|
|-----------------------------------------|-----------------|
|\< 0|Der Schlüssel ist kleiner als das Arrayelement.|
|0|Schlüssel und Arrayelement sind gleich.|
|> 0|Der Schlüssel ist größer als das Arrayelement.|

Die *Kontext* -Zeiger kann nützlich sein, wenn die durchsuchte Datenstruktur Teil eines Objekts ist und die Vergleichsfunktion auf Member des Objekts zugreifen muss. Die *vergleichen* Funktion möglicherweise den void-Zeiger umgewandelt, in das entsprechende Objekt und auf Member des Objekts. Das Hinzufügen der *Kontext* -Parameters macht **Bsearch_s** sicherer, da weiterer Kontext verwendet werden kann, um Wiedereintreten mit der Verwendung statischer Variablen zur Daten zur Verfügung stellen zu vermeiden. die *vergleichen* Funktion.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**bsearch_s**|\<stdlib.h> und \<search.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Dieses Programm sortiert ein Zeichenfolgenarray mit [qsort_s](qsort-s.md)und verwendet anschließend bsearch_s, um nach dem Wort „Katze“ zu suchen.

```cpp
// crt_bsearch_s.cpp
// This program uses bsearch_s to search a string array,
// passing a locale as the context.
// compile with: /EHsc
#include <stdlib.h>
#include <stdio.h>
#include <search.h>
#include <process.h>
#include <locale.h>
#include <locale>
#include <windows.h>
using namespace std;

// The sort order is dependent on the code page.  Use 'chcp' at the
// command line to change the codepage.  When executing this application,
// the command prompt codepage must match the codepage used here:

#define CODEPAGE_850

#ifdef CODEPAGE_850
#define ENGLISH_LOCALE "English_US.850"
#endif

#ifdef CODEPAGE_1252
#define ENGLISH_LOCALE "English_US.1252"
#endif

// The context parameter lets you create a more generic compare.
// Without this parameter, you would have stored the locale in a
// static variable, thus making it vulnerable to thread conflicts
// (if this were a multithreaded program).

int compare( void *pvlocale, char **str1, char **str2)
{
    char *s1 = *str1;
    char *s2 = *str2;

    locale& loc = *( reinterpret_cast< locale * > ( pvlocale));

    return use_facet< collate<char> >(loc).compare(
       s1, s1+strlen(s1),
       s2, s2+strlen(s2) );
}

int main( void )
{
   char *arr[] = {"dog", "pig", "horse", "cat", "human", "rat", "cow", "goat"};

   char *key = "cat";
   char **result;
   int i;

   /* Sort using Quicksort algorithm: */
   qsort_s( arr,
            sizeof(arr)/sizeof(arr[0]),
            sizeof( char * ),
            (int (*)(void*, const void*, const void*))compare,
            &locale(ENGLISH_LOCALE) );

   for( i = 0; i < sizeof(arr)/sizeof(arr[0]); ++i )    /* Output sorted list */
      printf( "%s ", arr[i] );

   /* Find the word "cat" using a binary search algorithm: */
   result = (char **)bsearch_s( &key,
                                arr,
                                sizeof(arr)/sizeof(arr[0]),
                                sizeof( char * ),
                                (int (*)(void*, const void*, const void*))compare,
                                &locale(ENGLISH_LOCALE) );
   if( result )
      printf( "\n%s found at %Fp\n", *result, result );
   else
      printf( "\nCat not found!\n" );
}
```

```Output
cat cow dog goat horse human pig rat
cat found at 002F0F04
```

## <a name="see-also"></a>Siehe auch

[Suchen und Sortieren](../../c-runtime-library/searching-and-sorting.md)<br/>
[_lfind](lfind.md)<br/>
[_lsearch](lsearch.md)<br/>
[qsort](qsort.md)<br/>
