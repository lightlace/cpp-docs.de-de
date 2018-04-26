---
title: __max | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/05/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- __max
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
- max
- __max
dev_langs:
- C++
helpviewer_keywords:
- max macro
- maximum macro
- __max macro
ms.assetid: 05c936f6-0e22-45d6-a58d-4bc102e9dae2
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5bc89f74bb98b8fb51dc652ab57c57d37a46d5a0
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="max"></a>__max

Ein Präprozessormakro, die die größere von zwei Werten zurückgibt.

## <a name="syntax"></a>Syntax

```C
#define __max(a,b) (((a) > (b)) ? (a) : (b))
```

### <a name="parameters"></a>Parameter

*eine*, *b*<br/>
Werte von einem numerischen Datentyp, der verglichen werden soll.

## <a name="return-value"></a>Rückgabewert

**__max** gibt das größere der Argumente zurück.

## <a name="remarks"></a>Hinweise

Die **__max** Makro vergleicht zwei Werte und gibt den Wert eines größeren zurück. Die Argumente können von einen beliebigen Datentyp stammen, signed oder unsigned. Beide Argumente sowie der Rückgabewert müssen demselben Datentyp entsprechen.

Das Argument, das zurückgegeben wird durch das Makro zweimal ausgewertet. Dies kann zu unerwarteten Ergebnissen führen, wenn das Argument einen Ausdruck, der seinen Wert ändert, wenn er, wie z. B. ausgewertet wird `*p++`.

## <a name="requirements"></a>Anforderungen

|Makro|Erforderlicher Header|
|-------------|---------------------|
|**__max**|\<stdlib.h>|

## <a name="example"></a>Beispiel

Weitere Informationen finden Sie im Beispiel für [__min](min.md).

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[__min](min.md)<br/>