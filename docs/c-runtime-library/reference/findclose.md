---
title: _findclose
ms.date: 11/04/2016
api_name:
- _findclose
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
- api-ms-win-crt-filesystem-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _findclose
- findclose
helpviewer_keywords:
- _findclose function
- findclose function
ms.assetid: 9216c573-0878-444c-b5d7-cdaf16fb9163
ms.openlocfilehash: c67336cc12bcdee754edd40b91078faa83a17984
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957319"
---
# <a name="_findclose"></a>_findclose

Schließt das angegebene Suchhandle und gibt zugeordnete Ressourcen frei.

## <a name="syntax"></a>Syntax

```C
int _findclose(
   intptr_t handle
);
```

### <a name="parameters"></a>Parameter

*bewältigen*<br/>
Such handle, das von einem vorherigen-Befehl an **_findfirst**zurückgegeben wurde.

## <a name="return-value"></a>Rückgabewert

Bei erfolgreicher Ausführung gibt **_findclose** 0 zurück. Andernfalls wird-1 zurückgegeben und **errno** auf **ENOENT**festgelegt, um anzugeben, dass keine weiteren übereinstimmenden Dateien gefunden werden konnten.

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|
|--------------|---------------------|
|**_findclose**|\<io.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Systemaufrufe](../../c-runtime-library/system-calls.md)<br/>
[Dateinamen-Suchfunktionen](../../c-runtime-library/filename-search-functions.md)<br/>
