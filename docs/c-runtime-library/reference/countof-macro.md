---
title: _countof-Makro
ms.date: 03/22/2018
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _countof
- countof
helpviewer_keywords:
- countof macro
- _countof macro
ms.assetid: 86198767-f7e5-4beb-898d-3cbbf60350a3
ms.openlocfilehash: 3debd63da7d218e29f31847034c69d89b4691643
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70942690"
---
# <a name="_countof-macro"></a>_countof-Makro

Berechnet die Anzahl von Elementen in einem statisch zugeordneten Array.

## <a name="syntax"></a>Syntax

```C
#define _countof(array) (sizeof(array) / sizeof(array[0]))
```

### <a name="parameters"></a>Parameter

*array*<br/>
Der Name eines Arrays.

## <a name="return-value"></a>Rückgabewert

Die Anzahl der Elemente im Array, ausgedrückt als **size_t**.

## <a name="remarks"></a>Hinweise

**_countof** wird als ein Funktions ähnliches Präprozessormakro implementiert. Die C++ Version verfügt über zusätzliche Vorlagen Mechanismen, die zur Kompilierzeit erkannt werden, wenn ein Zeiger anstelle eines statisch deklarierten Arrays an Sie übermittelt wird.

Stellen Sie sicher, dass *Array* tatsächlich ein Array und kein Zeiger ist. In C erzeugt **_countof** fehlerhafte Ergebnisse, wenn *Array* ein Zeiger ist. In C++kann **_countof** nicht kompiliert werden, wenn *Array* ein Zeiger ist.  Ein Array, das als Parameter an eine Funktion übergeben wird, wird *zu einem Zeiger*. Dies bedeutet, dass Sie innerhalb der Funktion **_countof** nicht verwenden können, um den Umfang des Arrays zu ermitteln.

## <a name="requirements"></a>Anforderungen

|Makro|Erforderlicher Header|
|-----------|---------------------|
|**_countof**|\<stdlib.h>|

## <a name="example"></a>Beispiel

```cpp
// crt_countof.cpp
#define _UNICODE
#include <stdio.h>
#include <stdlib.h>
#include <tchar.h>

int main( void )
{
   _TCHAR arr[20], *p;
   printf( "sizeof(arr) = %zu bytes\n", sizeof(arr) );
   printf( "_countof(arr) = %zu elements\n", _countof(arr) );
   // In C++, the following line would generate a compile-time error:
   // printf( "%zu\n", _countof(p) ); // error C2784 (because p is a pointer)

   _tcscpy_s( arr, _countof(arr), _T("a string") );
   // unlike sizeof, _countof works here for both narrow- and wide-character strings
}
```

```Output
sizeof(arr) = 40 bytes
_countof(arr) = 20 elements
```

## <a name="see-also"></a>Siehe auch

[sizeof-Operator](../../cpp/sizeof-operator.md)<br/>
