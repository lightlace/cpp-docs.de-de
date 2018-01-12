---
title: __max | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: __max
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
- max
- __max
dev_langs: C++
helpviewer_keywords:
- max macro
- maximum macro
- __max macro
ms.assetid: 05c936f6-0e22-45d6-a58d-4bc102e9dae2
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 585d2a295bedb8b0ba49a893d5089bc682a1debd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="max"></a>__max
Gibt den größeren der beiden Werte zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
type __max(  
   type a,  
   type b   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `type`  
 Jeder beliebige numerische Datentyp.  
  
 `a, b`  
 Werte von einem numerischen Datentyp, der verglichen werden soll.  
  
## <a name="return-value"></a>Rückgabewert  
 `__max` gibt das größere der Argumente zurück.  
  
## <a name="remarks"></a>Hinweise  
 Das `__max`-Makro vergleicht zwei Werte und gibt den größeren Wert zurück. Die Argumente können von einen beliebigen Datentyp stammen, signed oder unsigned. Beide Argumente sowie der Rückgabewert müssen demselben Datentyp entsprechen.  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`__max`|\<stdlib.h>|  
  
## <a name="example"></a>Beispiel  
 Weitere Informationen finden Sie im Beispiel für [__min](../../c-runtime-library/reference/min.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Floating-Point Support (Gleitkommaunterstützung)](../../c-runtime-library/floating-point-support.md)   
 [__min](../../c-runtime-library/reference/min.md)