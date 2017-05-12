---
title: copysign, copysignf, copysignl, _copysign, _copysignf, _copysignl | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- copysignf
- copysignl
- _copysignl
- _copysign
- _copysignf
- copysign
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
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _copysignl
- copysign
- copysignf
- _copysign
- copysignl
- _copysignf
dev_langs:
- C++
helpviewer_keywords:
- copysignl function
- _copysignl function
- copysign function
- _copysignf function
- _copysign function
- copysignf function
ms.assetid: 009216d6-72a2-402d-aa6c-91d924b2c9e4
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
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
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: eacbc58af19bf5b2a038021c982e348a50fa9271
ms.contentlocale: de-de
ms.lasthandoff: 03/29/2017

---
# <a name="copysign-copysignf-copysignl-copysign-copysignf-copysignl"></a>copysign, copysignf, copysignl, _copysign, _copysignf, _copysignl
Gibt einen Wert zurück, der die Größe eines Arguments und das Zeichen eines anderen Arguments aufweist.  
  
## <a name="syntax"></a>Syntax  
  
```  
double copysign(   
   double x,  
   double y   
);  
float copysign(   
   float x,  
   float y   
); // C++ only  
long double copysign(   
   long double x,  
   long double y   
); // C++ only  
float copysignf(   
   float x,  
   float y   
); // C++ only  
long double copysignl(   
   long double x,  
   long double y   
); // C++ only  
double _copysign(   
   double x,  
   double y   
);  
long double _copysignl(   
   long double x,  
   long double y   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `x`  
 Der Gleitkommawert, der als Betrag des Ergebnisses zurückgegeben wird.  
  
 `y`  
 Der Gleitkommawert, der als Zeichen des Ergebnisses zurückgegeben wird.  
  
 [Floating-Point Support Routines (Routinen für die Gleitkommaunterstützung)](../../c-runtime-library/floating-point-support.md)  
  
## <a name="return-value"></a>Rückgabewert  
 Die `copysign`-Funktionen geben einen Gleitkommawert zurück, der die Größe von `x` und das Zeichen von `y` kombiniert. Es gibt keine Fehlerrückgabe.  
  
## <a name="remarks"></a>Hinweise  
 Da C++ das Überladen zulässt, können Sie Überladungen von `copysign` aufrufen, die `float` oder `long double`-Werte verwenden und zurückgeben. In einem C-Programm verwendet `copysign` immer `double` und gibt diesen Wert zurück.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_copysign`|\<float.h>|  
|`copysign`, `copysignf`, `copysignl`, `_copysignf`, `_copysignl`|\<math.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Siehe auch  
 [fabs, fabsf, fabsl](../../c-runtime-library/reference/fabs-fabsf-fabsl.md)   
 [_chgsign, _chgsignf, _chgsignl](../../c-runtime-library/reference/chgsign-chgsignf-chgsignl.md)
