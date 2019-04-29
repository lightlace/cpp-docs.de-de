---
title: _set_printf_count_output
ms.date: 11/04/2016
apiname:
- _set_printf_count_output
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
- set_printf_count_output
- _set_printf_count_output
helpviewer_keywords:
- '%n format'
- set_printf_count_output function
- _set_printf_count_output function
ms.assetid: d8259ec5-764e-42d0-9169-72172e95163b
ms.openlocfilehash: 0d4847d850b39c7c03ea92a98499715b1e6a4913
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62356523"
---
# <a name="setprintfcountoutput"></a>_set_printf_count_output

Aktivieren oder Deaktivieren der Unterstützung für die **%n** -Formats in [Printf, _printf_l, Wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)-Familie der Funktionen.

## <a name="syntax"></a>Syntax

```C
int _set_printf_count_output(
   int enable
);
```

### <a name="parameters"></a>Parameter

*enable*<br/>
Ein Wert ungleich NULL aktivieren **%n** zu unterstützen, 0 zum Deaktivieren der **%n** unterstützen.

## <a name="property-valuereturn-value"></a>Eigenschaftswert/Rückgabewert

Der Status der **%n** -Unterstützung vor dem Aufrufen dieser Funktion: ungleich NULL, wenn **%n** -Unterstützung aktiviert wurde, 0, wenn sie deaktiviert wurde.

## <a name="remarks"></a>Hinweise

Aus Sicherheitsgründen, Unterstützung für die **%n** Formatbezeichner ist standardmäßig deaktiviert, in **Printf** und alle seine Varianten. Wenn **%n** gefunden wird in einem **Printf** Formatspezifikation, das Standardverhalten ist, um Handler für ungültige Parameter aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Aufrufen von **_set_printf_count_output** mit einem Argument ungleich 0 führt dazu, dass **Printf**-Familie, interpretieren die Funktionen **%n** Siehe [Format Syntax der Formatangabe: printf- und Wprintf-Funktionen](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

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
