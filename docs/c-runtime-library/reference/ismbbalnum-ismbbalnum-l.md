---
title: _ismbbalnum, _ismbbalnum_l
ms.date: 11/04/2016
apiname:
- _ismbbalnum
- _ismbbalnum_l
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
- _ismbbalnum
- ismbbalnum
- _ismbbalnum_l
- ismbbalnum_l
helpviewer_keywords:
- _ismbbalnum_l function
- ismbbalnum function
- ismbbalnum_l function
- _ismbbalnum function
ms.assetid: 8025de50-a871-49fd-9ae6-f437b47aa987
ms.openlocfilehash: 5b5f54754907c09a34b0f4c3bae3e5c27336ca36
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50554842"
---
# <a name="ismbbalnum-ismbbalnuml"></a>_ismbbalnum, _ismbbalnum_l

Bestimmt, ob ein angegebenes Multibytezeichen eine Alpha oder ein numerisches Zeichen ist.

## <a name="syntax"></a>Syntax

```C
int _ismbbalnum(
   unsigned int c
);
int _ismbbalnum_l(
   unsigned int c
);
```

### <a name="parameters"></a>Parameter

*c*<br/>
Die zu testende ganze Zahl.

*locale*<br/>
Zu verwendendes Gebietsschema.

## <a name="return-value"></a>Rückgabewert

**_ismbbalnum** gibt einen Wert ungleich NULL zurück, wenn der Ausdruck:

`isalnum(c) || _ismbbkalnum(c)`

ist ungleich NULL für *c*, oder 0, wenn er nicht ist.

Die Version dieser Funktion mit dem **_l** -Suffix ist beinahe identisch, außer dass er das Gebietsschema für den übergebenen Gebietsschemaparameter anstelle des aktuellen Gebietsschemas für ihr vom Gebietsschema abhängige Verhalten verwendet.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_ismbbalnum**|\<mbctype.h>|
|**_ismbbalnum_l**|\<mbctype.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Alle Versionen [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Siehe auch

[Byteklassifizierung](../../c-runtime-library/byte-classification.md)<br/>
[_ismbb-Routinen](../../c-runtime-library/ismbb-routines.md)<br/>
