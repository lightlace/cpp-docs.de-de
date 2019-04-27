---
title: _mbbtombc, _mbbtombc_l
ms.date: 11/04/2016
apiname:
- _mbbtombc_l
- _mbbtombc
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
- _mbbtombc_l
- _mbbtombc
- mbbtombc_l
- mbbtombc
helpviewer_keywords:
- mbbtombc_l function
- mbbtombc function
- _mbbtombc_l function
- _mbbtombc function
ms.assetid: 78593389-b0fc-43b6-8c1f-2a6bf702d64e
ms.openlocfilehash: 63b5dd33399201cd6ead7dbd1f710c8bebe53c69
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62156903"
---
# <a name="mbbtombc-mbbtombcl"></a>_mbbtombc, _mbbtombc_l

Konvertiert ein Einzelbyte-Multibytezeichen in ein entsprechendes Doppelbyte-Multibytezeichen.

> [!IMPORTANT]
> Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
unsigned int _mbbtombc(
   unsigned int c
);
unsigned int _mbbtombc_l(
   unsigned int c,
   _locale_t locale
);
```

### <a name="parameters"></a>Parameter

*c*<br/>
Zu konvertierendes Einzelbytezeichen.

*locale*<br/>
Zu verwendendes Gebietsschema.

## <a name="return-value"></a>Rückgabewert

Wenn **_mbbtombc** erfolgreich konvertiert *c*, wird ein Multibytezeichen zurückgegeben; andernfalls wird *c*.

## <a name="remarks"></a>Hinweise

Die **_mbbtombc** Funktion konvertiert ein angegebenes Einzelbyte-Multibytezeichen in ein entsprechendes Doppelbyte-Multibytezeichen. Zeichen muss innerhalb des Bereichs 0 x 20 – 0x7E oder 0xA1 – 0xDF, konvertiert werden soll.

Der Ausgabewert wird von der Einstellung beeinflusst die **LC_CTYPE** -kategorieeinstellung des Gebietsschemas, siehe [Setlocale, _wsetlocale](setlocale-wsetlocale.md) für Weitere Informationen. Die Versionen dieser Funktion sind nahezu identisch, außer dass **_mbbtombc** verwendet das aktuelle Gebietsschema für dieses vom Gebietsschema abhängiges Verhalten und **_mbbtombc_l** stattdessen verwendet den Locale-Parameter, die übergeben wird. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

In früheren Versionen **_mbbtombc** hieß **Hantozen**. Verwenden Sie bei neuem Code **_mbbtombc**.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_mbbtombc**|\<mbstring.h>|
|**_mbbtombc_l**|\<mbstring.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Datenkonvertierung](../../c-runtime-library/data-conversion.md)<br/>
[_mbctombb, _mbctombb_l](mbctombb-mbctombb-l.md)<br/>
