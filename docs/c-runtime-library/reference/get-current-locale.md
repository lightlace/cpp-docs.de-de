---
title: _get_current_locale | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _get_current_locale
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
- api-ms-win-crt-locale-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- get_current_locale
- __get_current_locale
- _get_current_locale
dev_langs:
- C++
helpviewer_keywords:
- get_current_locale function
- _get_current_locale function
- locales, getting information on
- __get_current_locale function
ms.assetid: 572217f2-a37a-4105-a293-a250b4fabd99
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c6f20e69ca3ace4214915cd22f00fe2c9e8c9ffd
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="getcurrentlocale"></a>_get_current_locale

Ruft ein Gebietsschemaobjekt auf, das das aktuelle Gebietsschema darstellt.

## <a name="syntax"></a>Syntax

```C
_locale_t _get_current_locale(void);
```

## <a name="return-value"></a>Rückgabewert

Ein Gebietsschemaobjekt, das das aktuelle Gebietsschema darstellt.

## <a name="remarks"></a>Hinweise

Die **_get_current_locale** Funktion ruft die aktuell festgelegten Gebietsschema des Threads und gibt ein Locale-Objekt, das diesem Gebietsschema darstellt.

Der vorherige Name dieser Funktion **__get_current_locale** (mit zwei führenden unterstrichen) ist veraltet.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_get_current_locale**|\<locale.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[_create_locale, _wcreate_locale](create-locale-wcreate-locale.md)<br/>
[_free_locale](free-locale.md)<br/>
