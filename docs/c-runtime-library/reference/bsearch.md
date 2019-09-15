---
title: bsearch
ms.date: 11/04/2016
api_name:
- bsearch
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- bsearch
helpviewer_keywords:
- arrays [CRT], binary search
- bsearch function
ms.assetid: e0ad2f47-e7dd-49ed-8288-870457a14a2c
ms.openlocfilehash: 9e44e85d1c6d73a68da2edd099cdeb6156f9759d
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70939436"
---
# <a name="bsearch"></a>bsearch

Führt eine binäre Suche eines sortierten Arrays aus. Es ist eine sicherere Version dieser Funktion verfügbar. Informationen dazu finden Sie unter [bsearch_s](bsearch-s.md).

## <a name="syntax"></a>Syntax

```C
void *bsearch(
   const void *key,
   const void *base,
   size_t num,
   size_t width,
   int ( __cdecl *compare ) (const void *key, const void *datum)
);
```

### <a name="parameters"></a>Parameter

*key*<br/>
Das Objekt, nach dem gesucht werden soll.

*base*<br/>
Zeiger auf die Basis der Suchdaten.

*number*<br/>
Anzahl der Elemente.

*width*<br/>
Breite der Elemente.

*compare*<br/>
Rückruffunktion, die zwei Elemente vergleicht. Da erste ist ein Zeiger auf den Schlüssel für die Suche, und das zweite ist ein Zeiger auf das Arrayelement, das mit dem Schlüssel verglichen werden soll.

## <a name="return-value"></a>Rückgabewert

**bsearch** gibt einen Zeiger auf ein Vorkommen von *Key* in dem Array zurück, auf das von *Base*verwiesen wird. Wenn *Key* nicht gefunden wird, gibt die Funktion **null**zurück. Wenn das Array nicht in aufsteigender Reihenfolge sortiert ist oder doppelte Datensätze mit identischen Schlüsseln enthält, ist das Ergebnis nicht vorhersehbar.

## <a name="remarks"></a>Hinweise

Die **bsearch** -Funktion führt eine binäre Suche eines sortierten Arrays von *Zahlen* Elementen durch, wobei jede *Breite* Byte groß ist. Der *Basiswert* ist ein Zeiger auf die Basis des zu durchsuchenden Arrays, und *Key* ist der Wert, der gesucht wird. Der *Compare* -Parameter ist ein Zeiger auf eine vom Benutzer bereitgestellte Routine, die den angeforderten Schlüssel mit einem Array Element vergleicht und einen der folgenden Werte zurückgibt, die die zugehörige Beziehung angeben:

|Von der *Vergleichs* Routine zurückgegebener Wert|Beschreibung|
|-----------------------------------------|-----------------|
|\< 0|Der Schlüssel ist kleiner als das Arrayelement.|
|0|Schlüssel und Arrayelement sind gleich.|
|> 0|Der Schlüssel ist größer als das Arrayelement.|

Diese Funktion überprüft ihre Parameter. Wenn *Compare*, *Key* oder *Number* **null**ist, oder wenn *Base* **null** und *Number* ungleich 0 (NULL *) ist,* wird der Handler für ungültige Parameter aufgerufen, wie in [Parameter Validation (Parameter Überprüfung) beschrieben. ](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, wird **errno** auf `EINVAL` festgelegt, und die Funktion gibt **null**zurück.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**bsearch**|\<stdlib.h> und \<search.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Dieses Programm sortiert ein Zeichenfolgenarray mit „qsort“ und verwendet anschließend bsearch, um nach dem Wort „Katze“ zu suchen.

```C
// crt_bsearch.c
#include <search.h>
#include <string.h>
#include <stdio.h>

int compare( char **arg1, char **arg2 )
{
   /* Compare all of both strings: */
   return _strcmpi( *arg1, *arg2 );
}

int main( void )
{
   char *arr[] = {"dog", "pig", "horse", "cat", "human", "rat", "cow", "goat"};
   char **result;
   char *key = "cat";
   int i;

   /* Sort using Quicksort algorithm: */
   qsort( (void *)arr, sizeof(arr)/sizeof(arr[0]), sizeof( char * ), (int (*)(const
   void*, const void*))compare );

   for( i = 0; i < sizeof(arr)/sizeof(arr[0]); ++i )    /* Output sorted list */
      printf( "%s ", arr[i] );

   /* Find the word "cat" using a binary search algorithm: */
   result = (char **)bsearch( (char *) &key, (char *)arr, sizeof(arr)/sizeof(arr[0]),
                              sizeof( char * ), (int (*)(const void*, const void*))compare );
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
