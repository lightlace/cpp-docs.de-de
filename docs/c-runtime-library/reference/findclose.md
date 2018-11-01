---
title: _findclose
ms.date: 11/04/2016
apiname:
- _findclose
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _findclose
- findclose
helpviewer_keywords:
- _findclose function
- findclose function
ms.assetid: 9216c573-0878-444c-b5d7-cdaf16fb9163
ms.openlocfilehash: 29010f8a502d463eeb6ca98837a1b7dae9f5ae6b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50538111"
---
# <a name="findclose"></a>_findclose

Schließt das angegebene Suchhandle und gibt zugeordnete Ressourcen frei.

## <a name="syntax"></a>Syntax

```C
int _findclose(
   intptr_t handle
);
```

### <a name="parameters"></a>Parameter

*Handle*<br/>
Von einem vorherigen Aufruf zurückgegebene Suchhandle **_findfirst**.

## <a name="return-value"></a>Rückgabewert

Im Erfolgsfall **_findclose** gibt 0 zurück. Andernfalls wird-1 zurückgegeben und legt **Errno** zu **ENOENT**, gibt an, dass keine übereinstimmenden Dateien gefunden werden.

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|
|--------------|---------------------|
|**_findclose**|\<io.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Systemaufrufe](../../c-runtime-library/system-calls.md)<br/>
[Dateinamen-Suchfunktionen](../../c-runtime-library/filename-search-functions.md)<br/>
