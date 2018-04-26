---
title: _set_printf_count_output | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- '%n format'
- set_printf_count_output function
- _set_printf_count_output function
ms.assetid: d8259ec5-764e-42d0-9169-72172e95163b
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 505d87a98ed212a4be7e23a05127686b370c9176
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="setprintfcountoutput"></a>_set_printf_count_output

Aktivieren oder Deaktivieren der Unterstützung für die **%n** in formatieren [Printf, _printf_l, Wprintf _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)-Familie Funktionen.

## <a name="syntax"></a>Syntax

```C
int _set_printf_count_output(
   int enable
);
```

### <a name="parameters"></a>Parameter

*Aktivieren Sie* einen Wert ungleich 0 (null), aktivieren Sie **%n** zu unterstützen, 0 zum Deaktivieren der **%n** unterstützen.

## <a name="property-valuereturn-value"></a>Eigenschaftswert/Rückgabewert

Der Status der **%n** vor dem Aufrufen dieser Funktion zu unterstützen: If ungleich NULL **%n** Unterstützung wurde aktiviert, 0, wenn er deaktiviert wurde.

## <a name="remarks"></a>Hinweise

Aus Gründen der Sicherheit unterstützt, für die **%n** Formatbezeichner ist standardmäßig deaktiviert, in **Printf** und alle seine Varianten. Wenn **%n** festgestellt wird, einem **Printf** Formatangabe ist das Standardverhalten wird der Handler für ungültige Parameter aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Aufrufen von **_set_printf_count_output** mit einem Argument ungleich 0 führt dazu, dass **Printf**-Produktfamilie Funktionen interpretieren **%n** wie beschrieben in [Format Syntax der Formatangabe: printf- und Wprintf-Funktionen](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
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
