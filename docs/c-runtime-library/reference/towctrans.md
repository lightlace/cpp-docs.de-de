---
title: towctrans | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- towctrans function
ms.assetid: 1ed1e70d-7b31-490f-a7d9-42564b5924ca
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a1e3029fc9d33df93e13e6fd0a8e9e8d8da168b0
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
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

Das Zeichen *c*nach **Towctrans** verwendet die transformationsregel in *Kategorie*.

## <a name="remarks"></a>Hinweise

Der Wert der *Kategorie* muss von einem früheren erfolgreichen Aufruf von zurückgegeben worden sein [Wctrans](wctrans.md).

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**towctrans**|\<wctype.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Finden Sie unter **Wctrans** für ein Beispiel, verwendet **Towctrans**.

## <a name="see-also"></a>Siehe auch

[Datenkonvertierung](../../c-runtime-library/data-conversion.md)<br/>
