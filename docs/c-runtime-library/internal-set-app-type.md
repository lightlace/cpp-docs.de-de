---
title: __set_app_type
ms.date: 11/04/2016
apiname:
- __set_app_type
- _set_app_type
apilocation:
- msvcr90.dll
- msvcr100.dll
- msvcr110.dll
- msvcr80.dll
- msvcrt.dll
- msvcr120.dll
- msvcr110_clr0400.dll
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- __set_app_type
helpviewer_keywords:
- __set_app_type
ms.assetid: f0ac0f4d-70e6-4e96-9e43-eb9d1515490c
ms.openlocfilehash: f42ac1c173637cf85d727adf25ebf9079f4cb37c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50457485"
---
# <a name="setapptype"></a>__set_app_type

Legt den aktuellen Anwendungstyp fest.

## <a name="syntax"></a>Syntax

```cpp
void __set_app_type (
   int at
   )
```

#### <a name="parameters"></a>Parameter

*at*<br/>
Ein Wert, der den Anwendungstyp angibt. Mögliche Werte sind:

|Wert|Beschreibung |
|-----------|-----------------|
|_UNKNOWN_APP|Unbekannter Anwendungstyp.|
|_CONSOLE_APP|Konsolenanwendung (für Befehlszeilen).|
|_GUI_APP|GUI-Anwendung (in Windows).|

## <a name="remarks"></a>Hinweise

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|__set_app_type|internal.h|