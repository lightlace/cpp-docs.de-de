---
title: _get_heap_handle
ms.date: 11/04/2016
apiname:
- _get_heap_handle
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
helpviewer_keywords:
- heap functions
- memory allocation, heap memory
- _get_heap_handle function
- get_heap_handle function
ms.assetid: a4d05049-8528-494a-8281-a470d1e1115c
ms.openlocfilehash: 7e82686c4b33dc11f02f387a97966d3ff5a47085
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69499926"
---
# <a name="_get_heap_handle"></a>_get_heap_handle

Gibt das Handle des Heaps zurück, der vom C-Laufzeitsystem verwendet wird.

## <a name="syntax"></a>Syntax

```C
intptr_t _get_heap_handle( void );
```

## <a name="return-value"></a>Rückgabewert

Gibt das Handle an den Win32-Heap zurück, der vom C-Laufzeitsystem verwendet wird.

## <a name="remarks"></a>Hinweise

Verwenden Sie diese Funktion, wenn Sie [HeapSetInformation](/windows/win32/api/heapapi/nf-heapapi-heapsetinformation) aufrufen und niedrige Heap-Fragmentierung auf dem CRT-Heap aktivieren möchten.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_get_heap_handle**|\<malloc.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="sample"></a>Beispiel

```cpp
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

[Speicherreservierung](../../c-runtime-library/memory-allocation.md)<br/>
