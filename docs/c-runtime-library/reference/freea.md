---
title: _freea
ms.date: 11/04/2016
api_name:
- _freea
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- freea
- _freea
helpviewer_keywords:
- _freea function
- freea function
- memory deallocation
ms.assetid: dcd30584-dd9d-443b-8c4c-13237a1cecac
ms.openlocfilehash: dcad8bea4f8cec28d8cb15a9937b1032593ef0cc
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70956711"
---
# <a name="_freea"></a>_freea

Hebt die Zuweisung eines Speicherblocks auf oder gibt diesen frei.

## <a name="syntax"></a>Syntax

```C
void _freea(
   void *memblock
);
```

### <a name="parameters"></a>Parameter

*memblock*<br/>
Zuvor zugewiesener Speicherblock, der freigegeben werden soll.

## <a name="return-value"></a>Rückgabewert

Keine.

## <a name="remarks"></a>Hinweise

Die **_freea** -Funktion hebt die Zuordnung eines Speicherblocks (*memblock*) auf, der zuvor durch einen-Befehl von [_malloca](malloca.md)zugeordnet wurde. **_freea** prüft, ob der Arbeitsspeicher auf dem Heap oder dem Stapel zugeordnet wurde. Wenn die Zuordnung auf dem Stapel erfolgt ist, führt **_freea** keine Aktion aus. Wenn Speicher auf dem Heap belegt wurde, entspricht die Anzahl der freigegebenen Bytes der Anzahl der Bytes, die angefordert wurden, als der Block belegt wurde. Wenn *memblock* **null**ist, wird der Zeiger ignoriert, und **_freea** gibt sofort zurück. Der Versuch, einen ungültigen Zeiger freizugeben (einen Zeiger auf einen Speicherblock, der nicht von **_malloca**zugeordnet wurde), kann nachfolgende Zuordnungs Anforderungen beeinflussen und Fehler verursachen.

**_freea** ruft **intern** auf, wenn festgestellt wird, dass der Arbeitsspeicher auf dem Heap belegt ist. Ein Marker bestimmt im Speicher an der Adresse, die dem zugewiesenen Speicher unmittelbar vorausgeht, ob der Speicher auf dem Heap oder dem Stapel belegt wird.

Wenn bei der Freigabe des Speichers ein Fehler auftritt, wird **errno** mit Informationen aus dem Betriebssystem für die Art des Fehlers festgelegt. Weitere Informationen finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Nachdem ein Speicherblock freigegeben wurde, minimiert [_heapmin](heapmin.md) die Menge des freien Speicherplatzes auf dem Heap, indem die nicht verwendeten Bereiche zusammengefügt und wieder an das Betriebssystem freigegeben werden. Freigegebener Speicher, der nicht an das Betriebssystem freigegeben wird, wird im freien Pool wiederhergestellt und ist wieder für eine Zuordnung verfügbar.

Ein Aufruf von **_freea** muss alle Aufrufe an **_malloca**begleiten. Es ist auch ein Fehler, **_freea** zweimal im gleichen Speicher aufzurufen. Wenn die Anwendung mit einer Debugversion der C-Laufzeitbibliotheken verknüpft ist, insbesondere bei [_malloc_dbg](malloc-dbg.md) -Funktionen, die durch Definieren von **_CRTDBG_MAP_ALLOC**aktiviert werden, ist es einfacher, fehlende oder doppelte Aufrufe von **_freea**zu finden. Weitere Informationen dazu, wie der Heap während des Debugprozesses verwaltet wird, finden Sie unter [CRT-Debugheap](/visualstudio/debugger/crt-debug-heap-details).

**_freea** ist als `__declspec(noalias)`markiert, was bedeutet, dass die Funktion globale Variablen garantiert nicht ändert. Weitere Informationen finden Sie unter [noalias](../../cpp/noalias.md).

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|
|--------------|---------------------|
|**_freea**|\<stdlib.h> und \<malloc.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Siehe das Beispiel für [_malloca](malloca.md).

## <a name="see-also"></a>Siehe auch

[Speicherreservierung](../../c-runtime-library/memory-allocation.md)<br/>
[_malloca](malloca.md)<br/>
[calloc](calloc.md)<br/>
[malloc](malloc.md)<br/>
[_malloc_dbg](malloc-dbg.md)<br/>
[realloc](realloc.md)<br/>
[_free_dbg](free-dbg.md)<br/>
[_heapmin](heapmin.md)<br/>
