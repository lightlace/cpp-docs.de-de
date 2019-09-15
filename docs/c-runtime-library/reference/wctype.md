---
title: wctype
ms.date: 11/04/2016
api_name:
- wctype
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- wctype
helpviewer_keywords:
- wctype function
- wide characters
ms.assetid: 14aded12-4087-4123-bc48-db4e10999223
ms.openlocfilehash: f77082bbcc5f3cd9d82fb40993c3ac678e7e7ba2
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957809"
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

*property*<br/>
Eigenschaftszeichenfolge

## <a name="return-value"></a>Rückgabewert

Wenn in der **LC_CTYPE** -Kategorie des aktuellen Gebiets Schemas keine Klassifizierungs Regel definiert ist, deren Name mit der Eigenschaften Zeichenfolgen- *Eigenschaft*übereinstimmt, gibt die Funktion NULL zurück. Andernfalls wird ein Wert ungleich 0 zurückgegeben, der für die Verwendung als das zweite Argument für einen nachfolgenden Aufruf von [towctrans](towctrans.md) geeignet ist.

## <a name="remarks"></a>Hinweise

Die Funktion bestimmt eine Klassifizierungsregel für Breitzeichencodes. Die folgenden Paare von Aufrufen weisen in allen Gebietsschemas das gleiche Verhalten auf (durch eine Implementierung können jedoch sogar im Gebietsschema „C“ zusätzliche Klassifizierungsregeln definiert werden):

|Funktion|Identisch mit|
|--------------|-------------|
|iswalnum(c)|iswctype(c, wctype( "alnum" ) )|
|iswalpha (c)|iswctype(c, wctype( "alpha" ) )|
|iswcntrl(c)|iswctype(c, wctype( "cntrl" ) )|
|iswdigit (c)|iswctype(c, wctype( "digit" ) )|
|iswgraph (c)|iswctype(c, wctype( "graph" ) )|
|iswlower (c)|iswctype(c, wctype( "lower" ) )|
|iswprint (c)|iswctype(c, wctype( "print" ) )|
|iswpunct (c)|iswctype(c, wctype( "punct" ) )|
|iswspace (c)|iswctype(c, wctype( "space" ) )|
|iswupper (c)|iswctype(c, wctype( "upper" ) )|
|iswxdigit (c)|iswctype(c, wctype( "xdigit" ) )|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**wctype**|\<wctype.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Datenkonvertierung](../../c-runtime-library/data-conversion.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
