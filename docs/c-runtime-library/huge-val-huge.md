---
title: "HUGE_VAL, _HUGE"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "_HUGE"
apilocation: 
  - "msvcrt.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_HUGE"
  - "HUGE_VAL"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_HUGE-Konstante"
  - "HUGE_VAL-Konstante"
  - "Double-Wert"
ms.assetid: 3f044b45-02cd-46b2-b1de-87fd0441dd6a
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# HUGE_VAL, _HUGE
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntax  
  
```  
  
#include <math.h>  
  
```  
  
## Hinweise  
 `HUGE_VAL` ist der größte darstellbare double\-Wert.  Dieser Wert wird von vielen Ablaufmathematischen funktionen zurückgegeben, wenn ein Fehler auftritt.  Für einige Funktionen \-`HUGE_VAL` wird zurückgegeben.  `HUGE_VAL` wird als `_HUGE`, aber Änderungen mathematische Funktionen Rückhol\- `HUGE_VAL` definiert.  Sie sollten `HUGE_VAL` im Code auch aus Gründen der Einheitlichkeit verwenden.  
  
## Siehe auch  
 [Globale Konstanten](../c-runtime-library/global-constants.md)