---
title: qsort | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- qsort function
- quick-sort algorithm
- sorting arrays
- arrays [CRT], sorting
ms.assetid: d6cb33eb-d209-485f-8d41-229eb743c027
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8ac444680a22a99f292b1728181103789435a150
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
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

*Basis* Anfang des Zielarrays.

*Anzahl* Array-Größe von Elementen führen.

*Breite* Elementgröße in Bytes.

*Vergleichen Sie* Zeiger auf eine vom Benutzer bereitgestellte Routine, die vergleicht zwei Elemente des Arrays und gibt einen Wert, der ihre Beziehung angibt.

## <a name="remarks"></a>Hinweise

Die **Qsort** -Funktion implementiert einen Schnellsortierungsalgorithmus um ein Array von sortieren *Anzahl* Elementen, von denen jedes *Breite* Bytes. Das Argument *Basis* ist ein Zeiger auf der Basis des Arrays sortiert werden. **Qsort** überschreibt dieses Array mit den sortierten Elementen.

**Qsort** Aufrufe der *vergleichen* Routine eine oder mehrere Zeiten während der Sortierung und Zeiger auf zwei Arrayelemente bei jedem Aufruf übergibt.

```C
compare( (void *) & elem1, (void *) & elem2 );
```

Die Routine vergleicht die Elemente und gibt einen der folgenden Werte zurück.

|Vergleich des Rückgabewerts der Funktion|Beschreibung|
|-----------------------------------|-----------------|
|< 0|**elem1** kleiner als **elem2**|
|0|**elem1** entspricht **elem2**|
|> 0|**elem1** größer als **elem2**|

Das Array wird in aufsteigender Reihenfolge sortiert, wie von der Vergleichsfunktion definiert. Kehren Sie den Sinn der „größer als“ und „kleiner als“ in der Vergleichsfunktion um, um ein Array in absteigender Reihenfolge zu sortieren.

Diese Funktion überprüft ihre Parameter. Wenn *vergleichen* oder *Anzahl* ist **NULL**, oder wenn *Basis* ist **NULL** und **Anzahl* ungleich NULL ist oder wenn *Breite* ist kleiner als 0 (null), die Handler für ungültige Parameter aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, gibt die Funktion und **Errno** festgelegt ist, um **EINVAL**.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
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
