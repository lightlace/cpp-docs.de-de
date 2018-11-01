---
title: iscsym, iscsymf, __iscsym, __iswcsym, __iscsymf, __iswcsymf, _iscsym_l, _iswcsym_l, _iscsymf_l, _iswcsymf_l
ms.date: 11/04/2016
apiname:
- _iswcsym_l
- __iswcsym
- __iscsym
- _iswcsymf_l
- _iscsym_l
- __iswcsymf
- __iscsymf
- _iscsymf_l
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
- _iswcsym_l
- _iswcsymf_l
- iscsymf
- iswcsymf
- __iswcsym
- __iswcsymf
- iscsym
- iswcsym
- __iscsym
- _iscsym_l
- _iscsymf_l
- __iscsymf
- ctype/iscsym
- ctype/iscsymf
- ctype/__iscsym
- ctype/__iscsymf
- ctype/__iscsym_l
- ctype/__iscsymf_l
- ctype/__iswcsym
- ctype/__iswcsymf
- ctype/__iswcsym_l
- ctype/__iswcsymf_l
helpviewer_keywords:
- iscsymf_l function
- iswsym_l function
- _iswcsym_l function
- iscsym_l function
- _iscsymf_l function
- _iswcsymf_l function
- _iscsym_l function
- __iscsym function
- __iswcsymf function
- iswsymf_l function
- __iscsymf function
- __iswcsym function
- iscsym function
- iscsymf function
ms.assetid: 944dfb99-f2b8-498c-9f55-dbcf370d0a2c
ms.openlocfilehash: 8ee84243b98c08504ac0bb63593e39c32230b706
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50617857"
---
# <a name="iscsym-iscsymf-iscsym-iswcsym-iscsymf-iswcsymf-iscsyml-iswcsyml-iscsymfl-iswcsymfl"></a>iscsym, iscsymf, __iscsym, __iswcsym, __iscsymf, __iswcsymf, _iscsym_l, _iswcsym_l, _iscsymf_l, _iswcsymf_l

Bestimmt, ob eine Ganzzahl ein Zeichen darstellt, das in einem Bezeichner verwendet werden kann.

## <a name="syntax"></a>Syntax

```C
int __iscsym(
   int c
);
int __iswcsym(
   wint_t c
);
int __iscsymf(
   int c
);
int __iswcsymf(
   wint_t c
);
int _iscsym_l(
   int c,
   _locale_t locale
);
int _iswcsym_l(
   wint_t c,
   _locale_t locale
);
int _iscsymf_l(
   int c,
   _locale_t locale
);
int _iswcsymf_l(
   wint_t c,
   _locale_t locale
);
#define iscsym __iscsym
#define iscsymf __iscsymf
```

### <a name="parameters"></a>Parameter

*c*<br/>
Zu testende ganze Zahl. *c* muss im Bereich von 0 – 255 für die schmale zeichenversion der Funktion.

*locale*<br/>
Das zu verwendende Gebietsschema.

## <a name="return-value"></a>Rückgabewert

Beide **__iscsym** und **__iswcsym** einen Wert ungleich NULL zurück, wenn *c* ist ein Buchstabe, Unterstrich oder Ziffer. Beide **__iscsymf** und **__iswcsymf** einen Wert ungleich NULL zurück, wenn *c* ein Buchstabe oder Unterstrich. Jede dieser Routinen gibt 0 zurück, wenn *c* die testbedingung nicht erfüllt. Die Versionen dieser Funktionen mit den **_l** -Suffix sind beinahe identisch, außer dass sie verwenden die *Gebietsschema* für den übergebenen Gebietsschemaparameter anstelle des aktuellen Gebietsschemas für ihr vom Gebietsschema abhängige Verhalten. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

## <a name="remarks"></a>Hinweise

Diese Routinen werden als Makros implementiert, es sei denn, die Präprozessormakro _CTYPE_DISABLE_MACROS ist definiert. Wenn Sie die Makroversionen dieser Routinen verwenden, können die Argumente mehr als einmal ausgewertet werden. Seien Sie vorsichtig, wenn Sie Ausdrücke mit Nebeneffekten in der Argumentliste verwenden.

Für die Abwärtskompatibilität **Iscsym** und **Iscsymf** werden als Makros definiert nur, wenn [ &#95; &#95;STDC&#95; &#95; ](../../preprocessor/predefined-macros.md) ist nicht definiert oder definiert ist als 0; Andernfalls sind sie nicht definiert.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**Iscsym**, **Iscsymf**, **__iscsym**, **__iswcsym**, **__iscsymf**, **__iswcsymf**, **_iscsym_l**, **_iswcsym_l**, **_iscsymf_l**, **_iswcsymf_l**|C: \<ctype.h><br /><br /> C++: \<cctype> oder \<ctype.h>|

Die **Iscsym**, **Iscsymf**, **__iscsym**, **__iswcsym**, **__iscsymf**, **__ Iswcsymf**, **_iscsym_l**, **_iswcsym_l**, **_iscsymf_l**, und **_iswcsymf_l** Routinen sind Microsoft-spezifisch. Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Zeichenklassifizierung](../../c-runtime-library/character-classification.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[is, isw Routines (is- und isw-Routinen)](../../c-runtime-library/is-isw-routines.md)<br/>
