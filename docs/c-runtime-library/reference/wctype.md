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
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62155315"
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
|iswalnum(c)|iswctype(c, wctype( "alnum" ) )|
|iswalpha(c)|iswctype(c, wctype( "alpha" ) )|
|iswcntrl(c)|iswctype(c, wctype( "cntrl" ) )|
|iswdigit(c)|iswctype(c, wctype( "digit" ) )|
|iswgraph(c)|iswctype(c, wctype( "graph" ) )|
|iswlower(c)|iswctype(c, wctype( "lower" ) )|
|iswprint(c)|iswctype(c, wctype( "print" ) )|
|iswpunct(c)|iswctype(c, wctype( "punct" ) )|
|iswspace(c)|iswctype(c, wctype( "space" ) )|
|iswupper(c)|iswctype(c, wctype( "upper" ) )|
|iswxdigit(c)|iswctype(c, wctype( "xdigit" ) )|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**wctype**|\<wctype.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Datenkonvertierung](../../c-runtime-library/data-conversion.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
