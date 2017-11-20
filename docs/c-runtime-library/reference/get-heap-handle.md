---
title: _get_heap_handle | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _get_heap_handle
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
- _get_heap_handle
- get_heap_handle
dev_langs: C++
helpviewer_keywords:
- heap functions
- memory allocation, heap memory
- _get_heap_handle function
- get_heap_handle function
ms.assetid: a4d05049-8528-494a-8281-a470d1e1115c
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2e8c08ed0ccffb7196133de89d4b9588333e1bfa
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="getheaphandle"></a>_get_heap_handle
Gibt das Handle des Heaps zurück, der vom C-Laufzeitsystem verwendet wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
intptr_t _get_heap_handle( void );  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt das Handle an den Win32-Heap zurück, der vom C-Laufzeitsystem verwendet wird.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion, wenn Sie [HeapSetInformation](http://msdn.microsoft.com/library/windows/desktop/aa366705) aufrufen und niedrige Heap-Fragmentierung auf dem CRT-Heap aktivieren möchten.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_get_heap_handle`|\<malloc.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="sample"></a>Beispiel  
  
```  
// crt_get_heap_handle.cpp  
// compile with: /MT  
#include <windows.h>  
#include <malloc.h>  
#include <stdio.h>  
  
int main(void)  
{  
    intptr_t hCrtHeap = _get_heap_handle();  
    ULONG ulEnableLFH = 2;  
    if (HeapSetInformation((PVOID)hCrtHeap,  
                           HeapCompatibilityInformation,  
                           &ulEnableLFH, sizeof(ulEnableLFH)))  
        puts("Enabling Low Fragmentation Heap succeeded");  
    else  
        puts("Enabling Low Fragmentation Heap failed");  
    return 0;  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Speicherbelegung](../../c-runtime-library/memory-allocation.md)