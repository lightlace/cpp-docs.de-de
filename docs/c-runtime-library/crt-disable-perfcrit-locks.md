---
title: _CRT_DISABLE_PERFCRIT_LOCKS | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _CRT_DISABLE_PERFCRIT_LOCKS
- CRT_DISABLE_PERFCRIT_LOCKS
dev_langs: C++
helpviewer_keywords:
- CRT_DISABLE_PERFCRIT_LOCKS constant
- _CRT_DISABLE_PERFCRIT_LOCKS constant
ms.assetid: 36cc2d86-cdb1-4b2b-a03c-c0d3818e7c6f
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: bb9a5662b15e6e4d0b6df09520263528f9fa72c5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="crtdisableperfcritlocks"></a>_CRT_DISABLE_PERFCRIT_LOCKS
Deaktiviert die leistungskritische Sperre bei E/A-Vorgängen.  
  
## <a name="syntax"></a>Syntax  
  
```  
#define _CRT_DISABLE_PERFCRIT_LOCKS  
```  
  
## <a name="remarks"></a>Hinweise  
 Durch die Definition dieses Symbols kann die Leistung in Singlethread-E/A-gebundenen Programmen verbessert werden, indem bei allen E/A-Vorgängen die Annahme eines Singlethread-E/A-Modells erzwungen wird. Weitere Informationen finden Sie unter [Leistung von Multithreadbibliotheken](../c-runtime-library/multithreaded-libraries-performance.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Globale Konstanten](../c-runtime-library/global-constants.md)