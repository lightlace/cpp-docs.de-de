---
title: OMP_DYNAMIC | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: OMP_DYNAMIC
dev_langs: C++
helpviewer_keywords: OMP_DYNAMIC OpenMP environment variable
ms.assetid: e306049d-b644-4b73-8b63-46c835bff98b
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b5c416919678cd7b0f80bd1299c7682fe159cd19
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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