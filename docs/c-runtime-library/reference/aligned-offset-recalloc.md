---
title: _aligned_offset_recalloc | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _aligned_offset_recalloc
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
dev_langs: C++
helpviewer_keywords:
- aligned_offset_recalloc function
- _aligned_offset_recalloc function
ms.assetid: a258f54e-eeb4-4853-96fc-007d710f98e9
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 886b90cd6509978d5af48d7d6be4dc0aa6e02ae9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="alignedoffsetrecalloc"></a>_aligned_offset_recalloc
Ändert die Größe eines Speicherblocks, der mit [_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md) oder [_aligned_offset_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md) belegt ist und den Speicher auf 0 initialisiert.  
  
## <a name="syntax"></a>Syntax  
  
```  
void * _aligned_offset_recalloc(  
   void *memblock,   
   size_t num,   
   size_t size,   
   size_t alignment,  
   size_t offset  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `memblock`  
 Der Zeiger auf den aktuellen Speicherblock.  
  
 `num`  
 Anzahl der Elemente.  
  
 `size`  
 Länge jedes Elements in Bytes.  
  
 `alignment`  
 Der Ausrichtungswert, der eine ganzzahlige Potenz von 2 sein muss.  
  
 `offset`  
 Der Offset in der Speicherbelegung zum Erzwingen der Ausrichtung.  
  
## <a name="return-value"></a>Rückgabewert  
 `_aligned_offset_recalloc` gibt einen leeren Zeiger auf den neu belegten (und möglicherweise verschobenen) Speicherblock zurück. Der Rückgabewert ist `NULL`, wenn die Größe 0 ist und das Pufferargument nicht `NULL` ist oder wenn nicht genügend Speicherplatz vorhanden ist, um den Block auf die vorgegebene Größe auszudehnen. Im ersten Fall wird der ursprüngliche Block freigegeben. Im zweiten Fall wird der ursprüngliche Block nicht geändert. Der Rückgabewert zeigt auf einen Speicherplatz, der für die Speicherung eines beliebigen Objekttyps geeignet ist. Um einen Zeiger auf einen anderen Typ als den leeren zurückzugeben, verwenden Sie eine Typumwandlung für den Rückgabewert.  
  
 `_aligned_offset_recalloc` ist als `__declspec(noalias)` und `__declspec(restrict)` gekennzeichnet, das bedeutet, dass die Funktion globale Variablen definitiv nicht ändert und dass der zurückgegebene Zeiger keinen Alias hat. Weitere Informationen finden Sie unter [noalias](../../cpp/noalias.md) und [restrict](../../cpp/restrict.md).  
  
## <a name="remarks"></a>Hinweise  
 Genau wie [_aligned_offset_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md) erlaubt `_aligned_offset_recalloc` die Ausrichtung einer Struktur an einem Offset innerhalb der Struktur.  
  
 `_aligned_offset_recalloc` ist auf `malloc` basiert. Weitere Informationen über die Verwendung von `_aligned_offset_malloc` finden Sie unter [malloc](../../c-runtime-library/reference/malloc.md). Wenn `memblock` `NULL` ist, ruft die Funktion `_aligned_offset_malloc` intern auf.  
  
 Diese Funktion legt `errno` auf `ENOMEM` fest, wenn die Speicherbelegung fehlgeschlagen ist oder die angeforderte Größe(`num` * `size`) größer als `_HEAP_MAXREQ` war. Weitere Informationen zu `errno` finden Sie unter [errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Darüber hinaus überprüft `_aligned_offset_recalloc` auch die eigenen Parameter. Wenn `alignment` keine Potenz von 2 ist oder `offset` größer als oder gleich der angeforderten Größe und ungleich 0 ist, ruft diese Funktion den Handler für ungültige Parameter auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, gibt diese Funktion `NULL` zurück und stellt `errno` auf `EINVAL` ein.  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`_aligned_offset_recalloc`|\<malloc.h>|  
  
## <a name="see-also"></a>Siehe auch  
 [Datenausrichtung](../../c-runtime-library/data-alignment.md)   
 [_recalloc](../../c-runtime-library/reference/recalloc.md)   
 [_aligned_recalloc](../../c-runtime-library/reference/aligned-recalloc.md)