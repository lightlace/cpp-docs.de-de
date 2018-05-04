---
title: _set_controlfp | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _set_controlfp
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- set_controlfp
- _set_controlfp
dev_langs:
- C++
helpviewer_keywords:
- set_controlfp function
- floating-point functions, setting control word
- _set_controlfp function
ms.assetid: e0689d50-f68a-4028-a9c1-fb23eedee4ad
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a2647e9719c2aa3fe303393fcc1da55de0385581
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="setcontrolfp"></a>_set_controlfp

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

*Maske*<br/>
Maske für festzulegende neue Steuerwortbits.

## <a name="return-value"></a>Rückgabewert

Keine.

## <a name="remarks"></a>Hinweise

Die **_set_controlfp** Funktion ist vergleichbar mit **_control87**, aber es wird nur das gleitkommasteuerwort auf *NewControl*. Die Bits in den Werten geben den Zustand des Gleitkommasteuerelements an. Über den Gleitkommawert-Steuerstatus kann das Programm die Modi für Genauigkeit, Rundung und Unendlichkeit im Paket für Gleitkommaoperationen ändern. Sie können auch zu maskieren bzw. die Maskierung aufzuheben Gleitkommaausnahmen mit **_set_controlfp**. Weitere Informationen finden Sie unter [_control87, _controlfp, \__control87_2](control87-controlfp-control87-2.md).

Diese Funktion ist veraltet, beim Kompilieren mit [/CLR (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md) , da die common Language Runtime nur die standardmäßige Genauigkeit von Gleitkommawerten unterstützt.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|Kompatibilität|
|-------------|---------------------|-------------------|
|**_set_controlfp**|\<float.h>|Nur x86-Prozessor|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[_clear87, _clearfp](clear87-clearfp.md)<br/>
[_status87, _statusfp, _statusfp2](status87-statusfp-statusfp2.md)<br/>
