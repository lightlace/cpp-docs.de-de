---
title: wctype
ms.date: 11/04/2016
apiname:
- wctype
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
apitype: DLLExport
f1_keywords:
- wctype
helpviewer_keywords:
- wctype function
- wide characters
ms.assetid: 14aded12-4087-4123-bc48-db4e10999223
ms.openlocfilehash: 81caf8e1ab04635d205d7b01af2d4c2896eec01c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50456900"
---
# <a name="wctype"></a>wctype

Bestimmt eine Klassifizierungsregel für Breitzeichencodes.

## <a name="syntax"></a>Syntax

```C
wctype_t wctype(
   const char * property
);
```

### <a name="parameters"></a>Parameter

*Eigenschaft*<br/>
Eigenschaftszeichenfolge

## <a name="return-value"></a>Rückgabewert

Wenn die **LC_CTYPE** -Kategorie des aktuellen Gebietsschemas definiert eine Klassifizierungsregel, deren Name der Eigenschaftszeichenfolge entspricht, nicht *Eigenschaft*, gibt die Funktion 0 (null) zurück. Andernfalls wird ein Wert ungleich 0 zurückgegeben, der für die Verwendung als das zweite Argument für einen nachfolgenden Aufruf von [towctrans](towctrans.md) geeignet ist.

## <a name="remarks"></a>Hinweise

Die Funktion bestimmt eine Klassifizierungsregel für Breitzeichencodes. Die folgenden Paare von Aufrufen weisen in allen Gebietsschemas das gleiche Verhalten auf (durch eine Implementierung können jedoch sogar im Gebietsschema „C“ zusätzliche Klassifizierungsregeln definiert werden):

|Funktion|Identisch mit|
|--------------|-------------|
|iswalnum(c)|Iswctype (C, Wctype ("Alnum"))|
|iswalpha(c)|Iswctype (C, Wctype ("Alpha"))|
|iswcntrl(c)|Iswctype (C, Wctype ("Strg"))|
|iswdigit(c)|Iswctype (C, Wctype ("Digit"))|
|iswgraph(c)|Iswctype (C, Wctype ("Graph"))|
|iswlower(c)|Iswctype (C, Wctype ("niedriger"))|
|iswprint(c)|Iswctype (C, Wctype ("Print"))|
|iswpunct(c)|Iswctype (C, Wctype ("Punct"))|
|iswspace(c)|Iswctype (C, Wctype ("Leerzeichen"))|
|iswupper(c)|Iswctype (C, Wctype ("oberen"))|
|iswxdigit(c)|Iswctype (C, Wctype ("Xdigit"))|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**wctype**|\<wctype.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Datenkonvertierung](../../c-runtime-library/data-conversion.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
