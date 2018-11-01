---
title: towctrans
ms.date: 11/04/2016
apiname:
- towctrans
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- towctrans
helpviewer_keywords:
- towctrans function
ms.assetid: 1ed1e70d-7b31-490f-a7d9-42564b5924ca
ms.openlocfilehash: b814c65d2f5d0bb18b19d97a539d79dd6df8a1c6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50561407"
---
# <a name="towctrans"></a>towctrans

Transformiert ein Zeichen.

## <a name="syntax"></a>Syntax

```C
wint_t towctrans(
   wint_t c,
   wctrans_t category
);
```

### <a name="parameters"></a>Parameter

*c*<br/>
Das Zeichen, das Sie transformieren möchten.

*category*<br/>
Ein Bezeichner, der den Rückgabewert von [wctrans](wctrans.md) enthält.

## <a name="return-value"></a>Rückgabewert

Das Zeichen *c*nach **Towctrans** die transformationsregel in *Kategorie*.

## <a name="remarks"></a>Hinweise

Der Wert des *Kategorie* muss von einer zuvor erfolgreichen Aufruf zurückgegeben wurden [Wctrans](wctrans.md).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**towctrans**|\<wctype.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Finden Sie unter **Wctrans** für ein Beispiel, verwendet **Towctrans**.

## <a name="see-also"></a>Siehe auch

[Datenkonvertierung](../../c-runtime-library/data-conversion.md)<br/>
