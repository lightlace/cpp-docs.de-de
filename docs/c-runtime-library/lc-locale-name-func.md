---
title: ___lc_locale_name_func
ms.date: 11/04/2016
apiname:
- ___lc_locale_name_func
apilocation:
- msvcrt.dll
- msvcr110.dll
- msvcr100.dll
- msvcr90.dll
- msvcr120.dll
- msvcr80.dll
- msvcr110_clr0400.dll
apitype: DLLExport
f1_keywords:
- ___lc_locale_name_func
helpviewer_keywords:
- ___lc_locale_name_func
ms.assetid: ef858308-872e-43de-95e0-9b1b4084343e
ms.openlocfilehash: 17724fe5335ba54d7e32ed7851b6a35b132b1086
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50639841"
---
# <a name="lclocalenamefunc"></a>___lc_locale_name_func

Interne CRT-Funktion. Ruft die aktuellen Gebietsschemanamen des Threads ab.

## <a name="syntax"></a>Syntax

```cpp
wchar_t** ___lc_locale_name_func(void);
```

## <a name="return-value"></a>Rückgabewert

Ein Zeiger auf eine Zeichenfolge, die den aktuellen Gebietsschemanamen des Threads enthält.

## <a name="remarks"></a>Hinweise

`___lc_locale_name_func` ist eine interne CRT-Funktion, die von anderen CRT-Funktionen verwendet wird, um den aktuellen Gebietsschemanamen aus dem lokalen Threadspeicher für CRT-Daten abzurufen. Diese Information ist auch mit Verwendung der Funktion [_get_current_locale](../c-runtime-library/reference/get-current-locale.md) oder der Funktionen [Setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) verfügbar.

Interne CRT-Funktionen sind implementierungsspezifisch und mit jedem neuen Release Änderungen unterworfen. Ihre Verwendung in einem Code wird nicht empfohlen.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|`___lc_locale_name_func`|crt\src\setlocal.h|

## <a name="see-also"></a>Siehe auch

[_get_current_locale](../c-runtime-library/reference/get-current-locale.md)<br/>
[setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)<br/>
[_create_locale, _wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)<br/>
[_free_locale](../c-runtime-library/reference/free-locale.md)