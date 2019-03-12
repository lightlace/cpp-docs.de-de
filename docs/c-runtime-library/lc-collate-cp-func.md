---
title: ___lc_collate_cp_func
ms.date: 11/04/2016
apiname:
- ___lc_collate_cp_func
apilocation:
- msvcr120.dll
- msvcrt.dll
- msvcr100.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr90.dll
apitype: DLLExport
f1_keywords:
- ___lc_collate_cp_func
helpviewer_keywords:
- ___lc_collate_cp_func
ms.assetid: 46ccc084-7ac9-4e5d-9138-e12cb5845615
ms.openlocfilehash: fac8b7ba2e9568dd53509e5cccbb96a6b2f1df8d
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57738880"
---
# <a name="lccollatecpfunc"></a>___lc_collate_cp_func

Interne CRT-Funktion. Ruft die aktuelle Sortierungscodeseite des Threads ab.

## <a name="syntax"></a>Syntax

```cpp
UINT ___lc_codepage_func(void);
```

## <a name="return-value"></a>Rückgabewert

Die aktuelle Sortierungscodeseite des Threads.

## <a name="remarks"></a>Anmerkungen

`___lc_collate_cp_func` ist eine interne CRT-Funktion, die von anderen CRT-Funktionen verwendet wird, um die aktuelle Sortierungscodeseite aus dem lokalen Threadspeicher für CRT-Daten abzurufen. Diese Information kann auch durch Verwendung der [_get_current_locale](../c-runtime-library/reference/get-current-locale.md)-Funktion gewonnen werden.

Interne CRT-Funktionen sind implementierungsspezifisch und mit jedem neuen Release Änderungen unterworfen. Ihre Verwendung in einem Code wird nicht empfohlen.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|`___lc_collate_cp_func`|crt\src\setlocal.h|

## <a name="see-also"></a>Siehe auch

[_get_current_locale](../c-runtime-library/reference/get-current-locale.md)<br/>
[setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)<br/>
[_create_locale, _wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)<br/>
[_free_locale](../c-runtime-library/reference/free-locale.md)
