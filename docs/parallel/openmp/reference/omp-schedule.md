---
title: OMP_SCHEDULE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- OMP_SCHEDULE
dev_langs:
- C++
helpviewer_keywords:
- OMP_SCHEDULE OpenMP environment variable
ms.assetid: 2295a801-e584-4d2f-826f-7ca4c88846a6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8ff09bf142fd1c8bbbd61d1e1d3bd76102f7d86b
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="ompschedule"></a>OMP_SCHEDULE
Verändert das Sitzungsverhalten, sodass die [Zeitplan](../../../parallel/openmp/reference/schedule.md) Klausel bei `schedule(runtime)` angegeben ist, eine `for` oder `parallel for` Richtlinie.  
  
## <a name="syntax"></a>Syntax  
  
```  
set OMP_SCHEDULE[=type[,size]]  
```  
  
## <a name="remarks"></a>Hinweise  
 wobei  
  
 `size` (optional)  
 Gibt die Größe der Iterationen. `size` Eine positive ganze Zahl muss sein. Der Standard ist 1, außer wenn `type` ist statisch. Nicht gültig, wenn `type` ist `runtime`.  
  
 `type`  
 Die Art der Planung:  
  
-   `dynamic`  
  
-   `guided`  
  
-   `runtime`  
  
-   `static`  
  
## <a name="remarks"></a>Hinweise  
 Der Standardwert in der Visual C++-Implementierung der OpenMP-Standard ist `OMP_SCHEDULE=static,0`.  
  
 Weitere Informationen finden Sie unter [4.1 OMP_SCHEDULE](../../../parallel/openmp/4-1-omp-schedule.md).  
  
## <a name="example"></a>Beispiel  
 Der folgende Befehl legt die **OMP_SCHEDULE** -Umgebungsvariablen angegeben:  
  
```  
set OMP_SCHEDULE="guided,2"  
```  
  
 Der folgende Befehl zeigt die aktuelle Einstellung der **OMP_SCHEDULE** -Umgebungsvariablen angegeben:  
  
```  
set OMP_SCHEDULE  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Umgebungsvariablen](../../../parallel/openmp/reference/openmp-environment-variables.md)