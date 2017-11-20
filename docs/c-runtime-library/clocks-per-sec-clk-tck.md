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
ms.openlocfilehash: facd2469a4b95351d54addce663d0b036db38786
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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