---
title: clog, clogf, clogl | Microsoft-Dokumentation
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
- clog
- clogf
- clogl
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
- clog
- clogf
- clogl
- complex/clog
- complex/clogf
- complex/clogl
dev_langs: C++
helpviewer_keywords:
- clog function
- clogf function
- clogl function
ms.assetid: 870b9b0b-6618-46f3-bfcf-da595cbd5e18
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 09cc64d10c997702e4dde2cff2b40ee4568bf42e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="clog-clogf-clogl"></a>clog, clogf, clogl
Ruft den natürlichen Logarithmus einer komplexen Zahl mit einem Achsenabschnitt auf der negativen reellen Achse ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
_Dcomplex clog(   
   _Dcomplex z   
);  
_Fcomplex clog(   
   _Fcomplex z   
);  // C++ only  
_Lcomplex clog(   
   _Lcomplex z   
);  // C++ only  
_Fcomplex clogf(   
   _Fcomplex z   
);  
_Lcomplex clogl(   
   _Lcomplex z   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `z`  
 Die Basis des Logarithmus.  
  
## <a name="return-value"></a>Rückgabewert  
 Der natürliche Logarithmus von `z`. Das Ergebnis ist unbounded entlang der echte und im Intervall [-Iπ, + Iπ] der imaginäre Achse.  
  
 Die möglichen Rückgabewerte sind:  
  
|z Parameter|Rückgabewert|  
|-----------------|------------------|  
|Positiv|Der Logarithmus zur Basis 10 von z|  
|Zero|- ∞|  
|Negativ|NaN|  
|NaN|NaN|  
|+ ∞|+ ∞|  
  
## <a name="remarks"></a>Hinweise  
 Da C++ das Überladen zulässt, können Sie Überladungen von `clog` aufrufen, die `_Fcomplex`- und `_Lcomplex`-Werte verwenden und zurückgeben. In einem C-Programm nimmt `clog` immer einen `_Dcomplex` -Wert an, und gibt auch einen solchen zurück.  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|C-Header|C++-Header|  
|-------------|--------------|------------------|  
|`clog`,               `clogf`, `clogl`|\<complex.h>|\<ccomplex>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="see-also"></a>Siehe auch  
 [Alphabetical Function Reference (Alphabetische Funktionsreferenz)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [cexp, cexpf, cexpl](../../c-runtime-library/reference/cexp-cexpf-cexpl.md)   
 [cpow, cpowf, cpowl](../../c-runtime-library/reference/cpow-cpowf-cpowl.md)   
 [clog10, clog10f, clog10l](../../c-runtime-library/reference/clog10-clog10f-clog10l.md)