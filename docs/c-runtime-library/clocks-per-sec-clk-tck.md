---
title: CLOCKS_PER_SEC, CLK_TCK | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CLOCKS_PER_SEC
- CLK_TCK
dev_langs: C++
helpviewer_keywords:
- CLOCKS_PER_SEC
- CLK_TCK constant
ms.assetid: bc285106-383d-44cb-91bf-276ad7de57bf
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b728dd56b8f0b3540b92c5243a566da77b5e12d4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="clockspersec-clktck"></a>CLOCKS_PER_SEC, CLK_TCK
## <a name="syntax"></a>Syntax  
  
```  
  
#include <time.h>  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Zeit in Sekunden ist der von der `clock`-Funktion zurückgegebene Wert, geteilt durch `CLOCKS_PER_SEC`. `CLK_TCK` ist die Entsprechung, wird jedoch als veraltet eingestuft.  
  
## <a name="see-also"></a>Siehe auch  
 [clock](../c-runtime-library/reference/clock.md)   
 [Globale Konstanten](../c-runtime-library/global-constants.md)