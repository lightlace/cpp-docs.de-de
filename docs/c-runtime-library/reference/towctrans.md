---
title: towctrans
ms.date: 11/04/2016
api_name:
- towctrans
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
- api-ms-win-crt-string-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- towctrans
helpviewer_keywords:
- towctrans function
ms.assetid: 1ed1e70d-7b31-490f-a7d9-42564b5924ca
ms.openlocfilehash: d63fc343647cd0f949f282e2a64d4a0636e62bd7
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957423"
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

Das Zeichen *c*, nachdem **towctrans** die Transformations Regel in der *Kategorie*verwendet hat.

## <a name="remarks"></a>Hinweise

Der Wert der *Kategorie* muss von einem früheren erfolgreichen [wctrans](wctrans.md)-Rückruf zurückgegeben worden sein.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**towctrans**|\<wctype.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Ein Beispiel für die Verwendung von **towctrans**finden Sie unter **wctrans** .

## <a name="see-also"></a>Siehe auch

[Datenkonvertierung](../../c-runtime-library/data-conversion.md)<br/>
