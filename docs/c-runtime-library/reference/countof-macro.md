---
title: _countof-Makro
ms.date: 03/22/2018
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
- _countof
- countof
helpviewer_keywords:
- countof macro
- _countof macro
ms.assetid: 86198767-f7e5-4beb-898d-3cbbf60350a3
ms.openlocfilehash: 60b4350d6cf14a545de67de0bdaee70ee2099006
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50536135"
---
# <a name="countof-macro"></a>_countof-Makro

Berechnet die Anzahl der Elemente in einem statisch zugeordneten Array.

## <a name="syntax"></a>Syntax

```C
#define _countof(array) (sizeof(array) / sizeof(array[0]))
```

### <a name="parameters"></a>Parameter

*array*<br/>
Der Name eines Arrays.

## <a name="return-value"></a>Rückgabewert

Die Anzahl der Elemente im Array fest, ausgedrückt als eine **"size_t"**.

## <a name="remarks"></a>Hinweise

**_countof** wird als ein Präprozessormakro funktionsähnliches implementiert. Die C++-Version verfügt über zusätzliche Vorlagen Mechanismen zum Zeitpunkt der Kompilierung zu erkennen, wenn ein Zeiger anstelle eines Arrays statisch deklarierte übergeben wird.

Sicherstellen, dass *Array* ist tatsächlich ein Array, kein Zeiger. In C **_countof** fehlerhafte Ergebnisse erzeugt, wenn *Array* ist ein Zeiger. In C++ **_countof** kann nicht kompiliert werden Wenn *Array* ist ein Zeiger.  Ein Array als Parameter an eine Funktion übergeben *unumgänglich in einen Zeiger*, was bedeutet, dass in der Funktion wird keine **_countof** um das Ausmaß des Arrays zu ermitteln.

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
