---
title: _getmaxstdio
ms.date: 11/04/2016
api_name:
- _getmaxstdio
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
- api-ms-win-crt-stdio-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _getmaxstdio
- getmaxstdio
helpviewer_keywords:
- files [C++], number open
- _getmaxstdio function
- getmaxstdio function
- open files, getting number
ms.assetid: 700ca8ce-4a8c-4e00-9467-dfa9d6b831a0
ms.openlocfilehash: cf3f55262e54ec4d5205d08dfcb499f2802ded23
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70955039"
---
# <a name="_getmaxstdio"></a>_getmaxstdio

Gibt die Anzahl der Dateien an, die auf der E/A-Ebene des Streams gleichzeitig geöffnet sein können.

## <a name="syntax"></a>Syntax

```C
int _getmaxstdio( void );
```

## <a name="return-value"></a>Rückgabewert

Gibt eine Zahl zurück, die die Anzahl der gleichzeitig geöffneten Dateien darstellt, die derzeit auf der **stdio** -Ebene zulässig sind.

## <a name="remarks"></a>Hinweise

Verwenden Sie [_setmaxstdio](setmaxstdio.md) , um die Anzahl der gleichzeitig geöffneten Dateien zu konfigurieren, die auf **stdio** -Ebene zulässig sind.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_getmaxstdio**|\<stdio.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_setmaxstdio.c
// The program retrieves the maximum number
// of open files and prints the results
// to the console.

#include <stdio.h>

int main()
{
   printf( "%d\n", _getmaxstdio());

   _setmaxstdio(2048);

   printf( "%d\n", _getmaxstdio());
}
```

```Output
512
2048
```

## <a name="see-also"></a>Siehe auch

[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
