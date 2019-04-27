---
title: wctrans
ms.date: 11/04/2016
apiname:
- wctrans
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- wctrans
helpviewer_keywords:
- character codes, wctrans
- characters, codes
- characters, converting
- wctrans function
ms.assetid: 215404bf-6d60-489c-9ae9-880e6b586162
ms.openlocfilehash: 3c7aace7a93160d2e9a4c1523d49bcaf6ae4dc20
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62188454"
---
# <a name="wctrans"></a>wctrans

Bestimmt eine Zuordnung von einer Gruppe Zeichencodes zu einer anderen.

## <a name="syntax"></a>Syntax

```C
wctrans_t wctrans(
   const char *property
);
```

### <a name="parameters"></a>Parameter

*Eigenschaft*<br/>
Eine Zeichenfolge, die eine der gültigen Transformationen angibt.

## <a name="return-value"></a>Rückgabewert

Wenn die **LC_CTYPE** -Kategorie des aktuellen Gebietsschemas definiert eine Zuordnung, deren Name der Eigenschaftszeichenfolge entspricht, nicht *Eigenschaft*, gibt die Funktion 0 (null) zurück. Andernfalls wird ein Wert ungleich 0 zurückgegeben, der für die Verwendung als das zweite Argument für einen nachfolgenden Aufruf von [towctrans](towctrans.md) geeignet ist.

## <a name="remarks"></a>Hinweise

Diese Funktion bestimmt eine Zuordnung von einer Gruppe Zeichencodes zu einer anderen.

Die folgenden Paare von Aufrufen weisen in allen Gebietsschemas das gleiche Verhalten auf, es ist jedoch möglich, sogar im Gebietsschema „C“ zusätzliche Zuordnungen zu definieren:

|Funktion|Identisch mit|
|--------------|-------------|
|ToLower(c)|towctrans(c, wctrans("towlower"))|
|towupper(c)|towctrans(c, wctrans("toupper"))|

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**wctrans**|\<wctype.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_wctrans.cpp
// compile with: /EHsc
// This example determines a mapping from one set of character
// codes to another.

#include <wchar.h>
#include <wctype.h>
#include <stdio.h>
#include <iostream>

int main()
{
    wint_t c = 'a';
    printf_s("%d\n",c);

    wctrans_t i = wctrans("toupper");
    printf_s("%d\n",i);

    wctrans_t ii = wctrans("towlower");
    printf_s("%d\n",ii);

    wchar_t wc = towctrans(c, i);
    printf_s("%d\n",wc);
}
```

```Output
97
1
0
65
```

## <a name="see-also"></a>Siehe auch

[Datenkonvertierung](../../c-runtime-library/data-conversion.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
