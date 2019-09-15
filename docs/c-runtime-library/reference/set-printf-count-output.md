---
title: _set_printf_count_output
ms.date: 11/04/2016
api_name:
- _set_printf_count_output
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
- set_printf_count_output
- _set_printf_count_output
helpviewer_keywords:
- '%n format'
- set_printf_count_output function
- _set_printf_count_output function
ms.assetid: d8259ec5-764e-42d0-9169-72172e95163b
ms.openlocfilehash: 0d53b4e4c56a69582a4eb517fa1a5c9e10cd7d2f
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70948424"
---
# <a name="_set_printf_count_output"></a>_set_printf_count_output

Aktivieren oder deaktivieren Sie die Unterstützung des **% n** -Formats in den Funktionen [printf, _printf_l, wprintf und _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)-Family.

## <a name="syntax"></a>Syntax

```C
int _set_printf_count_output(
   int enable
);
```

### <a name="parameters"></a>Parameter

*fähigen*<br/>
Ein Wert ungleich Null zum Aktivieren der **% n** -Unterstützung, 0 zum Deaktivieren der **% n** -Unterstützung.

## <a name="property-valuereturn-value"></a>Eigenschaftswert/Rückgabewert

Der Status der **% n** -Unterstützung vor dem Aufrufen dieser Funktion: ungleich 0 (null), wenn die **% n** -Unterstützung aktiviert war, 0, wenn Sie deaktiviert wurde

## <a name="remarks"></a>Hinweise

Aus Sicherheitsgründen ist die Unterstützung für den Format Bezeichner " **% n** " in **printf** und allen Varianten standardmäßig deaktiviert. Wenn **% n** in einer **printf** -Format Spezifikation gefunden wird, wird standardmäßig der Handler für ungültige Parameter aufgerufen, wie in [Parameter Validation (Parameter](../../c-runtime-library/parameter-validation.md)Überprüfung) beschrieben. Das Aufrufen von **_set_printf_count_output** mit einem Argument ungleich NULL bewirkt, dass die Funktionen der **printf**-Familie " **% n** " interpretieren, wie in [formatspezifikations Syntax: printf-und wprintf-Funktionen](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)beschrieben.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_set_printf_count_output**|\<stdio.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_set_printf_count_output.c
#include <stdio.h>

int main()
{
   int e;
   int i;
   e = _set_printf_count_output( 1 );
   printf( "%%n support was %sabled.\n",
        e ? "en" : "dis" );
   printf( "%%n support is now %sabled.\n",
        _get_printf_count_output() ? "en" : "dis" );
   printf( "12345%n6789\n", &i ); // %n format should set i to 5
   printf( "i = %d\n", i );
}
```

```Output
%n support was disabled.
%n support is now enabled.
123456789
i = 5
```

## <a name="see-also"></a>Siehe auch

[_get_printf_count_output](get-printf-count-output.md)<br/>
