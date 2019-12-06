---
title: isascii, __isascii, iswascii
ms.date: 11/04/2016
api_name:
- iswascii
- __isascii
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
- api-ms-win-crt-string-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- iswascii
- istascii
- __isascii
- _istascii
- isascii
- ctype/isascii
- ctype/__isascii
- corecrt_wctype/iswascii
helpviewer_keywords:
- __isascii function
- _isascii function
- isascii function
- _istascii function
- istascii function
- iswascii function
ms.assetid: ba4325ad-7cb3-4fb9-b096-58906d67971a
ms.openlocfilehash: b7677819a4b138b08ed4ff97de38c091ce0e94fd
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857787"
---
# <a name="isascii-__isascii-iswascii"></a>isascii, __isascii, iswascii

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

### <a name="parameters"></a>Parameters

*c*<br/>
Zu testende ganze Zahl.

## <a name="return-value"></a>Rückgabewert

Jede dieser Routinen gibt einen Wert ungleich 0 (null) zurück, wenn **c** eine bestimmte Darstellung eines ASCII-Zeichens ist. **__isascii** gibt einen Wert ungleich 0 (null) zurück, wenn **c** ein ASCII-Zeichen ist (im Bereich 0x00-0x7F). **iswascii** gibt einen Wert ungleich 0 (null) zurück, wenn **c** eine breit Zeichen Darstellung eines ASCII-Zeichens ist. Jede dieser Routinen gibt 0 zurück, wenn **c** die Test Bedingung nicht erfüllt.

## <a name="remarks"></a>Hinweise

Sowohl **__isascii** als auch **iswascii** werden als Makros implementiert, es sei denn, das Präprozessormakro _CTYPE_DISABLE_MACROS definiert.

Aus Gründen der Abwärtskompatibilität wird **isascii** nur dann als Makro implementiert, wenn [ &#95; &#95;stdc&#95; ](../../preprocessor/predefined-macros.md) nicht definiert oder als 0 definiert ist. Andernfalls ist es nicht definiert.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_istascii**|**__isascii**|**__isascii**|**iswascii**|

## <a name="requirements"></a>-Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**isascii**, **__isascii**|C: \<ctype.h><br /><br /> C++: \<cctype> oder \<ctype.h>|
|**iswascii**|C: \<wctype.h>, \<ctype.h>, oder \<wchar.h><br /><br /> C++: \<cwctype>, \<cctype>, \<wctype.h>, \<ctype.h>, oder \<wchar.h>|

Die Funktionen **isascii**, **__isascii** und **iswascii** sind Microsoft-spezifisch. Zusätzliche Informationen zur Kompatibilität finden Sie unter [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Zeichenklassifizierung](../../c-runtime-library/character-classification.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[is, isw Routines (is- und isw-Routinen)](../../c-runtime-library/is-isw-routines.md)<br/>
