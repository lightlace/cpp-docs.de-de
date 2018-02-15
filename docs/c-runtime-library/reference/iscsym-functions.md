---
title: iscsym, iscsymf, __iscsym, __iswcsym, __iscsymf, __iswcsymf, _iscsym_l, _iswcsym_l, _iscsymf_l, _iswcsymf_l | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _iswcsym_l
- __iswcsym
- __iscsym
- _iswcsymf_l
- _iscsym_l
- __iswcsymf
- __iscsymf
- _iscsymf_l
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
- _iswcsym_l
- _iswcsymf_l
- iscsymf
- iswcsymf
- __iswcsym
- __iswcsymf
- iscsym
- iswcsym
- __iscsym
- _iscsym_l
- _iscsymf_l
- __iscsymf
- ctype/iscsym
- ctype/iscsymf
- ctype/__iscsym
- ctype/__iscsymf
- ctype/__iscsym_l
- ctype/__iscsymf_l
- ctype/__iswcsym
- ctype/__iswcsymf
- ctype/__iswcsym_l
- ctype/__iswcsymf_l
dev_langs:
- C++
helpviewer_keywords:
- iscsymf_l function
- iswsym_l function
- _iswcsym_l function
- iscsym_l function
- _iscsymf_l function
- _iswcsymf_l function
- _iscsym_l function
- __iscsym function
- __iswcsymf function
- iswsymf_l function
- __iscsymf function
- __iswcsym function
- iscsym function
- iscsymf function
ms.assetid: 944dfb99-f2b8-498c-9f55-dbcf370d0a2c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 85c650efa09bb093da65be874c890c77282d3fa3
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="iscsym-iscsymf-iscsym-iswcsym-iscsymf-iswcsymf-iscsyml-iswcsyml-iscsymfl-iswcsymfl"></a>iscsym, iscsymf, __iscsym, __iswcsym, __iscsymf, __iswcsymf, _iscsym_l, _iswcsym_l, _iscsymf_l, _iswcsymf_l

Bestimmt, ob eine Ganzzahl ein Zeichen darstellt, das in einem Bezeichner verwendet werden kann.

## <a name="syntax"></a>Syntax

```C
int __iscsym(
   int c
);
int __iswcsym(
   wint_t c
);
int __iscsymf(
   int c
);
int __iswcsymf(
   wint_t c
);
int _iscsym_l(
   int c,
   _locale_t locale
);
int _iswcsym_l(
   wint_t c,
   _locale_t locale
);
int _iscsymf_l(
   int c,
   _locale_t locale
);
int _iswcsymf_l(
   wint_t c,
   _locale_t locale
);
#define iscsym __iscsym
#define iscsymf __iscsymf
```

### <a name="parameters"></a>Parameter

*c*  
Zu testende ganze Zahl. *c* muss im Bereich von 0 bis 255 schmalen Zeichen Version der Funktion.

*locale*  
Das zu verwendende Gebietsschema.

## <a name="return-value"></a>Rückgabewert

Beide `__iscsym` und `__iswcsym` einen Wert ungleich NULL zurück, wenn *c* ist ein Buchstabe, Unterstrich oder Ziffer. Beide `__iscsymf` und `__iswcsymf` einen Wert ungleich NULL zurück, wenn *c* ein Buchstabe oder Unterstrich. Jede dieser Routinen gibt 0 zurück, wenn *c* die testbedingung nicht erfüllt. Die Versionen dieser Funktionen mit dem `_l` -Suffix sind beinahe identisch, verwenden jedoch den *Gebietsschema* übergebenen Gebietsschemaparameter anstelle des aktuellen Gebietsschemas für ihr vom Gebietsschema abhängiges Verhalten. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

## <a name="remarks"></a>Hinweise

Diese Routinen werden als Makros implementiert, es sei denn, die Präprozessormakro _CTYPE_DISABLE_MACROS ist definiert. Wenn Sie die Makroversionen dieser Routinen verwenden, können die Argumente mehr als einmal ausgewertet werden. Seien Sie vorsichtig, wenn Sie Ausdrücke mit Nebeneffekten in der Argumentliste verwenden.

Für die Abwärtskompatibilität `iscsym` und `iscsymf` sind definiert als Makros nur, wenn [&#95; &#95; STDC++ &#95; &#95; ](../../preprocessor/predefined-macros.md) ist nicht definiert oder wird definiert als 0 ist; andernfalls sind sie nicht definiert.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|`iscsym`, `iscsymf`, `__iscsym`, `__iswcsym`, `__iscsymf`, `__iswcsymf`, `_iscsym_l`, `_iswcsym_l`, `_iscsymf_l`, `_iswcsymf_l`|C: \<ctype.h><br /><br /> C++: \<cctype> oder \<ctype.h>|

The `iscsym`-, `iscsymf`-, `__iscsym`-, `__iswcsym`-, `__iscsymf`-, `__iswcsymf`-, `_iscsym_l`-, `_iswcsym_l`-, `_iscsymf_l`-, und `_iswcsymf_l`-Routinen sind Microsoft-spezifisch. Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Zeichenklassifizierung](../../c-runtime-library/character-classification.md)   
[Gebietsschema](../../c-runtime-library/locale.md)   
[is, isw Routines (is- und isw-Routinen)](../../c-runtime-library/is-isw-routines.md)