---
title: _STATIC_ASSERT-Makro | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
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
f1_keywords: _STATIC_ASSERT
dev_langs: C++
helpviewer_keywords: _STATIC_ASSERT macro
ms.assetid: 89b0350c-2c2f-4be6-9786-8b1f0780a5da
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 686ac443eb32a9ca17e77baee95b50e06c6556b3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="staticassert-macro"></a>_STATIC_ASSERT-Makro
Auswerten eines Ausdrucks zur Kompilierzeit und Generieren eines Fehlers, wenn das Ergebnis `FALSE` ist  
  
## <a name="syntax"></a>Syntax  
  
```  
_STATIC_ASSERT(  
    booleanExpression  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `booleanExpression`  
 Ausdruck (einschließlich Zeiger) der zu ungleich null (`TRUE`) oder 0 (`FALSE`) ausgewertet wird.  
  
## <a name="remarks"></a>Hinweise  
 Dieses Makro ähnelt den [_ASSERT- und _ASSERTE-Makros](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md), außer dass `booleanExpression` zur Kompilierzeit und nicht zur Laufzeit ausgewertet wird. Wenn `booleanExpression` `FALSE` (0) ergibt, wird [Compilerfehler C2466](../../error-messages/compiler-errors-1/compiler-error-c2466.md) generiert.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird überprüft, ob das `sizeof` eines `int` größer als oder gleich 2 Bytes und das `sizeof` eines `long` 1 Byte ist. Das Programm wird nicht kompiliert und generiert [Compiler-Fehler C2466](../../error-messages/compiler-errors-1/compiler-error-c2466.md), da ein `long` größer als 1 Byte ist.  
  
```  
// crt__static_assert.c  
  
#include <crtdbg.h>  
#include <stdio.h>  
  
_STATIC_ASSERT(sizeof(int) >= 2);  
_STATIC_ASSERT(sizeof(long) == 1);  // C2466  
  
int main()  
{  
    printf("I am sure that sizeof(int) will be >= 2: %d\n",  
        sizeof(int));  
    printf("I am not so sure that sizeof(long) == 1: %d\n",  
        sizeof(long));  
}  
```  
  
## <a name="requirements"></a>Anforderungen  
  
|Makro|Erforderlicher Header|  
|-----------|---------------------|  
|`_STATIC_ASSERT`|\<crtdbg.h>|  
  
## <a name="see-also"></a>Siehe auch  
 [Alphabetische Funktionsreferenz](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [_ASSERT-, _ASSERTE-, _ASSERT_EXPR-Makros](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)