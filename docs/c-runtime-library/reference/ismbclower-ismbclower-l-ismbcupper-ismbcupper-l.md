---
title: _ismbclower, _ismbclower_l, _ismbcupper, _ismbcupper_l | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _ismbclower
- _ismbclower_l
- _ismbcupper_l
- _ismbcupper
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
- api-ms-win-crt-multibyte-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _ismbcupper
- _ismbclower
dev_langs:
- C++
helpviewer_keywords:
- _ismbcupper function
- ismbclower function
- _ismbclower_l function
- ismbcupper_l function
- _ismbclower function
- ismbcupper function
- ismbclower_l function
- _ismbcupper_l function
ms.assetid: 17d89587-65bc-477c-ba8f-a84e63cf59e7
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2350e8f3034d18dda32f3007d714d532828ee338
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="ismbclower-ismbclowerl-ismbcupper-ismbcupperl"></a>_ismbclower, _ismbclower_l, _ismbcupper, _ismbcupper_l

Überprüft, ob ein Multibytezeichen in Klein- oder Großschreibung vorliegt.

> [!IMPORTANT]
> Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
int _ismbclower(
   unsigned int c
);
int _ismbclower_l(
   unsigned int c,
   _locale_t locale
);
int _ismbcupper(
   unsigned int c
);
int _ismbcupper_l(
   unsigned int c,
   _locale_t locale
);
```

### <a name="parameters"></a>Parameter

*c*<br/>
Zu testende Zeichen.

*locale*<br/>
Zu verwendendes Gebietsschema.

## <a name="return-value"></a>Rückgabewert

Jede dieser Routinen gibt einen Wert ungleich 0 zurück, wenn das Zeichen die Testbedingung erfüllt, bzw. 0, wenn es sie nicht erfüllt. Wenn *c*< = 255, und es wird ein entsprechendes **_ismbb** Routine (z. B. **_ismbcalnum** entspricht **_ismbbalnum**), die Ergebnis ist der Rückgabewert der entsprechenden **_ismbb** Routine.

## <a name="remarks"></a>Hinweise

Jede dieser Funktionen testet ein angegebenes Mehrbytezeichen auf eine angegebene Bedingung.

Die Versionen dieser Funktionen mit dem **_l** -Suffix sind beinahe identisch, außer dass sie das Gebietsschema für den übergebenen Gebietsschemaparameter anstelle des aktuellen Gebietsschemas für ihr vom Gebietsschema abhängiges Verhalten verwenden. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

|Routine|Testbedingung|Beispiel für Codepage 932|
|-------------|--------------------|---------------------------|
|**_ismbclower**|Kleinbuchstaben alphabetisch|Gibt einen Wert ungleich NULL und nur, wenn *c* ist eine Single-Byte-Darstellung von einem Kleinbuchstaben ASCII-Buchstaben: 0 x 61 < =*c*< = 0x7A.|
|**_ismbclower_l**|Kleinbuchstaben alphabetisch|Gibt einen Wert ungleich NULL und nur, wenn *c* ist eine Single-Byte-Darstellung von einem Kleinbuchstaben ASCII-Buchstaben: 0 x 61 < =*c*< = 0x7A.|
|**_ismbcupper**|Großbuchstaben alphabetisch|Gibt einen Wert ungleich NULL und nur, wenn *c* eine einzelbytedarstellung eines englischen ASCII-Großbuchstabens ist: 0 x 41 nach < =*c*< = 0x5A.|
|**_ismbcupper_l**|Großbuchstaben alphabetisch|Gibt einen Wert ungleich NULL und nur, wenn *c* eine einzelbytedarstellung eines englischen ASCII-Großbuchstabens ist: 0 x 41 nach < =*c*< = 0x5A.|

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_ismbclower**|\<mbstring.h>|
|**_ismbclower_l**|\<mbstring.h>|
|**_ismbcupper**|\<mbstring.h>|
|**_ismbcupper_l**|\<mbstring.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Zeichenklassifizierung](../../c-runtime-library/character-classification.md)<br/>
[ismbc-Routinen](../../c-runtime-library/ismbc-routines.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[Interpretation von Multibyte-Zeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[is, isw Routines (is- und isw-Routinen)](../../c-runtime-library/is-isw-routines.md)<br/>
[_ismbb-Routinen](../../c-runtime-library/ismbb-routines.md)<br/>
