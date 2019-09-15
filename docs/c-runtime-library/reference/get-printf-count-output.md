---
title: _get_printf_count_output
ms.date: 11/04/2016
api_name:
- _get_printf_count_output
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
- get_printf_count_output
- _get_printf_count_output
helpviewer_keywords:
- '%n format'
- get_printf_count_output function
- _get_printf_count_output function
ms.assetid: 850f9f33-8319-433e-98d8-6a694200d994
ms.openlocfilehash: 15b37ac759821ad56cc5c03c9b98719d8f0cc19a
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70955708"
---
# <a name="_get_printf_count_output"></a>_get_printf_count_output

Gibt an, ob die Funktionen [printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)-Family das **% n** -Format unterstützen.

## <a name="syntax"></a>Syntax

```C
int _get_printf_count_output();
```

## <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn **% n** unterstützt wird, 0, wenn **% n** nicht unterstützt wird.

## <a name="remarks"></a>Hinweise

Wenn **% n** nicht unterstützt wird (Standardeinstellung), ruft **% n** in der Format Zeichenfolge der **printf** -Funktionen auf, wie in [Parameter Validation (Parameter](../../c-runtime-library/parameter-validation.md)Überprüfung) beschrieben, wird der Handler für ungültige Parameter aufgerufen. Wenn die **% n** -Unterstützung aktiviert ist (siehe [_set_printf_count_output](set-printf-count-output.md)), verhält sich **% n** wie in [Format Spezifikations Syntax: printf-und wprintf-Funktionen](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)beschrieben.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_get_printf_count_output**|\<stdio.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Siehe das Beispiel für [_set_printf_count_output](set-printf-count-output.md).

## <a name="see-also"></a>Siehe auch

[_set_printf_count_output](set-printf-count-output.md)<br/>
