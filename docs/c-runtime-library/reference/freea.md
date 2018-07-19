---
title: _freea | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _freea
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
apitype: DLLExport
f1_keywords:
- freea
- _freea
dev_langs:
- C++
helpviewer_keywords:
- _freea function
- freea function
- memory deallocation
ms.assetid: dcd30584-dd9d-443b-8c4c-13237a1cecac
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8ac01f965e159dae19bbbd748c1692058063a211
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32403602"
---
# <a name="freea"></a>_freea

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

Die **_freea** Funktion hebt die Zuordnung eines Speicherblocks (*Memblock*), die zuvor durch einen Aufruf von belegt wurde [_malloca](malloca.md). **_freea** prüft, ob der Speicher auf dem Heap oder Stapel belegt wurde. Wenn es auf dem Stapel belegt wurde **_freea** wird keine Aktion ausgeführt. Wenn Speicher auf dem Heap belegt wurde, entspricht die Anzahl der freigegebenen Bytes der Anzahl der Bytes, die angefordert wurden, als der Block belegt wurde. Wenn *Memblock* ist **NULL**, der Zeiger wird ignoriert und **_freea** wird sofort zurückgegeben. Bei dem Versuch, einen ungültigen Zeiger frei (ein Zeiger auf einen Speicherblock, der nicht durch belegt wurde **_malloca**) möglicherweise Auswirkungen auf nachfolgende belegungsanforderungen und Fehler verursachen.

**_freea** Aufrufe **freien** intern verwendet werden, wenn er feststellt, dass der Arbeitsspeicher auf dem Heap zugeordnet wird. Ein Marker bestimmt im Speicher an der Adresse, die dem zugewiesenen Speicher unmittelbar vorausgeht, ob der Speicher auf dem Heap oder dem Stapel belegt wird.

Wenn ein Fehler auftritt, bei der Freigabe des Arbeitsspeichers und **Errno** mit Informationen des Betriebssystems über die Art des Fehlers festgelegt ist. Weitere Informationen finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Nachdem ein Speicherblock freigegeben wurde, minimiert [_heapmin](heapmin.md) die Menge des freien Speicherplatzes auf dem Heap, indem die nicht verwendeten Bereiche zusammengefügt und wieder an das Betriebssystem freigegeben werden. Freigegebener Speicher, der nicht an das Betriebssystem freigegeben wird, wird im freien Pool wiederhergestellt und ist wieder für eine Zuordnung verfügbar.

Ein Aufruf von **_freea** müssen alle Aufrufe an begleiten **_malloca**. Es ist auch ein Fehler auf, rufen Sie **_freea** zweimal auf den gleichen Arbeitsspeicher. Wenn die Anwendung vor allem mit mit einer Debugversion der C-Laufzeitbibliotheken verknüpft ist [_malloc_dbg](malloc-dbg.md) definieren aktivierte Funktionen **_CRTDBG_MAP_ALLOC**, es ist einfacher, fehlen oder Aufrufe von dupliziert **_freea**. Weitere Informationen dazu, wie der Heap während des Debugprozesses verwaltet wird, finden Sie unter [CRT-Debugheap](/visualstudio/debugger/crt-debug-heap-details).

**_freea** RuntimeCompatibility `__declspec(noalias)`, was bedeutet, dass die Funktion gewährleistet ist, nicht um die globalen Variablen zu ändern. Weitere Informationen finden Sie unter [noalias](../../cpp/noalias.md).

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
