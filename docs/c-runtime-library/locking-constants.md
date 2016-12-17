---
title: "_locking-Konstanten"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "_LK_RLCK"
  - "_LK_NBLCK"
  - "_LK_LOCK"
  - "_LK_NBRLCK"
  - "_LK_UNLCK"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_LK_LOCK-Konstante"
  - "_LK_NBLCK-Konstante"
  - "_LK_NBRLCK-Konstante"
  - "_LK_RLCK-Konstante"
  - "_LK_UNLCK-Konstante"
  - "LK_LOCK-Konstante"
  - "LK_NBLCK-Konstante"
  - "LK_NBRLCK-Konstante"
  - "LK_RLCK-Konstante"
  - "LK_UNLCK-Konstante"
ms.assetid: c3dc92c8-60e3-4d29-9f50-5d217627c8ad
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# _locking-Konstanten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntax  
  
```  
  
#include <sys/locking.h>  
  
```  
  
## Hinweise  
 Das *Modusargument* im Aufruf der Funktion `_locking` wird der Sperrenaktion ausgeführt werden.  
  
 Das *Modusargument* muss eine der folgenden Manifestkonstanten sein.  
  
 `_LK_LOCK`  
 Sperrt die angegebenen Bytes.  Wenn die Bytes nicht gesperrt werden können, wird die Funktion erneut nach 1 Second.  Wenn, nach 10 Versuchen, die Bytes nicht gesperrt werden können, gibt die Funktion einen Fehler zurück.  
  
 `_LK_RLCK`  
 Dieselbe Bedeutung wie `_LK_LOCK`.  
  
 `_LK_NBLCK`  
 Sperrt die angegebenen Bytes.  Wenn Bytes nicht gesperrt werden können, gibt die Funktion einen Fehler zurück.  
  
 `_LK_NBRLCK`  
 Dieselbe Bedeutung wie `_LK_NBLCK`.  
  
 `_LK_UNLCK`  
 Setzt die angegebenen Bytes frei. \(Die Bytes müssen zuvor gesperrt werden.\)  
  
## Siehe auch  
 [\_locking](../c-runtime-library/reference/locking.md)   
 [Globale Konstanten](../c-runtime-library/global-constants.md)