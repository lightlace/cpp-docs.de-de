---
title: OMP_SCHEDULE | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- OMP_SCHEDULE
dev_langs:
- C++
helpviewer_keywords:
- OMP_SCHEDULE OpenMP environment variable
ms.assetid: 2295a801-e584-4d2f-826f-7ca4c88846a6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fd5bf96706b94ffbba8cb1b9aeeee8701b266e5d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46115039"
---
# <a name="ompschedule"></a>OMP_SCHEDULE
Ändert das Verhalten von der [Zeitplan](../../../parallel/openmp/reference/schedule.md) Klausel bei `schedule(runtime)` angegeben ist, eine `for` oder `parallel for` Richtlinie.  
  
## <a name="syntax"></a>Syntax  
  
```  
set OMP_SCHEDULE[=type[,size]]  
```  
  
## <a name="arguments"></a>Argumente

*size*<br/>
(Optional) Gibt die Größe der Iterationen. `size` Eine positive ganze Zahl muss sein. Der Standardwert ist 1, außer wenn `type` ist statisch. Nicht gültig, wenn `type` ist `runtime`.  
  
*Typ*<br/>
Die Art der Planung:  
  
-   `dynamic`  
  
-   `guided`  
  
-   `runtime`  
  
-   `static`  
  
## <a name="remarks"></a>Hinweise  
 Der Standardwert in der Visual C++-Implementierung des OpenMP-Standards ist `OMP_SCHEDULE=static,0`.  
  
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