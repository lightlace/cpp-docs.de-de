---
title: _abnormal_termination | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _abnormal_termination
apilocation:
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr90.dll
- msvcr120.dll
- msvcrt.dll
- msvcr80.dll
- msvcr100.dll
apitype: DLLExport
f1_keywords:
- _abnormal_termination
dev_langs:
- C++
helpviewer_keywords:
- _abnormal_termination
ms.assetid: 952970a4-9586-4c3d-807a-db729448c91c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fc205afd297c7cce87ae630369551e02f3109d88
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="abnormaltermination"></a>_abnormal_termination
Gibt an, ob der `__finally`-Block einer [try-finally-Anweisung](../cpp/try-finally-statement.md) eingegeben wurde, während das System eine interne Liste von Beendigungshandlern ausführt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
int   _abnormal_termination(  
   );  
```  
  
## <a name="return-value"></a>Rückgabewert  
 `true`, wenn das System einen Stapel *entlädt*; ansonsten `false`.  
  
## <a name="remarks"></a>Hinweise  
 Dies ist eine interne Funktion, die zum Verwalten von Entladungsausnahmen verwendet wird. Sie sollte nicht im Benutzercode aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|_abnormal_termination|excpt.h|  
  
## <a name="see-also"></a>Siehe auch  
 [try-finally-Anweisung](../cpp/try-finally-statement.md)