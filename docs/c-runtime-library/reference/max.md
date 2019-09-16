---
title: __max
ms.date: 04/05/2018
api_name:
- __max
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
- max
- __max
helpviewer_keywords:
- max macro
- maximum macro
- __max macro
ms.assetid: 05c936f6-0e22-45d6-a58d-4bc102e9dae2
ms.openlocfilehash: dac82ecd1c96d1edf9175a29797d93c65bc19c99
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70952750"
---
# <a name="__max"></a>__max

Ein Präprozessormakro, das den größeren von zwei Werten zurückgibt.

## <a name="syntax"></a>Syntax

```C
#define __max(a,b) (((a) > (b)) ? (a) : (b))
```

### <a name="parameters"></a>Parameter

*a*, *b*<br/>
Werte von einem numerischen Datentyp, der verglichen werden soll.

## <a name="return-value"></a>Rückgabewert

**__max** gibt die größere der Argumente zurück.

## <a name="remarks"></a>Hinweise

Das **__max** -Makro vergleicht zwei Werte und gibt den Wert der größeren zurück. Die Argumente können von einen beliebigen Datentyp stammen, signed oder unsigned. Beide Argumente sowie der Rückgabewert müssen demselben Datentyp entsprechen.

Das zurückgegebene Argument wird zweimal durch das Makro ausgewertet. Dies kann zu unerwarteten Ergebnissen führen, wenn das Argument ein Ausdruck ist, der seinen Wert bei der Auswertung ändert, z `*p++`. b.

## <a name="requirements"></a>Anforderungen

|Makro|Erforderlicher Header|
|-------------|---------------------|
|**__max**|\<stdlib.h>|

## <a name="example"></a>Beispiel

Weitere Informationen finden Sie im Beispiel für [__min](min.md).

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[__min](min.md)<br/>