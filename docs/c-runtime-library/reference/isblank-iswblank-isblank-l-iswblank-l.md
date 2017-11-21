---
title: isblank, iswblank, _isblank_l, _iswblank_l | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- isblank
- _isblank_l
- iswblank
- _iswblank_l
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
- _iswblank_l
- isblank
- _istblank_l
- _istblank
- _isblank_l
- iswblank
dev_langs: C++
ms.assetid: 33ce96c0-f387-411a-8283-c3d2a69e56bd
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 69b64f699cd98a98355aac5d64bc84c779927ac4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="isblank-iswblank-isblankl-iswblankl"></a>isblank, iswblank, _isblank_l, _iswblank_l
Bestimmt, ob eine ganze Zahl ein Leerzeichen darstellt.  
  
## <a name="syntax"></a>Syntax  
  
```  
int isblank(  
   int c   
);  
int iswblank(  
   wint_t c   
);  
int _isblank_l(  
   int c,  
   _locale_t locale  
);  
int _iswblank_l(  
   wint_t c,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `c`  
 Zu testende ganze Zahl.  
  
 `locale`  
 Zu verwendendes Gebietsschema.  
  
## <a name="return-value"></a>Rückgabewert  
 Jede dieser Routinen gibt ungleich 0 (null) zurück, wenn `c` eine bestimmte Darstellung eines Leerzeichens oder eines horizontalen Tabstoppzeichens ist oder wenn es ein gebietsschemaspezifischer Zeichensatz ist, der zum Trennen von Wörtern in einer Textzeile verwendet wird. `isblank` gibt einen Wert ungleich 0 (null) zurück, wenn `c` ein Leerzeichen (0x20) oder horizontales Tabstoppzeichen (0x09) ist. Das Ergebnis der Testbedingung für die `isblank`-Funktionen hängt von der `LC_CTYPE`-Kategorieneinstellung des Gebietsschemas ab. Weitere Informationen finden Sie unter [setlocale,_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md). Die Versionen dieser Funktionen, die das `_l`-Suffix nicht verwenden, verwenden das aktuelle Gebietsschema für jedes vom Gebietsschema abhängige Verhalten; die Versionen mit dem `_l`-Suffix sind beinahe identisch, verwenden jedoch stattdessen den übergebenen Gebietsschemaparameter. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
 `iswblank` gibt einen Wert ungleich 0 (null) zurück, wenn `c` ein Breitzeichen ist, das einem Standardleerzeichen oder einem horizontalen Tabstoppzeichen entspricht.  
  
 Das Verhalten von `isblank` und `_isblank_l` ist nicht definiert, wenn `c` nicht EOF ist oder nicht im Bereich von 0 bis 0xFF liegt. Wenn eine CRT-Debugbibliothek verwendet wird und `c` keinem dieser Werte entspricht, lösen die Funktionen eine Assertion aus.  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_istblank`|`isblank`|[_ismbcblank](../../c-runtime-library/reference/ismbcgraph-functions.md)|`iswblank`|  
|`_istblank_l`|`_isblank_l`|[_ismbcblank_l](../../c-runtime-library/reference/ismbcgraph-functions.md)|`_iswblank_l`|  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`isblank`|\<ctype.h>|  
|`iswblank`|\<ctype.h> oder \<wchar.h>|  
|`_isblank_l`|\<ctype.h>|  
|`_iswblank_l`|\<ctype.h> oder \<wchar.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Zeichenklassifizierung](../../c-runtime-library/character-classification.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [is, isw Routines (is- und isw-Routinen)](../../c-runtime-library/is-isw-routines.md)