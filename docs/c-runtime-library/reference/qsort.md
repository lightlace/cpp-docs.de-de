---
title: qsort
ms.date: 11/04/2016
apiname:
- qsort
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
- ntdll.dll
- ucrtbase.dll
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- qsort
helpviewer_keywords:
- qsort function
- quick-sort algorithm
- sorting arrays
- arrays [CRT], sorting
ms.assetid: d6cb33eb-d209-485f-8d41-229eb743c027
ms.openlocfilehash: e912a7a53619e9347cf2c0cd40adf0f9162b314b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50618490"
---
# <a name="qsort"></a>qsort

Führt eine schnelle Sortierung aus. Es ist eine sicherere Version dieser Funktion verfügbar. Informationen dazu finden Sie unter [qsort_s](qsort-s.md).

## <a name="syntax"></a>Syntax

```C
void qsort(
   void *base,
   size_t num,
   size_t width,
   int (__cdecl *compare )(const void *, const void *)
);
```

### <a name="parameters"></a>Parameter

<br/>
Start des Zielarrays.

*Anzahl*<br/>
Arraygröße in Elementen.

*width*<br/>
Elementgröße in Bytes.

*compare*<br/>
Zeiger auf eine benutzerdefinierte Routine, die zwei Elemente des Arrays vergleicht und einen Wert zurückgibt, der ihre Beziehung angibt.

## <a name="remarks"></a>Hinweise

Die **Qsort** -Funktion implementiert einen Schnellsortierungsalgorithmus, um ein Array von sortieren *Anzahl* Elementen, die jeweils von *Breite* Bytes. Das Argument *Basis* ist ein Zeiger auf die Basis des Arrays, das sortiert werden. **Qsort** überschreibt dieses Array mit den sortierten Elementen.

**Qsort** Aufrufe der *vergleichen* -Routine einmal oder mehrere Male während der Sortierung und Zeiger auf zwei Arrayelemente übergeben, bei jedem Aufruf.

```C
compare( (void *) & elem1, (void *) & elem2 );
```

Die Routine vergleicht die Elemente und gibt einen der folgenden Werte zurück.

|Vergleich des Rückgabewerts der Funktion|Beschreibung|
|-----------------------------------|-----------------|
|< 0|**elem1** kleiner als **elem2**|
|0|**elem1** entspricht **elem2**|
|> 0|**elem1** größer als **elem2**|

Das Array wird in aufsteigender Reihenfolge sortiert, wie von der Vergleichsfunktion definiert. Kehren Sie den Sinn der „größer als“ und „kleiner als“ in der Vergleichsfunktion um, um ein Array in absteigender Reihenfolge zu sortieren.

Diese Funktion überprüft ihre Parameter. Wenn *vergleichen* oder *Anzahl* ist **NULL**, oder wenn *Basis* ist **NULL** und **Anzahl* ungleich NULL ist, oder wenn *Breite* ist kleiner als 0 (null), Handler für ungültige Parameter aufgerufen wird, der unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, gibt die Funktion und **Errno** nastaven NA hodnotu **EINVAL**.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**qsort**|\<stdlib.h> und \<search.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_qsort.c
// arguments: every good boy deserves favor

/* This program reads the command-line
* parameters and uses qsort to sort them. It
* then displays the sorted arguments.
*/

#include <stdlib.h>
#include <string.h>
#include <stdio.h>

int compare( const void *arg1, const void *arg2 );

int main( int argc, char **argv )
{
   int i;
   /* Eliminate argv[0] from sort: */
   argv++;
   argc--;

   /* Sort remaining args using Quicksort algorithm: */
   qsort( (void *)argv, (size_t)argc, sizeof( char * ), compare );

   /* Output sorted list: */
   for( i = 0; i < argc; ++i )
      printf( " %s", argv[i] );
   printf( "\n" );
}

int compare( const void *arg1, const void *arg2 )
{
   /* Compare all of both strings: */
   return _stricmp( * ( char** ) arg1, * ( char** ) arg2 );
}
```

```Output
boy deserves every favor good
```

## <a name="see-also"></a>Siehe auch

[Suchen und Sortieren](../../c-runtime-library/searching-and-sorting.md)<br/>
[bsearch](bsearch.md)<br/>
[_lsearch](lsearch.md)<br/>
