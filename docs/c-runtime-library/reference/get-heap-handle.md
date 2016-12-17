---
title: "_get_heap_handle"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "_get_heap_handle"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-heap-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_get_heap_handle"
  - "get_heap_handle"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Heapfunktionen"
  - "speicherbelegung, Heapspeicher"
  - "_get_heap_handle-Funktion"
  - "get_heap_handle-Funktion"
ms.assetid: a4d05049-8528-494a-8281-a470d1e1115c
caps.latest.revision: 16
caps.handback.revision: "16"
ms.author: "corob"
manager: "ghogen"
---
# _get_heap_handle
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt das Handle des Heaps zurück, der vom C\-Laufzeitsystem verwendet wird.  
  
## Syntax  
  
```  
intptr_t _get_heap_handle( void );  
```  
  
## Rückgabewert  
 Gibt das Handle an den Win32\-Heap zurück, der vom C\-Laufzeitsystem verwendet wird.  
  
## Hinweise  
 Verwenden Sie diese Funktion, wenn Sie [HeapSetInformation](http://msdn.microsoft.com/library/windows/desktop/aa366705) aufrufen und niedrige Heap\-Fragmentierung auf dem CRT\-Heap aktivieren möchten.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_get_heap_handle`|\<malloc.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
  
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
  
## Siehe auch  
 [Speicherbelegung](../../c-runtime-library/memory-allocation.md)