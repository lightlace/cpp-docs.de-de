---
title: _set_controlfp
ms.date: 04/05/2018
api_name:
- _set_controlfp
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
- api-ms-win-crt-runtime-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- set_controlfp
- _set_controlfp
helpviewer_keywords:
- set_controlfp function
- floating-point functions, setting control word
- _set_controlfp function
ms.assetid: e0689d50-f68a-4028-a9c1-fb23eedee4ad
ms.openlocfilehash: 4d39406db0f4c9ba6374776da62aea2dbb61e23d
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70948684"
---
# <a name="_set_controlfp"></a>_set_controlfp

Legt das Gleitkommasteuerwort fest.

## <a name="syntax"></a>Syntax

```C
void __cdecl _set_controlfp(
    unsigned int newControl,
    unsigned int mask
);
```

### <a name="parameters"></a>Parameter

*newControl*<br/>
Neue Bitwerte des Steuerworts.

*chel*<br/>
Maske für festzulegende neue Steuerwortbits.

## <a name="return-value"></a>Rückgabewert

Keine.

## <a name="remarks"></a>Hinweise

Die **_set_controlfp** -Funktion ähnelt **_control87**, aber Sie legt nur das Gleit Komma Steuerwort auf *newControl*fest. Die Bits in den Werten geben den Zustand des Gleitkommasteuerelements an. Über den Gleitkommawert-Steuerstatus kann das Programm die Modi für Genauigkeit, Rundung und Unendlichkeit im Paket für Gleitkommaoperationen ändern. Sie können auch Gleit Komma Ausnahmen mithilfe von **_set_controlfp**maskieren oder aufheben. Weitere Informationen finden Sie unter [_control87, _controlfp, \__control87_2](control87-controlfp-control87-2.md).

Diese Funktion ist als veraltet markiert, wenn die Kompilierung mit [/CLR (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md) erfolgt, da die Common Language Runtime nur die standardmäßige Gleit Komma Genauigkeit unterstützt.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|Kompatibilität|
|-------------|---------------------|-------------------|
|**_set_controlfp**|\<float.h>|Nur x86-Prozessor|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[_clear87, _clearfp](clear87-clearfp.md)<br/>
[_status87, _statusfp, _statusfp2](status87-statusfp-statusfp2.md)<br/>
