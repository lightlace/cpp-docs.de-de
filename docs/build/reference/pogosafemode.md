---
title: PogoSafeMode | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- PogoSafeMode
ms.assetid: 2daeeff7-44cb-417f-90eb-6b9edf658533
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5f40dad6feff9e49deeb495e8acbf2584dea3e41
ms.sourcegitcommit: 5cd2e3e51ecc8d9fc0d889555b4bfa193ba1d6a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2018
---
# <a name="pogosafemode"></a>PogoSafeMode
Geben Sie an, ob der schnelle oder abgesicherte Modus zur Anwendungsprofilerstellung verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
PogoSafeMode  
```  
  
## <a name="remarks"></a>Hinweise  
 Profilgesteuerte Optimierung (PGO) besitzt zwei mögliche Modi während der Profilerstellungsphase: den schnellen und den abgesicherten Modus. Wenn die profilerstellung im schnellen Modus stattfindet, verwendet der **INC** Anweisung, um Leistungsindikatoren zu erhöhen. Die **INC** -Anweisung ist schneller, jedoch nicht threadsicher. Wenn die profilerstellung im abgesicherten Modus stattfindet, verwendet der **SPERRE INC** Anweisung, um Leistungsindikatoren zu erhöhen. Die **SPERRE INC** -Anweisung besitzt die gleiche Funktionalität wie die **INC** -Anweisung und ist threadsicher, dabei jedoch langsamer als die **INC** Anweisung.  
  
 Standardmäßig wird PGO-Profilerstellung im schnellen Modus ausgeführt. `PogoSafeMode` ist nur erforderlich, wenn Sie den abgesicherten Modus verwenden möchten.  
  
 Um PGO-profilerstellung im abgesicherten Modus auszuführen, müssen Sie entweder die Umgebungsvariable verwenden `PogoSafeMode` oder den Linkerschalter **- PogoSafeMode**, je nachdem, auf dem System. Wenn Sie die Profilerstellung auf einem x64-Computer ausführen, müssen Sie den Linkerschalter verwenden. Wenn Sie die Profilerstellung auf einem x86-Computer ausführen, müssen Sie die Umgebungsvariable auf einen beliebigen Wert festlegen, bevor Sie den Optimierungsprozess starten.  
  
## <a name="example"></a>Beispiel  
  
```  
set PogoSafeMode=1  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Umgebungsvariablen für Profilgesteuerte Optimierungen](../../build/reference/environment-variables-for-profile-guided-optimizations.md)   
 [Profilgesteuerte Optimierungen](../../build/reference/profile-guided-optimizations.md)