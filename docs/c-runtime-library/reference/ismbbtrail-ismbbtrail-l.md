---
title: _ismbbtrail, _ismbbtrail_l | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _ismbbtrail
- _ismbbtrail_l
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
- _ismbbtrail
- ismbbtrail
- _ismbbtrail_l
- ismbbtrail_l
dev_langs:
- C++
helpviewer_keywords:
- ismbbtrail_l function
- _ismbbtrail function
- _ismbbtrail_l function
- ismbbtrail function
ms.assetid: dfdd0292-960b-4c1d-bf11-146e0fc80247
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5b062dff3ef38743af21e2dcf75ea1cfb4a8c921
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="ismbbtrail-ismbbtraill"></a>_ismbbtrail, _ismbbtrail_l

Bestimmt, ob ein Byte ein führendes Byte eines Multibytezeichens ist.

## <a name="syntax"></a>Syntax

```C
int _ismbbtrail(
   unsigned int c
);
int _ismbbtrail_l(
   unsigned int c,
   _locale_t locale
);
```

### <a name="parameters"></a>Parameter

*c*<br/>
Die zu testende ganze Zahl.

*locale*<br/>
Das zu verwendende Gebietsschema.

## <a name="return-value"></a>Rückgabewert

**_ismbbtrail** gibt einen Wert ungleich NULL zurück, wenn die ganze Zahl *c* das zweite Byte eines multibytezeichens ist. Auf Codeseite 932 sind beispielsweise die gültigen Bereiche nur 0x40 bis 0x7E und 0x80 bis 0xFC.

## <a name="remarks"></a>Hinweise

**_ismbbtrail** verwendet das aktuelle Gebietsschema für gebietsschemaabhängige Verhalten. **_ismbbtrail_l** ist nahezu identisch, verwendet jedoch den Gebietsschemaparameter, der stattdessen übergeben wird. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|Optionaler Header|
|-------------|---------------------|---------------------|
|**_ismbbtrail**|\<mbctype.h> oder \<mbstring.h>|\<ctype.h>,* \<limits.h>, \<stdlib.h>|
|**_ismbbtrail_l**|\<mbctype.h> oder \<mbstring.h>|\<ctype.h>,* \<limits.h>, \<stdlib.h>|

\* Für Manifestkonstanten für die Testbedingungen.

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Byteklassifizierung](../../c-runtime-library/byte-classification.md)<br/>
[_ismbb-Routinen](../../c-runtime-library/ismbb-routines.md)<br/>
