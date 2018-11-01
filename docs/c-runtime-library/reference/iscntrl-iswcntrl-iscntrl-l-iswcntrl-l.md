---
title: iscntrl, iswcntrl, _iscntrl_l, _iswcntrl_l
ms.date: 11/04/2016
apiname:
- iscntrl
- _iswcntrl_l
- _iscntrl_l
- iswcntrl
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _istcntrl_l
- _iswcntrl_l
- iswcntrl
- _iscntrl_l
- iscntrl
- _istcntrl
helpviewer_keywords:
- iscntrl function
- _iscntrl_l function
- _iswcntrl_l function
- _istcntrl function
- istcntrl function
- iswcntrl function
- _istcntrl_l function
ms.assetid: 616eebf9-aed4-49ba-ba2c-8677c8fe6fb5
ms.openlocfilehash: 150073e78426f5029dd46cbc6766fbd6a2a242e1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50506751"
---
# <a name="iscntrl-iswcntrl-iscntrll-iswcntrll"></a>iscntrl, iswcntrl, _iscntrl_l, _iswcntrl_l

Bestimmt, ob eine ganze Zahl ein Steuerzeichen darstellt.

## <a name="syntax"></a>Syntax

```C
int iscntrl(
   int c
);
int iswcntrl(
   wint_t c
);
int _iscntrl_l(
   int c,
   _locale_t locale
);
int _iswcntrl_l(
   wint_t c,
   _locale_t locale
);
```

### <a name="parameters"></a>Parameter

*c*<br/>
Zu testende ganze Zahl

*locale*<br/>
Das zu verwendende Gebietsschema.

## <a name="return-value"></a>Rückgabewert

Jede dieser Routinen gibt ungleich NULL, wenn *c* eine bestimmte Darstellung eines Steuerzeichens ist. **Iscntrl** gibt einen Wert ungleich NULL zurück, wenn *c* ein Steuerzeichen ist (0 x 00-0x1F oder 0x7F). **Iswcntrl** gibt einen Wert ungleich NULL zurück, wenn *c* ist ein Steuerelement Breitzeichen. Jede dieser Routinen gibt 0 zurück, wenn *c* die testbedingung nicht erfüllt.

Die Versionen dieser Funktionen, die **_l** -Suffix verwenden den Gebietsschemaparameter, der übergeben wird, anstelle des aktuellen Gebietsschemas. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

Das Verhalten der **Iscntrl** und **_iscntrl_l** ist undefiniert, wenn *c* nicht EOF-Markierung ist oder im Bereich von 0 bis 0xFF liegt. Wenn eine CRT-Debugbibliothek verwendet wird und *c* ist keine dieser Werte, lösen die Funktionen eine Assertion.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_istcntrl**|**iscntrl**|**iscntrl**|**iswcntrl**|
|**_istcntrl_l**|**_iscntrl_l**|**_iscntrl_l**|**_iswcntrl_l**|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**iscntrl**|\<ctype.h>|
|**iswcntrl**|\<ctype.h> oder \<wchar.h>|
|**_iscntrl_l**|\<ctype.h>|
|**_iswcntrl_l**|\<ctype.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Zeichenklassifizierung](../../c-runtime-library/character-classification.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[is, isw Routines (is- und isw-Routinen)](../../c-runtime-library/is-isw-routines.md)<br/>
