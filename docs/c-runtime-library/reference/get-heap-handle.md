---
title: _get_heap_handle | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- heap functions
- memory allocation, heap memory
- _get_heap_handle function
- get_heap_handle function
ms.assetid: a4d05049-8528-494a-8281-a470d1e1115c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 238fab4ec2d900c8183c018f3cb03fe6dc1fb2f5
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43202233"
---
# <a name="getheaphandle"></a>_get_heap_handle

Gibt das Handle des Heaps zurück, der vom C-Laufzeitsystem verwendet wird.

## <a name="syntax"></a>Syntax

```C
intptr_t _get_heap_handle( void );
```

## <a name="return-value"></a>Rückgabewert

Gibt das Handle an den Win32-Heap zurück, der vom C-Laufzeitsystem verwendet wird.

## <a name="remarks"></a>Hinweise

Verwenden Sie diese Funktion, wenn Sie [HeapSetInformation](/windows/desktop/api/heapapi/nf-heapapi-heapsetinformation) aufrufen und niedrige Heap-Fragmentierung auf dem CRT-Heap aktivieren möchten.

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
