---
title: _freea | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: bd53960a97cc6647008b683e354df664941428e9
ms.contentlocale: de-de
ms.lasthandoff: 04/04/2017

---
# <a name="freea"></a>_freea
Hebt die Zuweisung eines Speicherblocks auf oder gibt diesen frei.  
  
## <a name="syntax"></a>Syntax  
  
```  
void _freea(   
   void *memblock   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `memblock`  
 Zuvor zugewiesener Speicherblock, der freigegeben werden soll.  
  
## <a name="return-value"></a>Rückgabewert  
 Keine.  
  
## <a name="remarks"></a>Hinweise  
 Die Funktion `_freea` gibt einen Speicherblock frei (`memblock`), der zuvor durch einen Aufruf von [_malloca](../../c-runtime-library/reference/malloca.md) belegt wurde. `_freea` überprüft, ob der Speicher auf dem Heap oder Stapel belegt wurde. Wenn Speicher auf dem Stapel belegt wurde, führt `_freea` keine Aktion aus. Wenn Speicher auf dem Heap belegt wurde, entspricht die Anzahl der freigegebenen Bytes der Anzahl der Bytes, die angefordert wurden, als der Block belegt wurde. Wenn `memblock` `NULL` ist, wird der Zeiger ignoriert und `_freea` wird sofort zurückgegeben. Der Versuch, einen ungültigen Zeiger freizugeben (einen Zeiger auf einen Speicherblock, der nicht von `_malloca` belegt wurde), kann nachfolgende Zuordnungsanforderungen beeinflussen und Fehler verursachen.  
  
 `_freea`Aufrufe `free` intern verwendet werden, wenn er feststellt, dass der Arbeitsspeicher auf dem Heap zugeordnet wird. Ein Marker bestimmt im Speicher an der Adresse, die dem zugewiesenen Speicher unmittelbar vorausgeht, ob der Speicher auf dem Heap oder dem Stapel belegt wird.  
  
 Wenn bei der Freigabe des Speichers ein Fehler auftritt, wird `errno` mit Informationen des Betriebssystems über die Art des Fehlers angegeben. Weitere Informationen finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Nachdem ein Speicherblock freigegeben wurde, minimiert [_heapmin](../../c-runtime-library/reference/heapmin.md) die Menge des freien Speicherplatzes auf dem Heap, indem die nicht verwendeten Bereiche zusammengefügt und wieder an das Betriebssystem freigegeben werden. Freigegebener Speicher, der nicht an das Betriebssystem freigegeben wird, wird im freien Pool wiederhergestellt und ist wieder für eine Zuordnung verfügbar.  
  
 Alle Aufrufe von `_malloca` müssen von einem Aufruf von `_freea` begleitet werden. Es ist auch ein Fehler, `_freea` zweimal im gleichen Speicher aufzurufen. Wenn die Anwendung mit einer Debugversion der C-Laufzeitbibliotheken verknüpft ist, vor allem mit [_malloc_dbg](../../c-runtime-library/reference/malloc-dbg.md)-Funktionen, die durch die Definition von `_CRTDBG_MAP_ALLOC` aktiviert werden, ist es einfacher, fehlende oder duplizierte Aufrufe von `_freea` zu finden. Weitere Informationen dazu, wie der Heap während des Debugprozesses verwaltet wird, finden Sie unter [CRT-Debugheap](/visualstudio/debugger/crt-debug-heap-details).  
  
 `_freea` ist als `__declspec(noalias)` gekennzeichnet, d.h., die Funktion ändert auf keinen Fall globale Variablen. Weitere Informationen finden Sie unter [noalias](../../cpp/noalias.md).  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------|  
|`_freea`|\<stdlib.h> und \<malloc.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
 Siehe das Beispiel für [_malloca](../../c-runtime-library/reference/malloca.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Memory Allocation (Speicherreservierung)](../../c-runtime-library/memory-allocation.md)   
 [_malloca](../../c-runtime-library/reference/malloca.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [_malloc_dbg](../../c-runtime-library/reference/malloc-dbg.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [_free_dbg](../../c-runtime-library/reference/free-dbg.md)   
 [_heapmin](../../c-runtime-library/reference/heapmin.md)
