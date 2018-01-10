---
title: _aligned_offset_malloc | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _aligned_offset_malloc
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
- _aligned_offset_malloc
- aligned_offset_malloc
dev_langs: C++
helpviewer_keywords:
- _aligned_offset_malloc function
- aligned_offset_malloc function
ms.assetid: 447681a3-7c95-4655-86ba-fa3a4ca4c521
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 12bb22245619931732d08d3239c89380471f11b2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="alignedoffsetmalloc"></a>_aligned_offset_malloc
Weist Speicher mit einer definierten Zuweisungsgrenze zu.  
  
## <a name="syntax"></a>Syntax  
  
```  
void * _aligned_offset_malloc(  
   size_t size,   
   size_t alignment,   
   size_t offset  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 [in] `size`  
 Die Größe der angeforderten Speicherbelegung.  
  
 [in] `alignment`  
 Der Ausrichtungswert, der eine ganzzahlige Potenz von 2 sein muss.  
  
 [in] `offset`  
 Der Offset in der Speicherbelegung zum Erzwingen der Ausrichtung.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Zeiger zum Speicherblock, der belegt wurde, oder `NULL`bei fehlgeschlagenem Vorgang.  
  
## <a name="remarks"></a>Hinweise  
 `_aligned_offset_malloc` ist nützlich in Situationen, in denen eine Ausrichtung für ein geschachteltes Element erforderlich ist, beispielsweise wenn eine Ausrichtung für eine geschachtelte Klasse erforderlich war.  
  
 `_aligned_offset_malloc` basiert auf `malloc`. Weitere Informationen finden Sie unter [malloc](../../c-runtime-library/reference/malloc.md).  
  
 `_aligned_offset_malloc` ist als `__declspec(noalias)` und `__declspec(restrict)` gekennzeichnet, das bedeutet, dass die Funktion globale Variablen definitiv nicht ändert und dass der zurückgegebene Zeiger keinen Alias hat. Weitere Informationen finden Sie unter [noalias](../../cpp/noalias.md) und [restrict](../../cpp/restrict.md).  
  
 Diese Funktion legt `errno` auf `ENOMEM` fest, wenn die Speicherbelegung fehlgeschlagen ist oder die angeforderte Größe größer als `_HEAP_MAXREQ` war. Weitere Informationen zu `errno` finden Sie unter [errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Darüber hinaus überprüft `_aligned_offset_malloc` auch die eigenen Parameter. Wenn `alignment` keine Potenz von 2 ist oder `offset` größer als oder gleich `size` und ungleich 0 ist, ruft diese Funktion den ungültigen Parameterhandler auf, wie unter [Parametervalidation](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, gibt diese Funktion `NULL` zurück und stellt `errno` auf `EINVAL` ein.  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`_aligned_offset_malloc`|\<malloc.h>|  
  
## <a name="example"></a>Beispiel  
 Weitere Informationen finden Sie unter [_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Datenausrichtung](../../c-runtime-library/data-alignment.md)