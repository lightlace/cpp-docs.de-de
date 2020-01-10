---
title: _ismbblead, _ismbblead_l
description: Beschreibt die Funktionen der Microsoft C-Lauf Zeit Bibliothek (CRT) _ismbblead und _ismbblead_l.
ms.date: 01/08/2020
api_name:
- _ismbblead_l
- _ismbblead
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
- api-ms-win-crt-multibyte-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- ismbblead_l
- istlead
- _ismbblead
- _ismbblead_l
- ismbblead
- _istlead
helpviewer_keywords:
- _ismbblead_l function
- ismbblead function
- _ismbblead function
- istlead function
- ismbblead_l function
- _istlead function
ms.assetid: 2abc6f75-ed5c-472e-bfd0-e905a1835ccf
ms.openlocfilehash: 6a7bb992eeeb9c66a7cbdea0ed34cf797d374617
ms.sourcegitcommit: 7bd3567fc6a0e7124aab51cad63bbdb44a99a848
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "75755031"
---
# <a name="_ismbblead-_ismbblead_l"></a>_ismbblead, _ismbblead_l

Testet ein Zeichen, um zu bestimmen, ob es sich um ein führendes Byte eines multibytezeichens handelt.

## <a name="syntax"></a>Syntax

```C
int _ismbblead(
   unsigned int c
);
int _ismbblead_l(
   unsigned int c,
   _locale_t locale
);
```

### <a name="parameters"></a>Parameters

*c* -\
Die zu testende ganze Zahl.

Gebiets *Schema\*
Zu verwendendes Gebietsschema.

## <a name="return-value"></a>Rückgabewert

Gibt einen Wert ungleich 0 (null) zurück, wenn die ganze Zahl *c* das erste Byte eines multibytezeichens ist.

## <a name="remarks"></a>Hinweise

Multibytezeichen bestehen aus einem führenden Byte gefolgt von einem nachfolgendem Byte. Führende Bytes werden anhand ihrer Zugehörigkeit zu einem bestimmten Bereich für einen gegebenen Zeichensatz unterschieden. Beispielsweise reichen in der Codepage 932 nur die führenden Bytes von 0x81-0x9F und 0xE0-0xFC.

**_ismbblead** verwendet das aktuelle Gebiets Schema für vom Gebiets Schema abhängiges Verhalten. **_ismbblead_l** ist beinahe identisch, verwendet jedoch stattdessen das übergebene Gebiets Schema. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

Wenn das Gebiets Schema UTF-8 ist, gibt **_ismbblead** und **_ismbblead_l** immer 0 (false) zurück, ob *c* ein führendes Byte ist oder nicht.

**_ismbblead** und **_ismbblead_l** sind Microsoft-spezifisch, nicht Teil der Standard-C-Bibliothek. Wir empfehlen Ihnen nicht, Sie zu verwenden, wenn Sie portablen Code verwenden möchten. Verwenden Sie für die Standard-C-Kompatibilität stattdessen **mbrlen** .

### <a name="generic-text-routine-mappings"></a>Zuordnungen von generischen Text Routinen

|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_istlead**|Gibt immer "false" zurück|**_ismbblead**|Gibt immer "false" zurück|

## <a name="requirements"></a>-Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|Optionaler Header|
|-------------|---------------------|---------------------|
|**_ismbblead**|\<mbctype.h> oder \<mbstring.h>|\<ctype.h>,* \<limits.h>, \<stdlib.h>|
|**_ismbblead_l**|\<mbctype.h> oder \<mbstring.h>|\<ctype.h>,* \<limits.h>, \<stdlib.h>|

\* Für Manifestkonstanten für die Testbedingungen.

Weitere Informationen zur Kompatibilität finden Sie unter [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Byte Klassifizierung](../../c-runtime-library/byte-classification.md)\
[_ismbb Routinen](../../c-runtime-library/ismbb-routines.md)\
[mbrlen](mbrlen.md)
