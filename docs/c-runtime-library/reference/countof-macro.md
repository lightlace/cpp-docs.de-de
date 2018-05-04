---
title: _countof-Makro | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/22/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- countof macro
- _countof macro
ms.assetid: 86198767-f7e5-4beb-898d-3cbbf60350a3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f30df64b045e2af6181d343a4eafb962d22eaa05
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
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

Die Anzahl der Elemente im Array, ausgedrückt als eine **Size_t**.

## <a name="remarks"></a>Hinweise

**_countof** wird als ein Präprozessormakro funktionsähnliche implementiert. Die C++-Version verfügt über zusätzliche Vorlage-Maschinen, die zur Kompilierzeit zu erkennen, wenn ein Zeiger anstelle eines Arrays statisch deklarierte übergeben wird.

Sicherstellen, dass *Array* ist tatsächlich ein Array, kein Zeiger. In C **_countof** fehlerhafte Ergebnisse erzeugt, wenn *Array* ist ein Zeiger. In C++ **_countof** schlägt fehl, wenn die Kompilierung *Array* ist ein Zeiger.  Ein Array als Parameter an eine Funktion übergeben *unumgänglich in einen Zeiger*, was bedeutet, dass innerhalb der Funktion Verwendung nicht möglich **_countof** um den Umfang des Arrays ermitteln.

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
