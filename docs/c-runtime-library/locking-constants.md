---
title: _locking-Konstanten | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _LK_RLCK
- _LK_NBLCK
- _LK_LOCK
- _LK_NBRLCK
- _LK_UNLCK
dev_langs: C++
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
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 799b00209463c90c61b4b497a88af39ba554cd01
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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