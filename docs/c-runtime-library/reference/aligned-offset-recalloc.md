---
title: _aligned_offset_recalloc | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _aligned_offset_recalloc
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
- aligned_offset_recalloc
- _aligned_offset_recalloc
dev_langs:
- C++
helpviewer_keywords:
- aligned_offset_recalloc function
- _aligned_offset_recalloc function
ms.assetid: a258f54e-eeb4-4853-96fc-007d710f98e9
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 23e3fdf431a270211cba3a4552d7df4affc46ca4
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="alignedoffsetrecalloc"></a>_aligned_offset_recalloc

Ändert die Größe eines Speicherblocks, der mit [_aligned_malloc](aligned-malloc.md) oder [_aligned_offset_malloc](aligned-offset-malloc.md) belegt ist und den Speicher auf 0 initialisiert.

## <a name="syntax"></a>Syntax

```C
void * _aligned_offset_recalloc(
   void *memblock,
   size_t num,
   size_t size,
   size_t alignment,
   size_t offset
);
```

### <a name="parameters"></a>Parameter

*memblock*<br/>
Der Zeiger auf den aktuellen Speicherblock.

*Anzahl*<br/>
Anzahl der Elemente.

*size*<br/>
Länge jedes Elements in Bytes.

*Ausrichtung*<br/>
Der Ausrichtungswert, der eine ganzzahlige Potenz von 2 sein muss.

*offset*<br/>
Der Offset in der Speicherbelegung zum Erzwingen der Ausrichtung.

## <a name="return-value"></a>Rückgabewert

**_aligned_offset_recalloc** gibt einen void-Zeiger auf den neu belegten (und möglicherweise verschobenen) Speicherblock zurück. Der Rückgabewert ist **NULL** Wenn die Größe 0 (null beträgt) und das pufferargument nicht **NULL**, oder es ist nicht genügend Arbeitsspeicher verfügbar, um den Block auf die vorgegebene Größe auszudehnen. Im ersten Fall wird der ursprüngliche Block freigegeben. Im zweiten Fall wird der ursprüngliche Block nicht geändert. Der Rückgabewert zeigt auf einen Speicherplatz, der für die Speicherung eines beliebigen Objekttyps geeignet ist. Um einen Zeiger auf einen anderen Typ als den leeren zurückzugeben, verwenden Sie eine Typumwandlung für den Rückgabewert.

**_aligned_offset_recalloc** RuntimeCompatibility `__declspec(noalias)` und `__declspec(restrict)`, was bedeutet, dass die Funktion garantiert nicht, so ändern Sie globale Variablen und der zurückgegebene Zeiger keinen Alias. Weitere Informationen finden Sie unter [noalias](../../cpp/noalias.md) und [restrict](../../cpp/restrict.md).

## <a name="remarks"></a>Hinweise

Wie [_aligned_offset_malloc](aligned-offset-malloc.md), **_aligned_offset_recalloc** eine Struktur, die an einem Offset innerhalb der Struktur ausgerichtet werden können.

**_aligned_offset_recalloc** basiert auf **"malloc"**. Weitere Informationen zur Verwendung von **_aligned_offset_malloc**, finden Sie unter ["malloc"](malloc.md). Wenn *Memblock* ist **NULL**, die Funktionsaufrufe **_aligned_offset_malloc** intern.

Diese Funktion legt **Errno** auf **ENOMEM** , wenn die speicherbelegung fehlgeschlagen ist oder wenn die angeforderte Größe (*Anzahl* * *Größe* ) war größer als **_HEAP_MAXREQ**. Weitere Informationen zu **Errno**, finden Sie unter [Errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Darüber hinaus **_aligned_offset_recalloc** überprüft die eigenen Parameter. Wenn *Ausrichtung* Potenz von 2 ist oder wenn *Offset* ist größer als oder gleich der angeforderten Größe und ungleich NULL ist, ruft diese Funktion den Handler für ungültige Parameter aus, wie in beschrieben [Parameter Überprüfung](../../c-runtime-library/parameter-validation.md). Diese Funktion gibt zurück, wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, **NULL** und legt **Errno** auf **EINVAL**.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_aligned_offset_recalloc**|\<malloc.h>|

## <a name="see-also"></a>Siehe auch

[Datenausrichtung](../../c-runtime-library/data-alignment.md)<br/>
[_recalloc](recalloc.md)<br/>
[_aligned_recalloc](aligned-recalloc.md)<br/>
