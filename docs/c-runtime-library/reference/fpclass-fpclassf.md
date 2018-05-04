---
title: _fpclass, _fpclassf | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _fpclass
- _fpclassf
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
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- fpclass
- _fpclass
- _fpclassf
- math/_fpclass
- float/_fpclass
- math/_fpclassf
dev_langs:
- C++
helpviewer_keywords:
- fpclass function
- floating-point numbers, IEEE representation
- _fpclass function
- _fpclassf function
ms.assetid: 2774872d-3543-446f-bc72-db85f8b95a6b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 79895cf19c188addee45236df5dc47d3f4ebf6a3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="fpclass-fpclassf"></a>_fpclass, _fpclassf

Gibt einen Wert zurück, der die Gleitkommaklassifizierung des Arguments angibt.

## <a name="syntax"></a>Syntax

```C
int _fpclass(
   double x
);

int _fpclassf(
   float x
); /* x64 only */
```

### <a name="parameters"></a>Parameter

*w*<br/>
Der zu testende Gleitkommawert.

## <a name="return-value"></a>Rückgabewert

Die **_fpclass** und **_fpclassf** Funktionen zurück, einen ganzzahliger Wert, der die Gleitkomma Klassifizierung des Arguments angibt *x*. Die Klassifizierung weist möglicherweise einen der folgenden, in \<float.h> definierten Werte auf.

|Wert|Beschreibung|
|-----------|-----------------|
|**_FPCLASS_SNAN**|Signalisierender NaN|
|**_FPCLASS_QNAN**|Stiller NaN|
|**_FPCLASS_NINF**|Minus unendlich (-INF)|
|**_FPCLASS_NN**|Negativ normalisierter ungleich null-Wert|
|**_FPCLASS_ND**|Negativ denormalisiert|
|**_FPCLASS_NZ**|Negative 0 (null) (– 0)|
|**_FPCLASS_PZ**|Positiv 0 (+0)|
|**_FPCLASS_PD**|Positiv denormalisiert|
|**_FPCLASS_PN**|Positiv normalisierter ungleich null-Wert|
|**_FPCLASS_PINF**|Positiv unendlich|

## <a name="remarks"></a>Hinweise

Die **_fpclass** und **_fpclassf** Funktionen sind Microsoft-spezifisch. Sie ähneln [fpclassify](fpclassify.md), geben jedoch detaillierte Informationen über das Argument zurück. Die **_fpclassf** Funktion ist nur verfügbar, wenn die X64 Plattform.

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|
|--------------|---------------------|
|**_fpclass**, **_fpclassf**|\<float.h>|

Weitere Informationen zur Kompatibilität und Konformität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
[fpclassify](fpclassify.md)<br/>