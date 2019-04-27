---
title: isleadbyte, _isleadbyte_l
ms.date: 11/04/2016
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
helpviewer_keywords:
- lead bytes
- _isleadbyte_l function
- _istleadbyte function
- istleadbyte function
- isleadbyte function
ms.assetid: 3b2bcf09-d82b-4803-9e80-59d04942802a
ms.openlocfilehash: 1a3f427e49e53bb553020da100b0e713350fab3f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62286917"
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

**Isleadbyte** gibt einen Wert ungleich NULL zurück, wenn das Argument die testbedingung "oder" 0 erfüllt, wenn dies nicht der Fall. Im Gebietsschema "C" und im Einzelbyte-Zeichensatz (SBCS) Gebietsschemas **Isleadbyte** gibt immer 0 zurück.

## <a name="remarks"></a>Hinweise

Die **Isleadbyte** Makro gibt einen Wert ungleich NULL zurück, wenn dessen Argument das erste Byte eines multibytezeichens ist. **Isleadbyte** erzeugt ein aussagekräftiges Ergebnis für alle Ganzzahlargumente von-1 (**EOF**) zu **UCHAR_MAX** (0xFF) einschließlich.

Der erwartete Argumenttyp von **Isleadbyte** ist **Int**; Wenn ein Vorzeichen übergebenes Zeichen wird, der Compiler möglicherweise konvertieren in eine ganze Zahl von vorzeichenerweiterung, unvorhersehbare Ergebnisse bereitzustellen.

Die Version dieser Funktion mit dem **_l** -Suffix ist beinahe identisch, außer dass er das Gebietsschema für den übergebenen Gebietsschemaparameter anstelle des aktuellen Gebietsschemas für ihr vom Gebietsschema abhängige Verhalten verwendet.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_istleadbyte**|Gibt immer "false" zurück|**_isleadbyte**|Gibt immer "false" zurück|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**isleadbyte**|\<ctype.h>|
|**_isleadbyte_l**|\<ctype.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Byteklassifizierung](../../c-runtime-library/byte-classification.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[_ismbb-Routinen](../../c-runtime-library/ismbb-routines.md)<br/>
