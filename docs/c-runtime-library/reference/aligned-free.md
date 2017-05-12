---
title: _aligned_free | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
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
dev_langs:
- C++
helpviewer_keywords:
- _aligned_free function
- aligned_free function
ms.assetid: ed1ce952-cdfc-4682-85cc-f75d4101603d
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 8ddc662a1d497a419ebbaf0a93bfbf0ec17b664a
ms.contentlocale: de-de
ms.lasthandoff: 03/29/2017

---
# <a name="alignedfree"></a>_aligned_free
Gibt einen Speicherblock frei, der mit [_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md) oder [_aligned_offset_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md) belegt wurde.  
  
## <a name="syntax"></a>Syntax  
  
```  
void _aligned_free (  
   void *memblock  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `memblock`  
 Ein Zeiger auf den Speicherblock, der an die Funktion `_aligned_malloc` oder `_aligned_offset_malloc` zurückgegeben wurde.  
  
## <a name="remarks"></a>Hinweise  
 `_aligned_free` ist als `__declspec(noalias)` gekennzeichnet, d.h., die Funktion ändert keine globalen Variablen. Weitere Informationen finden Sie unter [noalias](../../cpp/noalias.md).  
  
 Diese Funktion überprüft im Gegensatz zu den anderen _aligned-CRT-Funktionen den Parameter nicht. Wenn `memblock` ein `NULL`-Zeiger ist, führt diese Funktion schlicht keine Aktionen aus. Es verändert `errno` nicht und ruft auch keine ungültigen Parametertyphandler auf. Wenn in der Funktion ein Fehler auftritt, weil Sie vorher keine _aligned-Funktion benutzt haben, um den Speicherblock zuzuordnen, oder wenn eine falsche Speicherausrichtung aufgrund eines unvorhergesehenen Problems auftritt, generiert die Funktion einen Debugbericht aus den [_RPT, _RPTF, _RPTW und _RPTFW-Makros](../../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md).  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_aligned_free`|\<malloc.h>|  
  
## <a name="example"></a>Beispiel  
 Weitere Informationen finden Sie unter [_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Datenausrichtung](../../c-runtime-library/data-alignment.md)
