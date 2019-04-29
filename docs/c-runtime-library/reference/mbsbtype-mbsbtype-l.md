---
title: _mbsbtype, _mbsbtype_l
ms.date: 11/04/2016
apiname:
- _mbsbtype_l
- _mbsbtype
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
- mbsbtype
- mbsbtype_l
- _mbsbtype_l
- _mbsbtype
helpviewer_keywords:
- _mbsbtype function
- mbsbtype function
- _mbsbtype_l function
- mbsbtype_l function
ms.assetid: 0d5dd91a-d32d-4f98-ac57-98dfc9e98eac
ms.openlocfilehash: 5c2927b4e4b68b1284341fe7e767ec50feb21a44
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62331505"
---
# <a name="mbsbtype-mbsbtypel"></a>_mbsbtype, _mbsbtype_l

Gibt den Bytetyp in einer Zeichenfolge zurück.

> [!IMPORTANT]
> Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
int _mbsbtype(
   const unsigned char *mbstr,
   size_t count
);
int _mbsbtype_l(
   const unsigned char *mbstr,
   size_t count,
   _locale_t locale
);
```

### <a name="parameters"></a>Parameter

*mbstr*<br/>
Adresse einer Sequenz von Multibytezeichen.

*count*<br/>
Byte-Offset vom Anfang der Zeichenfolge.

*locale*<br/>
Zu verwendendes Gebietsschema.

## <a name="return-value"></a>Rückgabewert

**_mbsbtype** und **_mbsbtype_l** gibt einen ganzzahligen Wert, der das Ergebnis des Tests für das angegebene Byte. Die Manifestkonstanten in der folgenden Tabelle sind in Mbctype.h definiert.

|Rückgabewert|Bytetyp|
|------------------|---------------|
|**_MBC_SINGLE** (0)|Einzelbytezeichen. Beispielsweise in Codepage 932 **_mbsbtype** gibt 0 zurück, wenn das angegebene Byte im Bereich 0 x 20 – 0x7E oder 0xA1 - 0xDF liegt.|
|**_MBC_LEAD** (1)|Führendes Byte des Multibytezeichens. Beispielsweise in Codepage 932 **_mbsbtype** gibt 1 zurück, wenn das angegebene Byte im Bereich 0 x 81 – 0x9F oder 0xE0 - 0xFC liegt.|
|**_MBC_TRAIL** (2)|Nachfolgendes Byte des Multibytezeichens. Beispielsweise in Codepage 932 **_mbsbtype** gibt 2 zurück, wenn das angegebene Byte im Bereich 0 x 40-0x7E oder 0 x 80 – 0xFC liegt.|
|**_MBC_ILLEGAL** (-1)|**NULL** Zeichenfolge, ungültiges Zeichen oder null Byte, gefunden vor dem Byte am Offset *Anzahl* in *Mbstr*.|

## <a name="remarks"></a>Hinweise

Die **_mbsbtype** -Funktion bestimmt den Typ eines Bytes in einer Multibyte-Zeichenfolge. Die Funktion überprüft nur das Byte am Offset *Anzahl* in *Mbstr*, ignoriert ungültige Zeichen vor dem angegebenen Byte.

Der Ausgabewert ist von der Kategorieeinstellung **LC_CTYPE** des Gebietsschemas betroffen. Weitere Informationen finden Sie unter [setlocale](setlocale-wsetlocale.md). Die Version dieser Funktion ohne die **_l** -Suffix verwendet das aktuelle Gebietsschema für dieses vom Gebietsschema abhängige Verhalten; die Version mit der **_l** -Suffix ist beinahe identisch, außer dass es den übergebenen Gebietsschemaparameter verwenden in stattdessen. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

Wenn die Eingabezeichenfolge **NULL**, Handler für ungültige Parameter aufgerufen, siehe [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, **Errno** nastaven NA hodnotu **EINVAL** und die Funktion gibt **_MBC_ILLEGAL**.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|Optionaler Header|
|-------------|---------------------|---------------------|
|**_mbsbtype**|\<mbstring.h>|\<mbctype.h>*|
|**_mbsbtype_l**|\<mbstring.h>|\<mbctype.h>*|

\* Für Manifestkonstanten, die als Rückgabewerte verwendet werden.

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Byteklassifizierung](../../c-runtime-library/byte-classification.md)<br/>
