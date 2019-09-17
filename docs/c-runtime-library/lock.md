---
title: _lock
ms.date: 11/04/2016
api_name:
- _lock
api_location:
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr100.dll
- msvcr90.dll
- msvcr80.dll
- msvcr110.dll
- msvcrt.dll
- msvcr120_clr0400.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- lock
- _lock
helpviewer_keywords:
- lock function
- _lock function
ms.assetid: 29f77c37-30de-4b3d-91b6-030216e645a6
ms.openlocfilehash: 666fdb8febebe133ae09ef3632cb38b6527d1210
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70944495"
---
# <a name="_lock"></a>_lock

Ruft eine Multi-Thread-Sperre ab.

> [!IMPORTANT]
>  Diese Funktion ist veraltet. Von Visual Studio 2015 an ist sie nicht in der CRT verfügbar.

## <a name="syntax"></a>Syntax

```
void __cdecl _lock
   int locknum
);
```

#### <a name="parameters"></a>Parameter

*locknum*<br/>
[in]: Der Bezeichner der abzurufenden Sperre.

## <a name="remarks"></a>Anmerkungen

Wenn die Sperre bereits abgerufen wurde, ruft diese Methode die Sperre dennoch ab und verursacht einen internen C-Laufzeitfehler (CRT). Wenn die Methode keine Sperre abrufen kann, wird sie mit einem schwerwiegenden Fehler beendet und der Fehlercode auf `_RT_LOCK`festgelegt.

## <a name="requirements"></a>Requirements (Anforderungen)

**Quelle:** mlock.c

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
[_unlock](../c-runtime-library/unlock.md)
