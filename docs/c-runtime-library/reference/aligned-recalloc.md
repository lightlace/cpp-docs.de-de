---
title: _aligned_recalloc | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _aligned_recalloc
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
- aligned_recalloc
- _aligned_recalloc
dev_langs:
- C++
helpviewer_keywords:
- aligned_recalloc function
- _aligned_recalloc function
ms.assetid: d3da3dcc-79ef-4273-8af5-ac7469420142
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ae20d71dc3a6e23b29c76166e1a09fab8afaf6f9
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="alignedrecalloc"></a>_aligned_recalloc

Ändert die Größe eines Speicherblocks, der mit [_aligned_malloc](aligned-malloc.md) oder [_aligned_offset_malloc](aligned-offset-malloc.md) belegt ist und den Speicher auf 0 initialisiert.

## <a name="syntax"></a>Syntax

```C
void * _aligned_recalloc(
   void *memblock,
   size_t num,
   size_t size,
   size_t alignment
);
```

### <a name="parameters"></a>Parameter

*memblock*<br/>
Der Zeiger auf den aktuellen Speicherblock.

*Anzahl*<br/>
Die Anzahl der Elemente.

*size*<br/>
Die Größe jedes Elements in Byte.

*Ausrichtung*<br/>
Der Ausrichtungswert, der eine ganzzahlige Potenz von 2 sein muss.

## <a name="return-value"></a>Rückgabewert

**_aligned_recalloc** gibt einen void-Zeiger auf den neu belegten (und möglicherweise verschobenen) Speicherblock zurück. Der Rückgabewert ist **NULL** Wenn die Größe 0 (null beträgt) und das pufferargument nicht **NULL**, oder es ist nicht genügend Arbeitsspeicher verfügbar, um den Block auf die vorgegebene Größe auszudehnen. Im ersten Fall wird der ursprüngliche Block freigegeben. Im zweiten Fall wird der ursprüngliche Block nicht geändert. Der Rückgabewert zeigt auf einen Speicherplatz, der für die Speicherung eines beliebigen Objekttyps geeignet ist. Um einen Zeiger auf einen anderen Typ als den leeren zurückzugeben, verwenden Sie eine Typumwandlung für den Rückgabewert.

Es ist ein Fehler, wenn ein Speicher neu belegt und die Ausrichtung eines Blocks geändert wird.

## <a name="remarks"></a>Hinweise

**_aligned_recalloc** basiert auf **"malloc"**. Weitere Informationen zur Verwendung von **_aligned_offset_malloc**, finden Sie unter ["malloc"](malloc.md).

Diese Funktion legt **Errno** auf **ENOMEM** , wenn die speicherbelegung fehlgeschlagen ist oder wenn die angeforderte Größe größer war **_HEAP_MAXREQ**. Weitere Informationen zu **Errno**, finden Sie unter [Errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Darüber hinaus **_aligned_recalloc** überprüft die eigenen Parameter. Wenn *Ausrichtung* ist keine Potenz von 2, ruft diese Funktion den Handler für ungültige Parameter wie beschrieben in [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Diese Funktion gibt zurück, wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, **NULL** und legt **Errno** auf **EINVAL**.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_aligned_recalloc**|\<malloc.h>|

## <a name="see-also"></a>Siehe auch

[Datenausrichtung](../../c-runtime-library/data-alignment.md)<br/>
[_recalloc](recalloc.md)<br/>
[_aligned_offset_recalloc](aligned-offset-recalloc.md)<br/>
