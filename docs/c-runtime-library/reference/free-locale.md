---
title: _free_locale
ms.date: 11/04/2016
apiname:
- _free_locale
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
- __free_locale
- free_locale
- _free_locale
helpviewer_keywords:
- __free_locale function
- free_locale function
- locales, freeing
- _free_locale function
ms.assetid: 1f08d348-ab32-4028-a145-6cbd51b49af9
ms.openlocfilehash: 92dc8cd711087e8e797b484d6c7e3c6c3b031b5c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62333039"
---
# <a name="freelocale"></a>_free_locale

Gibt ein locale-Objekt frei

## <a name="syntax"></a>Syntax

```C
void _free_locale(
   _locale_t locale
);
```

### <a name="parameters"></a>Parameter

*locale*<br/>
Das freizugebende locale-Objekt

## <a name="remarks"></a>Hinweise

Die **_free_locale** Funktion dient zum Freigeben des Locale-Objekts, das von einem Aufruf abgerufen **_get_current_locale** oder **_create_locale**.

Der vorherige Name dieser Funktion **__free_locale** (mit zwei führenden unterstrichen) ist veraltet.

## <a name="requirements"></a>Anforderungen

|**Routine**|Erforderlicher Header|
|---------------|---------------------|
|**_free_locale**|\<locale.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[_get_current_locale](get-current-locale.md)<br/>
[_create_locale, _wcreate_locale](create-locale-wcreate-locale.md)<br/>
