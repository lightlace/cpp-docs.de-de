---
title: isascii, __isascii, iswascii | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- iswascii
- __isascii
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
- iswascii
- istascii
- __isascii
- _istascii
- isascii
- ctype/isascii
- ctype/__isascii
- corecrt_wctype/iswascii
dev_langs:
- C++
helpviewer_keywords:
- __isascii function
- _isascii function
- isascii function
- _istascii function
- istascii function
- iswascii function
ms.assetid: ba4325ad-7cb3-4fb9-b096-58906d67971a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bffc46bae24689558999d188f96e5b9f8d21c54e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32402272"
---
# <a name="isascii-isascii-iswascii"></a>isascii, __isascii, iswascii

Bestimmt, ob ein angegebenes Zeichen ein ASCII-Zeichen ist.

## <a name="syntax"></a>Syntax

```C
int __isascii(
   int c
);
int iswascii(
   wint_t c
);

#define isascii __isascii
```

### <a name="parameters"></a>Parameter

*c*<br/>
Zu testende ganze Zahl.

## <a name="return-value"></a>Rückgabewert

Jede dieser Routinen gibt ungleich NULL, wenn **c** ist eine bestimmte Darstellung von ASCII-Zeichen. **__isascii** gibt einen Wert ungleich NULL zurück, wenn **c** wird ein ASCII-Zeichen (im Bereich 0 x 00 – 0x7F). **Iswascii** gibt einen Wert ungleich NULL zurück, wenn **c** ist eine Breitzeichen-Darstellung von ASCII-Zeichen. Jede dieser Routinen gibt 0 zurück, wenn **c** die testbedingung nicht erfüllt.

## <a name="remarks"></a>Hinweise

Beide **__isascii** und **Iswascii** werden als Makros implementiert, es sei denn, die _CTYPE_DISABLE_MACROS Präprozessormakro definiert ist.

Gründen der Abwärtskompatibilität **Isascii** wird als nur, wenn ein Makro implementiert [ &#95; &#95;STDC++&#95; &#95; ](../../preprocessor/predefined-macros.md) ist nicht definiert oder wird definiert als 0; andernfalls ist es nicht definiert.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_istascii**|**__isascii**|**__isascii**|**iswascii**|

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**Isascii**, **__isascii**|C: \<ctype.h><br /><br /> C++: \<cctype> oder \<ctype.h>|
|**iswascii**|C: \<wctype.h>, \<ctype.h>, oder \<wchar.h><br /><br /> C++: \<cwctype>, \<cctype>, \<wctype.h>, \<ctype.h>, oder \<wchar.h>|

Die **Isascii**, **__isascii** und **Iswascii** Funktionen sind Microsoft-spezifisch. Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Zeichenklassifizierung](../../c-runtime-library/character-classification.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[is, isw Routines (is- und isw-Routinen)](../../c-runtime-library/is-isw-routines.md)<br/>
