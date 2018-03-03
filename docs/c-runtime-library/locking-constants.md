---
title: _locking-Konstanten | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _LK_RLCK
- _LK_NBLCK
- _LK_LOCK
- _LK_NBRLCK
- _LK_UNLCK
dev_langs:
- C++
helpviewer_keywords:
- LK_UNLCK constant
- LK_NBRLCK constant
- _LK_NBRLCK constant
- _LK_NBLCK constant
- _LK_LOCK constant
- LK_NBLCK constant
- _LK_UNLCK constant
- LK_RLCK constant
- _LK_RLCK constant
- LK_LOCK constant
ms.assetid: c3dc92c8-60e3-4d29-9f50-5d217627c8ad
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a4231235fc35a8b6d22f49e2ba05db337a619713
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="locking-constants"></a>_locking-Konstanten
## <a name="syntax"></a>Syntax  
  
```  
  
#include <sys/locking.h>  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Das *mode*-Argument im Aufruf der `_locking`-Funktion gibt die auszuführende Sperraktion an.  
  
 Das *mode*-Argument muss eine der folgenden Manifestkonstanten sein.  
  
 `_LK_LOCK`  
 Sperrt die angegebenen Bytes. Wenn die Bytes nicht gesperrt werden können, führt die Funktion nach 1 Sekunde einen neuen Versuch durch. Wenn nach 10 Versuchen die Bytes nicht gesperrt werden können, gibt die Funktion einen Fehler zurück.  
  
 `_LK_RLCK`  
 Wie in `_LK_LOCK`.  
  
 `_LK_NBLCK`  
 Sperrt die angegebenen Bytes. Wenn die Bytes nicht gesperrt werden können, gibt die Funktion einen Fehler zurück.  
  
 `_LK_NBRLCK`  
 Wie in `_LK_NBLCK`.  
  
 `_LK_UNLCK`  
 Entsperrt die angegebenen Bytes. (Die Bytes müssen zuvor gesperrt worden sein.)  
  
## <a name="see-also"></a>Siehe auch  
 [_locking](../c-runtime-library/reference/locking.md)   
 [Globale Konstanten](../c-runtime-library/global-constants.md)