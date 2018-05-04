---
title: _mbbtype, _mbbtype_l | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _mbbtype
- _mbbtype_l
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
- _mbbtype_l
- mbbtype
- mbbtype_l
- _mbbtype
dev_langs:
- C++
helpviewer_keywords:
- _mbbtype function
- _mbbtype_l function
- mbbtype function
- mbbtype_l function
ms.assetid: b8e34b40-842a-4298-aa39-0bd2d8e51c2a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 91b78b0dc57873810f96a793288da3f1457299de
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="mbbtype-mbbtypel"></a>_mbbtype, _mbbtype_l

Gibt den Bytetyp basierend auf dem vorherigen Byte zurück.

> [!IMPORTANT]
> Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
int _mbbtype(
   unsigned char c,
   int type
);
int _mbbtype_l(
   unsigned char c,
   int type,
   _locale_t locale
);
```

### <a name="parameters"></a>Parameter

*c*<br/>
Das zu überprüfende Zeichen.

*Typ*<br/>
Der Typ des zu prüfenden Bytes.

*locale*<br/>
Das zu verwendende Gebietsschema.

## <a name="return-value"></a>Rückgabewert

**_mbbtype** gibt den Typ der Byte in einer Zeichenfolge zurück. Diese Entscheidung ist kontextabhängig, wie durch den Wert des angegebenen *Typ*, das Steuerelement-testbedingung bereitstellt. *Typ* ist der Typ des vorherigen Byte in der Zeichenfolge. Die Manifestkonstanten in der folgenden Tabelle sind in Mbctype.h definiert.

|Wert des *Typ*|**_mbbtype** wird geprüft|Rückgabewert|*c*|
|---------------------|--------------------------|------------------|---------|
|Einen beliebiger Wert außer 1|Gültiges Einzelbyte oder führendes Byte|**_MBC_SINGLE** (0)|Single-Byte (0 x 20 – 0x7E, 0xA1 – 0xDF)|
|Einen beliebiger Wert außer 1|Gültiges Einzelbyte oder führendes Byte|**_MBC_LEAD** (1)|Führendes Byte des multibytezeichens (0 x 81 – 0x9F, 0xE0 – 0xFC)|
|Einen beliebiger Wert außer 1|Gültiges Einzelbyte oder führendes Byte|**_MBC_ILLEGAL**<br /><br /> ( -1)|Ungültiges Zeichen (jeder Wert außer 0 x 20 – 0x7E, 0xA1 – 0xDF, 0 x 81 – 0x9F, 0xE0 – 0xFC|
|1|Gültiges nachfolgendes Byte|**_MBC_TRAIL** (2)|Nachfolgendes Byte des multibytezeichens (0 x 40 – 0x7E, 0 x 80 – 0xFC)|
|1|Gültiges nachfolgendes Byte|**_MBC_ILLEGAL**<br /><br /> ( -1)|Ungültiges Zeichen (jeder Wert außer 0 x 20 – 0x7E, 0xA1 – 0xDF, 0 x 81 – 0x9F, 0xE0 – 0xFC|

## <a name="remarks"></a>Hinweise

Die **_mbbtype** -Funktion bestimmt den Typ eines Bytes in einem multibyte-Zeichen. Wenn der Wert der *Typ* beliebiger Wert außer 1, **_mbbtype** testet, ob ein gültiges Einzelbyte oder führendes Byte eines multibytezeichens. Wenn der Wert der *Typ* beträgt 1, **_mbbtype** Tests auf ein gültiges nachfolgendes Byte eines multibytezeichens.

Der Ausgabewert wird von der Einstellung der beeinflusst die **LC_CTYPE** -kategorieneinstellung des Gebietsschemas; Siehe [Setlocale, _wsetlocale](setlocale-wsetlocale.md) für Weitere Informationen. Die **_mbbtype** Version dieser Funktion verwendet das aktuelle Gebietsschema für dieses vom Gebietsschema abhängige Verhalten; die **_mbbtype_l** -Version ist beinahe identisch, verwendet jedoch den Gebietsschemaparameter, der übergebene . Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

In früheren Versionen **_mbbtype** hieß **Chkctype**. Verwenden Sie bei neuem Code **_mbbtype** stattdessen.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|Optionaler Header|
|-------------|---------------------|---------------------|
|**_mbbtype**|\<mbstring.h>|\<mbctype.h>*|
|**_mbbtype_l**|\<mbstring.h>|\<mbctype.h>*|

\* Für Definitionen von Manifestkonstanten, die als Rückgabewerte verwendet werden.

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Byteklassifizierung](../../c-runtime-library/byte-classification.md)<br/>
