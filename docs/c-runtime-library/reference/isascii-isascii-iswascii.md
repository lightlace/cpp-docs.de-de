---
title: isascii, __isascii, iswascii | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- iswascii
- __isascii
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
- iswascii
- istascii
- __isascii
- _istascii
- isascii
- ctype/isascii
- ctype/__isascii
- corecrt_wctype/iswascii
dev_langs:
- C++
helpviewer_keywords:
- __isascii function
- _isascii function
- isascii function
- _istascii function
- istascii function
- iswascii function
ms.assetid: ba4325ad-7cb3-4fb9-b096-58906d67971a
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 401d8d05cc80ef1c72e7c72c06f94707b8c9848b
ms.contentlocale: de-de
ms.lasthandoff: 04/01/2017

---
# <a name="isascii-isascii-iswascii"></a>isascii, __isascii, iswascii
Bestimmt, ob ein angegebenes Zeichen ein ASCII-Zeichen ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
int __isascii(   
   int c   
);  
int iswascii(   
   wint_t c   
);  
#define isascii __isascii  
```  
  
#### <a name="parameters"></a>Parameter  
 `c`  
 Zu testende ganze Zahl.  
  
## <a name="return-value"></a>Rückgabewert  
 Jede dieser Routinen gibt einen Wert ungleich null zurück, wenn `c` eine bestimmte Darstellung eines ASCII-Zeichens ist. `__isascii`Gibt einen Wert ungleich NULL zurück, wenn `c` wird ein ASCII-Zeichen (im Bereich 0 x 00 – 0x7F). `iswascii` gibt einen Wert ungleich null zurück, wenn `c` eine Breitzeichendarstellung eines ASCII-Zeichens ist. Jede dieser Routinen gibt 0 zurück, wenn `c` die Testbedingung nicht erfüllt.  
  
## <a name="remarks"></a>Hinweise  
 `__isascii` und `iswascii` werden beide als Makros implementiert, es sei denn, das Präprozessormakro _CTYPE_DISABLE_MACROS ist definiert.  
  
 Für die Abwärtskompatibilität wird `isascii` nur als ein Makro implementiert, wenn [__STDC\_\_](../../preprocessor/predefined-macros.md) nicht definiert oder als 0 definiert wird; andernfalls ist es nicht definiert.  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_istascii`|`__isascii`|`__isascii`|`iswascii`|  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`isascii`, `__isascii`|C: \<ctype.h><br /><br /> C++: \<cctype> oder \<ctype.h>|  
|`iswascii`|C: \<wctype.h>, \<ctype.h>, oder \<wchar.h><br /><br /> C++: \<cwctype>, \<cctype>, \<wctype.h>, \<ctype.h>, oder \<wchar.h>|  
  
 Die Funktionen `isascii`, `__isascii` und `iswascii` sind Microsoft-spezifisch. Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="see-also"></a>Siehe auch  
 [Zeichenklassifizierung](../../c-runtime-library/character-classification.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [is, isw Routines (is- und isw-Routinen)](../../c-runtime-library/is-isw-routines.md)
