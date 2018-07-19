---
title: isleadbyte, _isleadbyte_l | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _isleadbyte_l
- isleadbyte
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
- _istleadbyte
- _isleadbyte_l
- isleadbyte
dev_langs:
- C++
helpviewer_keywords:
- lead bytes
- _isleadbyte_l function
- _istleadbyte function
- istleadbyte function
- isleadbyte function
ms.assetid: 3b2bcf09-d82b-4803-9e80-59d04942802a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 682cdde6983c5e590920c43418e510b9c275b34e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32401017"
---
# <a name="isleadbyte-isleadbytel"></a>isleadbyte, _isleadbyte_l

Bestimmt, ob ein Zeichen das führende Byte eines Multibytezeichens ist.

> [!IMPORTANT]
> Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
int isleadbyte( int c );
int _isleadbyte_l( int c );
```

### <a name="parameters"></a>Parameter

*c*<br/>
Zu testende ganze Zahl.

## <a name="return-value"></a>Rückgabewert

**Isleadbyte** gibt einen Wert ungleich NULL zurück, wenn das Argument die testbedingung erfüllt, bzw. 0 erfüllt, wenn dies nicht der Fall. In der "C"-Gebietsschema und Einzelbyte-Zeichensatz (SBCS) Gebietsschemas **Isleadbyte** gibt immer 0 zurück.

## <a name="remarks"></a>Hinweise

Die **Isleadbyte** Makro gibt einen Wert ungleich NULL zurück, wenn dessen Argument das erste Byte eines multibytezeichens ist. **Isleadbyte** erzeugt ein aussagekräftiges Ergebnis für ein Ganzzahlargument von – 1 (**EOF**) zu **UCHAR_MAX** (0xFF) inklusive.

Der erwartete Argumenttyp von **Isleadbyte** ist **Int**; Wenn ein mit Vorzeichen übergebenes Zeichen wird, vom Compiler möglicherweise konvertiert in eine ganze Zahl durch vorzeichenerweiterung, zu unvorhersehbaren Ergebnissen führt.

Die Version dieser Funktion mit dem **_l** -Suffix ist beinahe identisch, außer dass er das Gebietsschema für den übergebenen Gebietsschemaparameter anstelle des aktuellen Gebietsschemas für ihr vom Gebietsschema abhängiges Verhalten verwendet.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_istleadbyte**|Gibt immer "false" zurück|**_isleadbyte**|Gibt immer "false" zurück|

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**isleadbyte**|\<ctype.h>|
|**_isleadbyte_l**|\<ctype.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Byteklassifizierung](../../c-runtime-library/byte-classification.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[_ismbb-Routinen](../../c-runtime-library/ismbb-routines.md)<br/>
