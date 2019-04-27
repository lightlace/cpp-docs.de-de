---
title: __uncaught_exception
ms.date: 11/04/2016
apiname:
- __uncaught_exception
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
- __uncaught_exception
helpviewer_keywords:
- __uncaught_exception
ms.assetid: 4d9b75c6-c9c7-4876-b761-ea9ab1925e96
ms.openlocfilehash: 19d1e18af27722d6f9da39ebaaf6c9415c281849
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62268896"
---
# <a name="uncaughtexception"></a>__uncaught_exception

Gibt an, ob eine oder mehrere Ausnahmen ausgelöst wurden, aber noch nicht mit den entsprechenden bearbeitet wurden **catch** -Block eine [Try / Catch](../../cpp/try-throw-and-catch-statements-cpp.md) Anweisung.

## <a name="syntax"></a>Syntax

```cpp
bool __uncaught_exception(
   );
```

## <a name="return-value"></a>Rückgabewert

**"true"** ab dem Zeitpunkt, eine Ausnahme ausgelöst wird, eine **versuchen** blockieren, bis der passende **catch** Block ist, initialisiert wurde, andernfalls **"false"**.

## <a name="remarks"></a>Hinweise

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|__uncaught_exception|eh.h|

## <a name="see-also"></a>Siehe auch

[try-, throw- und catch-Anweisungen (C++)](../../cpp/try-throw-and-catch-statements-cpp.md)<br/>
