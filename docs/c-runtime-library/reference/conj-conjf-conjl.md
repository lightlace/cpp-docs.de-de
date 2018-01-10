---
title: conj, conjf, conjl | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- conj
- conjf
- conjl
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
- conj
- conjf
- conjl
- complex/conj
- complex/conjf
- complex/conjl
dev_langs: C++
helpviewer_keywords:
- conj function
- conjf function
- conjl function
ms.assetid: 792fccfa-19c6-4890-99f9-a3b89effccd6
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3ce33f536a97f5f78ae573a757402cc316e85f5d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="conj-conjf-conjl"></a>conj, conjf, conjl
Gibt die konjugiert komplexe Zahl einer komplexen Zahl zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
_Dcomplex conj(   
   _Dcomplex z   
);  
_Fcomplex conj(   
   _Fcomplex z   
);  // C++ only  
_Lcomplex conj(   
   _Lcomplex z   
);  // C++ only  
_Fcomplex conjf(   
   _Fcomplex z   
);  
_Lcomplex conjl(   
   _Lcomplex z   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `z`  
 Eine komplexe Zahl.  
  
## <a name="return-value"></a>Rückgabewert  
 Die konjugierte komplexe Zahl von `z`.  Das Ergebnis hat den gleichen Real- und Imaginärteil wie `z`, jedoch mit umgekehrtem Vorzeichen.  
  
## <a name="remarks"></a>Hinweise  
 Da C++ das Überladen zulässt, können Sie Überladungen von `conj` aufrufen, die `_Fcomplex`- und `_Lcomplex`-Werte verwenden und zurückgeben. In einem C-Programm nimmt `conj` immer einen `_Dcomplex` -Wert an, und gibt auch einen solchen zurück.  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|C-Header|C++-Header|  
|-------------|--------------|------------------|  
|`conj`,               `conjf`, `conjl`|\<complex.h>|\<ccomplex>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="see-also"></a>Siehe auch  
 [Alphabetical Function Reference (Alphabetische Funktionsreferenz)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [norm, normf, norml](../../c-runtime-library/reference/norm-normf-norml1.md)   
 [creal, crealf, creall](../../c-runtime-library/reference/creal-crealf-creall.md)   
 [cproj, cprojf, cprojl](../../c-runtime-library/reference/cproj-cprojf-cprojl.md)   
 [cimag, cimagf, cimagl](../../c-runtime-library/reference/cimag-cimagf-cimagl.md)   
 [carg, cargf, cargl](../../c-runtime-library/reference/carg-cargf-cargl.md)   
 [cabs, cabsf, cabsl](../../c-runtime-library/reference/cabs-cabsf-cabsl.md)