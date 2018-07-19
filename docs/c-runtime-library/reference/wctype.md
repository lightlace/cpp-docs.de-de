---
title: wctype | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- wctype
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
apitype: DLLExport
f1_keywords:
- wctype
dev_langs:
- C++
helpviewer_keywords:
- wctype function
- wide characters
ms.assetid: 14aded12-4087-4123-bc48-db4e10999223
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0bb5003db02ed27c2906ebc3619313489e40e5fb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32411899"
---
# <a name="wctype"></a>wctype

Bestimmt eine Klassifizierungsregel für Breitzeichencodes.

## <a name="syntax"></a>Syntax

```C
wctype_t wctype(
   const char * property
);
```

### <a name="parameters"></a>Parameter

*Eigenschaft*<br/>
Eigenschaftszeichenfolge

## <a name="return-value"></a>Rückgabewert

Wenn die **LC_CTYPE** Kategorie des aktuellen Gebietsschemas definiert eine Klassifizierungsregel, deren Name mit der Eigenschaftszeichenfolge für die keine *Eigenschaft*, gibt die Funktion 0 (null) zurück. Andernfalls wird ein Wert ungleich 0 zurückgegeben, der für die Verwendung als das zweite Argument für einen nachfolgenden Aufruf von [towctrans](towctrans.md) geeignet ist.

## <a name="remarks"></a>Hinweise

Die Funktion bestimmt eine Klassifizierungsregel für Breitzeichencodes. Die folgenden Paare von Aufrufen weisen in allen Gebietsschemas das gleiche Verhalten auf (durch eine Implementierung können jedoch sogar im Gebietsschema „C“ zusätzliche Klassifizierungsregeln definiert werden):

|Funktion|Identisch mit|
|--------------|-------------|
|iswalnum(c)|Iswctype (C, Wctype ("" alnum ""))|
|iswalpha(c)|Iswctype (C, Wctype ("Alpha"))|
|iswcntrl(c)|Iswctype (C, Wctype ("Strg"))|
|iswdigit(c)|Iswctype (C, Wctype ("Digit"))|
|iswgraph(c)|Iswctype (C, Wctype ("Diagramm"))|
|iswlower(c)|Iswctype (C, Wctype ("niedriger"))|
|iswprint(c)|Iswctype (C, Wctype ("Print"))|
|iswpunct(c)|Iswctype (C, Wctype ("Interpunktion"))|
|iswspace(c)|Iswctype (C, Wctype ("Space"))|
|iswupper(c)|Iswctype (C, Wctype ("Upper"))|
|iswxdigit(c)|Iswctype (C, Wctype ("Xdigit"))|

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**wctype**|\<wctype.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Datenkonvertierung](../../c-runtime-library/data-conversion.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
