---
title: _get_printf_count_output
ms.date: 11/04/2016
apiname:
- _get_printf_count_output
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- get_printf_count_output
- _get_printf_count_output
helpviewer_keywords:
- '%n format'
- get_printf_count_output function
- _get_printf_count_output function
ms.assetid: 850f9f33-8319-433e-98d8-6a694200d994
ms.openlocfilehash: 477e4a9e987f27bd70b9707e91b9ea9d84b69993
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50610634"
---
# <a name="getprintfcountoutput"></a>_get_printf_count_output

Gibt an, ob [Printf, _printf_l, Wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)-Familie Funktionen unterstützen die **%n** Format.

## <a name="syntax"></a>Syntax

```C
int _get_printf_count_output();
```

## <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn **%n** wird unterstützt, 0, wenn **%n** wird nicht unterstützt.

## <a name="remarks"></a>Hinweise

Wenn **%n** wird nicht unterstützt (Standard), auftreten **%n** in der Formatzeichenfolge eines der **Printf** Funktionen werden der Handler für ungültige Parameter aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn **%n** -Unterstützung aktiviert ist (finden Sie unter [_set_printf_count_output](set-printf-count-output.md)) klicken Sie dann **%n** verhält sich wie beschrieben in [Syntax der Formatangabe: Printf und Wprintf Funktionen](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_get_printf_count_output**|\<stdio.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Siehe das Beispiel für [_set_printf_count_output](set-printf-count-output.md).

## <a name="see-also"></a>Siehe auch

[_set_printf_count_output](set-printf-count-output.md)<br/>
