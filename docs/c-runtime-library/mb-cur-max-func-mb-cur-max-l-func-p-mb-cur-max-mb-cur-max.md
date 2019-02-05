---
title: ___mb_cur_max_func, ___mb_cur_max_l_func, __p___mb_cur_max, __mb_cur_max
ms.date: 11/04/2016
apiname:
- ___mb_cur_max_l_func
- __p___mb_cur_max
- ___mb_cur_max_func
- __mb_cur_max
apilocation:
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr80.dll
- msvcr100.dll
- msvcrt.dll
- msvcr90.dll
- msvcr120.dll
- api-ms-win-crt-locale-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- ___mb_cur_max_func
- ___mb_cur_max_l_func
- __p___mb_cur_max
- __mb_cur_max
helpviewer_keywords:
- __mb_cur_max
- ___mb_cur_max_func
- ___mb_cur_max_l_func
- __p___mb_cur_max
ms.assetid: 60d36108-1ca7-45a6-8ce7-68a91f13e3a1
ms.openlocfilehash: e59f487825b49c8ee6fefe41b41100b571619c6c
ms.sourcegitcommit: e98671a4f741b69d6277da02e6b4c9b1fd3c0ae5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2019
ms.locfileid: "55702790"
---
# <a name="mbcurmaxfunc-mbcurmaxlfunc-pmbcurmax-mbcurmax"></a>___mb_cur_max_func, ___mb_cur_max_l_func, __p___mb_cur_max, __mb_cur_max

Interne CRT-Funktion. Ruft die maximale Anzahl von Bytes in einem Multibyte-Zeichen für das aktuelle oder ein angegebenes Gebietsschema ab.

## <a name="syntax"></a>Syntax

```cpp
int ___mb_cur_max_func(void);
int ___mb_cur_max_l_func(_locale_t locale);
int * __p___mb_cur_max(void);
#define __mb_cur_max (___mb_cur_max_func())
```

#### <a name="parameters"></a>Parameter

locale: Die Struktur des Gebietsschemas, aus dem das Ergebnis abgerufen werden soll. Wenn dieser Wert null ist, wird das Gebietsschema des aktuellen Threads verwendet.

## <a name="return-value"></a>Rückgabewert

Die maximale Anzahl von Bytes in einem Multibyte-Zeichen für das Gebietsschema des aktuelles Threads oder das angegebene Gebietsschema.

## <a name="remarks"></a>Hinweise

Dies ist eine interne Funktion, die CRT nutzt, um den aktuellen Wert des Makros [MB_CUR_MAX](../c-runtime-library/mb-cur-max.md) aus dem lokalen Threadspeicher abzurufen. Wir empfehlen, das Makro `MB_CUR_MAX` in Ihrem Code für Übertragbarkeit zu nutzen.

Das Makro `__mb_cur_max` ist ein bequemer Weg zum Aufrufen der Funktion `___mb_cur_max_func()`. Die Funktion `__p___mb_cur_max` ist für eine Kompatibilität mit Visual C++ 5.0 und früheren Versionen definiert.

Interne CRT-Funktionen sind implementierungsspezifisch und mit jeder neuen Veröffentlichung Änderungen unterworfen. Ihre Verwendung in einem Code wird nicht empfohlen.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|`___mb_cur_max_func`, `___mb_cur_max_l_func`, `__p___mb_cur_max`|\<ctype.h>, \<stdlib.h>|

## <a name="see-also"></a>Siehe auch

[MB_CUR_MAX](../c-runtime-library/mb-cur-max.md)