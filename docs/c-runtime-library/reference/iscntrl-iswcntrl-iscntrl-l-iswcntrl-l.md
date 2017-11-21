---
title: iscntrl, iswcntrl, _iscntrl_l, _iswcntrl_l | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- iscntrl
- _iswcntrl_l
- _iscntrl_l
- iswcntrl
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
- _istcntrl_l
- _iswcntrl_l
- iswcntrl
- _iscntrl_l
- iscntrl
- _istcntrl
dev_langs: C++
helpviewer_keywords:
- iscntrl function
- _iscntrl_l function
- _iswcntrl_l function
- _istcntrl function
- istcntrl function
- iswcntrl function
- _istcntrl_l function
ms.assetid: 616eebf9-aed4-49ba-ba2c-8677c8fe6fb5
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 66e06a0a35980d28b03e3b0ba5b2e06ca6861e41
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="iscntrl-iswcntrl-iscntrll-iswcntrll"></a>iscntrl, iswcntrl, _iscntrl_l, _iswcntrl_l
Bestimmt, ob eine ganze Zahl ein Steuerzeichen darstellt.  
  
## <a name="syntax"></a>Syntax  
  
```  
int iscntrl(   
   int c   
);  
int iswcntrl(   
   wint_t c   
);  
int _iscntrl_l(   
   int c,  
   _locale_t locale  
);  
int _iswcntrl_l(   
   wint_t c,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `c`  
 Zu testende ganze Zahl  
  
 `locale`  
 Das zu verwendende Gebietsschema.  
  
## <a name="return-value"></a>Rückgabewert  
 Jede dieser Routinen gibt einen Wert ungleich 0 (null) zurück, wenn `c` eine bestimmte Darstellung eines Steuerzeichens ist. `iscntrl`Gibt einen Wert ungleich NULL zurück, wenn `c` ein Steuerzeichen ist (0 x 00 – 0x1F oder 0x7F). `iswcntrl` gibt einen Wert ungleich 0 (null) zurück, wenn `c` ein Steuerbreitzeichen ist. Jede dieser Routinen gibt 0 zurück, wenn `c` die Testbedingung nicht erfüllt.  
  
 Die Versionen dieser Funktionen mit dem `_l`-Suffix verwenden den ihnen übergebenen Gebietsschemaparameter anstelle des aktuellen Gebietsschemas. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
 Das Verhalten von `iscntrl` und `_iscntrl_l` ist nicht definiert, wenn `c` nicht EOF ist oder nicht im Bereich von 0 bis 0xFF liegt. Wenn eine CRT-Debugbibliothek verwendet wird und `c` keinem dieser Werte entspricht, lösen die Funktionen eine Assertion aus.  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_istcntrl`|`iscntrl`|`iscntrl`|`iswcntrl`|  
|`_istcntrl_l`|`_iscntrl_l`|`_iscntrl_l`|`_iswcntrl_l`|  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`iscntrl`|\<ctype.h>|  
|`iswcntrl`|\<ctype.h> oder \<wchar.h>|  
|`_iscntrl_l`|\<ctype.h>|  
|`_iswcntrl_l`|\<ctype.h> oder \<wchar.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Zeichenklassifizierung](../../c-runtime-library/character-classification.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [is, isw Routines (is- und isw-Routinen)](../../c-runtime-library/is-isw-routines.md)