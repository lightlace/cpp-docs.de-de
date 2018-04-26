---
title: _isctype, iswctype, _isctype_l, _iswctype_l | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _isctype_l
- iswctype
- _iswctype_l
- _isctype
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- iswctype
- _isctype
- _isctype_l
- _iswctype
- isctype
- iswctype_l
- isctype_l
- _iswctype_l
dev_langs:
- C++
helpviewer_keywords:
- isctype_l function
- iswctype_l function
- iswctype function
- _isctype function
- _isctype_l function
- _iswctype_l function
- isctype function
- _iswctype function
ms.assetid: cf7509b7-12fc-4d95-8140-ad2eb98173d3
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 25df7ddaaea8c1f4df0907ebd92827f2a4865007
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="isctype-iswctype-isctypel-iswctypel"></a>_isctype, iswctype, _isctype_l, _iswctype_l

Tests *c* für die Ctype-Eigenschaft, die gemäß der *"DESC"* Argument. Für jeden gültigen Wert des *"DESC"*, es wird eine entsprechende breitzeichenklassifizierungs-Routine.

## <a name="syntax"></a>Syntax

```C
int _isctype(
   int c,
   _ctype_t desc
);
int _isctype_l(
   int c,
   _ctype_t desc,
   _locale_t locale
);
int iswctype(
   wint_t c,
   wctype_t desc
);
int _iswctype_l(
   wint_t c,
   wctype_t desc,
   _locale_t locale
);
```

### <a name="parameters"></a>Parameter

*c*<br/>
Zu testende ganze Zahl.

*"DESC"*<br/>
Eigenschaft, für die der Test durchgeführt werden soll. Diese wird normalerweise mithilfe von ctype oder [wctype](wctype.md) abgerufen.

*locale*<br/>
Das für alle gebietsschemaabhängigen Tests zu verwendende Gebietsschema.

## <a name="return-value"></a>Rückgabewert

**_isctype** und **Iswctype** einen Wert ungleich NULL zurück, wenn *c* wurde durch die angegebene Eigenschaft *"DESC"* in das aktuelle Gebietsschema oder 0, wenn dies nicht der Fall. Die Versionen dieser Funktionen mit dem **_l** -Suffix sind beinahe identisch, außer dass sie das Gebietsschema für den übergebenen Gebietsschemaparameter anstelle des aktuellen Gebietsschemas für ihr vom Gebietsschema abhängiges Verhalten verwenden. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

Das Verhalten des **_isctype** und **_isctype_l** ist undefiniert, wenn *c* nicht EOF ist oder im Bereich von 0 bis 0xFF liegt. Wenn eine CRT-Debugbibliothek verwendet wird und *c* ist keine dieser Werte, lösen die Funktionen eine Assertion.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|
|---------------------|--------------------------------------|--------------------|-----------------------|
|n/v|**_isctype**|n/v|**_iswctype**|
|n/v|**_isctype_l**|n/v|**_iswctype_l**|

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_isctype**|\<ctype.h>|
|**iswctype**|\<ctype.h> oder \<wchar.h>|
|**_isctype_l**|\<ctype.h>|
|**_iswctype_l**|\<ctype.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Alle Versionen [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Siehe auch

[Zeichenklassifizierung](../../c-runtime-library/character-classification.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[is, isw Routines (is- und isw-Routinen)](../../c-runtime-library/is-isw-routines.md)<br/>
