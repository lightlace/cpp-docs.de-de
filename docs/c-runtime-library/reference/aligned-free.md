---
title: _aligned_free
ms.date: 11/04/2016
apiname:
- _aligned_free
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
- aligned_free
- _aligned_free
helpviewer_keywords:
- _aligned_free function
- aligned_free function
ms.assetid: ed1ce952-cdfc-4682-85cc-f75d4101603d
ms.openlocfilehash: e2d1dc1172d1cd0d31f8daa8125bd052252393c0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62341651"
---
# <a name="alignedfree"></a>_aligned_free

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

**_aligned_free** RuntimeCompatibility `__declspec(noalias)`, was bedeutet, dass die Funktion garantiert nicht, um globale Variablen zu ändern. Weitere Informationen finden Sie unter [noalias](../../cpp/noalias.md).

Diese Funktion überprüft im Gegensatz zu den anderen _aligned-CRT-Funktionen den Parameter nicht. Wenn *Memblock* ist ein Nullzeiger, diese Funktion einfach führt keine Aktionen. Es verändert `errno` nicht und ruft auch keine ungültigen Parametertyphandler auf. Wenn in der Funktion ein Fehler auftritt, weil Sie vorher keine _aligned-Funktion benutzt haben, um den Speicherblock zuzuordnen, oder wenn eine falsche Speicherausrichtung aufgrund eines unvorhergesehenen Problems auftritt, generiert die Funktion einen Debugbericht aus den [_RPT, _RPTF, _RPTW und _RPTFW-Makros](rpt-rptf-rptw-rptfw-macros.md).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_aligned_free**|\<malloc.h>|

## <a name="example"></a>Beispiel

Weitere Informationen finden Sie unter [_aligned_malloc](aligned-malloc.md).

## <a name="see-also"></a>Siehe auch

[Datenausrichtung](../../c-runtime-library/data-alignment.md)