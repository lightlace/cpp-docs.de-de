---
title: _aligned_free
ms.date: 11/04/2016
api_name:
- _aligned_free
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
- api-ms-win-crt-heap-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- aligned_free
- _aligned_free
helpviewer_keywords:
- _aligned_free function
- aligned_free function
ms.assetid: ed1ce952-cdfc-4682-85cc-f75d4101603d
ms.openlocfilehash: 44556d3f044a567f4903ef14a4b2a9b353af02ff
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70943968"
---
# <a name="_aligned_free"></a>_aligned_free

Gibt einen Speicherblock frei, der mit [_aligned_malloc](aligned-malloc.md) oder [_aligned_offset_malloc](aligned-offset-malloc.md) belegt wurde.

## <a name="syntax"></a>Syntax

```C
void _aligned_free (
   void *memblock
);
```

### <a name="parameters"></a>Parameter

*memblock*<br/>
Ein Zeiger auf den Speicherblock, der an die Funktion `_aligned_malloc` oder `_aligned_offset_malloc` zurückgegeben wurde.

## <a name="remarks"></a>Hinweise

**_aligned_free** ist als `__declspec(noalias)`markiert, was bedeutet, dass die Funktion globale Variablen garantiert nicht ändert. Weitere Informationen finden Sie unter [noalias](../../cpp/noalias.md).

Diese Funktion überprüft im Gegensatz zu den anderen _aligned-CRT-Funktionen den Parameter nicht. Wenn *memblock* ein NULL-Zeiger ist, führt diese Funktion einfach keine Aktionen aus. Es verändert `errno` nicht und ruft auch keine ungültigen Parametertyphandler auf. Wenn in der Funktion ein Fehler auftritt, weil Sie vorher keine _aligned-Funktion benutzt haben, um den Speicherblock zuzuordnen, oder wenn eine falsche Speicherausrichtung aufgrund eines unvorhergesehenen Problems auftritt, generiert die Funktion einen Debugbericht aus den [_RPT, _RPTF, _RPTW und _RPTFW-Makros](rpt-rptf-rptw-rptfw-macros.md).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_aligned_free**|\<malloc.h>|

## <a name="example"></a>Beispiel

Weitere Informationen finden Sie unter [_aligned_malloc](aligned-malloc.md).

## <a name="see-also"></a>Siehe auch

[Datenausrichtung](../../c-runtime-library/data-alignment.md)