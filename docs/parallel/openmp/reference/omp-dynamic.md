---
title: OMP_DYNAMIC | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- OMP_DYNAMIC
dev_langs:
- C++
helpviewer_keywords:
- OMP_DYNAMIC OpenMP environment variable
ms.assetid: e306049d-b644-4b73-8b63-46c835bff98b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: de4a81d861bf72943a67356577da37c36df63f69
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33695810"
---
# <a name="ompdynamic"></a>OMP_DYNAMIC
Gibt an, ob die OpenMP zur Laufzeit die Anzahl der Threads in einem parallelen Bereich anpassen kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
set OMP_DYNAMIC[=TRUE | =FALSE]  
```  
  
## <a name="remarks"></a>Hinweise  
 Die `OMP_DYNAMIC` -Umgebungsvariable kann überschrieben werden, indem die [Omp_set_dynamic](../../../parallel/openmp/reference/omp-set-dynamic.md) Funktion.  
  
 Der Standardwert in der Visual C++-Implementierung der OpenMP-Standard ist `OMP_DYNAMIC=FALSE`.  
  
 Weitere Informationen finden Sie unter [4.3 OMP_DYNAMIC](../../../parallel/openmp/4-3-omp-dynamic.md).  
  
## <a name="example"></a>Beispiel  
 Der folgende Befehl legt die `OMP_DYNAMIC` -Umgebungsvariable auf "true":  
  
```  
set OMP_DYNAMIC=TRUE  
```  
  
 Der folgende Befehl zeigt die aktuelle Einstellung der `OMP_DYNAMIC` -Umgebungsvariablen angegeben:  
  
```  
set OMP_DYNAMIC  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Umgebungsvariablen](../../../parallel/openmp/reference/openmp-environment-variables.md)