---
title: _mbcjistojms, _mbcjistojms_l, _mbcjmstojis, _mbcjmstojis_l | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 07d34331e38362a6491e3231566443b5fe03260e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32402428"
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

Die **_mbcjistojms** -Funktion konvertiert ein Zeichen Japan Industry Standard (JIS) in ein Microsoft Kanji (Shift-JIS) Zeichen. Das Zeichen wird nur konvertiert, wenn die führendes und nachfolgendes Byte im Bereich 0 x 21 – 0x7E sind. Wenn das anführende oder das nachfolgende Byte außerhalb dieses Bereichs ist **Errno** festgelegt ist, um **EILSEQ**. Weitere Informationen hierzu und über andere Fehlercodes finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Die **_mbcjmstojis** -Funktion konvertiert ein Shift JIS-Zeichen In JIS-Zeichen. Das Zeichen wird nur konvertiert, wenn das führende Byte im Bereich 0 x 81-0x9F oder 0xE0 - 0xFC liegt liegt und das nachfolgende Byte im Bereich 0 x 40-0x7E oder 0 x 80 – 0xFC liegt. Beachten Sie, dass einigen Codepunkten in diesem Bereich kein Zeichen zugewiesen ist und sie daher nicht konvertiert werden können.

Der Wert *c* sollte ein 16-Bit-Wert sein, dessen obere 8 Bits das führende Byte der zu konvertierende Zeichen darstellen und dessen untere 8 Bits das nachfolgende Byte darstellen.

Der Ausgabewert wird von der Einstellung der beeinflusst die **LC_CTYPE** -kategorieneinstellung des Gebietsschemas; Siehe [Setlocale](setlocale-wsetlocale.md) für Weitere Informationen. Die Versionen dieser Funktionen ohne das **_l**-Suffix verwenden das aktuelle Gebietsschema für dieses vom Gebietsschema abhängige Verhalten; die Versionen mit dem **_l**-Suffix sind beinahe identisch, verwenden jedoch stattdessen den ihnen übergebenen Gebietsschemaparameter. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

In früheren Versionen **_mbcjistojms** und **_mbcjmstojis** aufgerufen wurden **Jistojms** und **Jmstojis**zugeordnet. **_mbcjistojms**, **_mbcjistojms_l**, **_mbcjmstojis** und **_mbcjmstojis_l** sollte stattdessen verwendet werden.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_mbcjistojms**|\<mbstring.h>|
|**_mbcjistojms_l**|\<mbstring.h>|
|**_mbcjmstojis**|\<mbstring.h>|
|**_mbcjmstojis_l**|\<mbstring.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Datenkonvertierung](../../c-runtime-library/data-conversion.md)<br/>
[_ismbb-Routinen](../../c-runtime-library/ismbb-routines.md)<br/>
