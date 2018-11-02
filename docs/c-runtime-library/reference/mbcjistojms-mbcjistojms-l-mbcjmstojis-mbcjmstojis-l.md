---
title: _mbcjistojms, _mbcjistojms_l, _mbcjmstojis, _mbcjmstojis_l
ms.date: 11/04/2016
apiname:
- _mbcjistojms
- _mbcjmstojis
- _mbcjistojms_l
- _mbcjmstojis_l
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
- mbcjistojms
- _mbcjistojms
- _mbcjistojms_l
- _mbcjmstojis_l
- _mbcjmstojis
- mbcjmstojis_l
- mbcjistojms_l
- mbcjmstojis
helpviewer_keywords:
- _mbcjmstojis_l function
- _mbcjistojms function
- mbcjmstojis function
- _mbcjistojms_l function
- _mbcjmstojis function
- mbcjistojms function
- mbcjmstojis_l function
- mbcjistojms_l function
ms.assetid: dece5127-b337-40a4-aa10-53320a2c9432
ms.openlocfilehash: 22cf8eeb5f99b6abee624aa3b1d06246d7230652
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50665893"
---
# <a name="mbcjistojms-mbcjistojmsl-mbcjmstojis-mbcjmstojisl"></a>_mbcjistojms, _mbcjistojms_l, _mbcjmstojis, _mbcjmstojis_l

Konvertiert zwischen Zeichen aus den Zeichensätzen Japan Industry Standard (JIS) und Japan Microsoft (JMS).

> [!IMPORTANT]
> Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
unsigned int _mbcjistojms(
   unsigned int c
);
unsigned int _mbcjistojms_l(
   unsigned int c,
   _locale_t locale
);
unsigned int _mbcjmstojis(
   unsigned int c
);
unsigned int _mbcjmstojis_l(
   unsigned int c,
   _locale_t locale
);
```

### <a name="parameters"></a>Parameter

*c*<br/>
Zu konvertierendes Zeichen.

*locale*<br/>
Zu verwendendes Gebietsschema.

## <a name="return-value"></a>Rückgabewert

Bei einem japanischen Gebietsschema geben diese Funktionen ein konvertiertes Zeichen zurück. Wenn keine Konvertierung möglich ist, wir 0 (null) zurückgegeben. Bei einem nicht japanischen Gebietsschema geben diese Funktionen das Zeichen zurück, das übergeben wurde.

## <a name="remarks"></a>Hinweise

Die **_mbcjistojms** -Funktion konvertiert ein Zeichen Japan Industry Standard (JIS) in ein Microsoft Kanji (Shift-JIS) Zeichen. Das Zeichen wird nur konvertiert, wenn die und die nachfolgenden Bytes im Bereich 0 x 21 – 0x7E sind. Wenn das anführende oder das nachfolgende Byte außerhalb dieses Bereichs liegen, ist **Errno** nastaven NA hodnotu **EILSEQ**. Weitere Informationen hierzu und über andere Fehlercodes finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Die **_mbcjmstojis** Funktion konvertiert ein Shift JIS-Zeichen in ein JIS-Zeichen. Nur, wenn das führende Byte im Bereich 0 x 81 – 0x9F oder 0xE0 - 0xFC liegt liegt und das nachfolgende Byte im Bereich 0 x 40-0x7E oder 0 x 80 – 0xFC liegt liegt, wird das Zeichen konvertiert. Beachten Sie, dass einigen Codepunkten in diesem Bereich kein Zeichen zugewiesen ist und sie daher nicht konvertiert werden können.

Der Wert *c* muss ein 16-Bit-Wert, dessen obere 8 Bits das führende Byte der zu konvertierende Zeichen darstellen, und dessen untere 8 Bits das nachfolgende Byte darstellen.

Der Ausgabewert ist von der Kategorieeinstellung **LC_CTYPE** des Gebietsschemas betroffen. Weitere Informationen finden Sie unter [setlocale](setlocale-wsetlocale.md). Die Versionen dieser Funktionen ohne das **_l**-Suffix verwenden das aktuelle Gebietsschema für dieses vom Gebietsschema abhängige Verhalten; die Versionen mit dem **_l**-Suffix sind beinahe identisch, verwenden jedoch stattdessen den ihnen übergebenen Gebietsschemaparameter. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

In früheren Versionen **_mbcjistojms** und **_mbcjmstojis** aufgerufen wurden **Jistojms** und **Jmstojis**bzw. **_mbcjistojms**, **_mbcjistojms_l**, **_mbcjmstojis** und **_mbcjmstojis_l** sollte stattdessen verwendet werden.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_mbcjistojms**|\<mbstring.h>|
|**_mbcjistojms_l**|\<mbstring.h>|
|**_mbcjmstojis**|\<mbstring.h>|
|**_mbcjmstojis_l**|\<mbstring.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Datenkonvertierung](../../c-runtime-library/data-conversion.md)<br/>
[_ismbb-Routinen](../../c-runtime-library/ismbb-routines.md)<br/>
