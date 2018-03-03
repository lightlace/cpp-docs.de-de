---
title: _heapadd | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _heapadd
apilocation:
- msvcr100.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr80.dll
- msvcrt.dll
- msvcr110.dll
- msvcr90.dll
apitype: DLLExport
f1_keywords:
- heapadd
- _heapadd
dev_langs:
- C++
helpviewer_keywords:
- _heapadd function
- memory, adding to heaps
- heaps, adding memory
- heapadd function
ms.assetid: 4d691fe2-2763-49f4-afb1-62738b7cd3ff
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9c046f9e26848edbbc609b9f3c729a0654fe3718
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="heapadd"></a>_heapadd
Fügt dem Heap Arbeitsspeicher hinzu.  
  
> [!IMPORTANT]
>  Diese Funktion ist veraltet. Von Visual Studio 2015 an ist sie nicht in der CRT verfügbar.  
  
## <a name="syntax"></a>Syntax  
  
```  
int _heapadd(   
   void *memblock,  
   size_t size   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `memblock`  
 Zeiger auf den Heapspeicher.  
  
 `size`  
 Größe des hinzuzufügenden Speichers in Byte.  
  
## <a name="return-value"></a>Rückgabewert  
 Bei Erfolg gibt `_heapadd` „0“ (null) zurück; andernfalls gibt die Funktion „-1“ zurück und legt `errno` auf `ENOSYS` fest.  
  
 Weitere Informationen zu diesem und anderen Rückgabecodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Hinweise  
 Von Visual C++, Version 4.0, an, wurde die zugrundeliegende Heapstruktur in die C-Laufzeitbibliotheken verschoben, um die neuen Debugfunktionen zu unterstützen. Das hat zur Folge, dass `_heapadd` auf Plattformen, die auf der Win32-API basieren, nicht mehr unterstützt wird.  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|Optionaler Header|  
|-------------|---------------------|---------------------|  
|`_heapadd`|\<malloc.h>|\<errno.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="see-also"></a>Siehe auch  
 [Speicherbelegung](../c-runtime-library/memory-allocation.md)   
 [free](../c-runtime-library/reference/free.md)   
 [_heapchk](../c-runtime-library/reference/heapchk.md)   
 [_heapmin](../c-runtime-library/reference/heapmin.md)   
 [_heapset](../c-runtime-library/heapset.md)   
 [_heapwalk](../c-runtime-library/reference/heapwalk.md)   
 [malloc](../c-runtime-library/reference/malloc.md)   
 [realloc](../c-runtime-library/reference/realloc.md)