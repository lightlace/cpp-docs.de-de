---
title: _get_output_format
ms.date: 11/04/2016
api_name:
- _get_output_format
api_location:
- msvcr110_clr0400.dll
- msvcr100.dll
- msvcr80.dll
- msvcrt.dll
- msvcr90.dll
- msvcr120.dll
- msvcr110.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- get_output_format
- _get_output_format
helpviewer_keywords:
- output formatting
- get_output_format function
- _get_output_format function
ms.assetid: 0ce42f3b-3479-41c4-bcbf-1d21f7ee37e7
ms.openlocfilehash: 20afa988bc4fdf3bc3a6ff073a48a1cc00ff84c5
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70944369"
---
# <a name="_get_output_format"></a>_get_output_format

Ruft den aktuellen Wert des Ausgabeformatkennzeichens ab.

> [!IMPORTANT]
>  Diese Funktion ist veraltet. Von Visual Studio 2015 an ist sie nicht in der CRT verfügbar.

## <a name="syntax"></a>Syntax

```
unsigned int _get_output_format();
```

## <a name="return-value"></a>Rückgabewert

Der aktuelle Wert des Ausgabeformatkennzeichens.

## <a name="remarks"></a>Anmerkungen

Das Ausgabeformatkennzeichen steuert Funktionen von formatierter E/A. Derzeit hat das Kennzeichen zwei mögliche Werte: 0 und `_TWO_DIGIT_EXPONENT`. Wenn `_TWO_DIGIT_EXPONENT` festgelegt ist, werden Gleitkommazahlen mit nur zwei Stellen im Exponenten gedruckt, es sei denn, eine dritte Stelle ist aufgrund der Größe des Exponenten erforderlich. Wenn das Kennzeichen den Wert 0 hat, wird in der Gleitkommadarstellung ein dreistelliger Exponent angezeigt, der ggf. mit Nullen aufgefüllt wird.

## <a name="requirements"></a>Requirements (Anforderungen)

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|`_get_output_format`|\<stdio.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../c-runtime-library/compatibility.md) in der Einführung.

## <a name="see-also"></a>Siehe auch

[Syntax der Formatangabe: printf- und wprintf-Funktionen](../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)<br/>
[printf_s, _printf_s_l, wprintf_s, _wprintf_s_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)<br/>
[_set_output_format](../c-runtime-library/set-output-format.md)
