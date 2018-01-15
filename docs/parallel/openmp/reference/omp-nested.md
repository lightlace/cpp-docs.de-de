---
title: OMP_NESTED | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: OMP_NESTED
dev_langs: C++
helpviewer_keywords: OMP_NESTED OpenMP environment variable
ms.assetid: c43f5287-a548-40d0-bd54-0c6b2b9f9a53
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d90d43727227593cccbd3d885f71f5cabaf10429
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ompnested"></a>OMP_NESTED
Gibt an, ob geschachtelte Parallelität aktiviert ist, es sei denn, geschachtelte Parallelität aktiviert oder deaktiviert ist, `omp_set_nested`.  
  
## <a name="syntax"></a>Syntax  
  
```  
set OMP_NESTED[=TRUE | =FALSE]  
```  
  
## <a name="remarks"></a>Hinweise  
 Die `OMP_NESTED` -Umgebungsvariable kann überschrieben werden, indem die [Omp_set_nested](../../../parallel/openmp/reference/omp-set-nested.md) Funktion.  
  
 Der Standardwert in der Visual C++-Implementierung der OpenMP-Standard ist `OMP_DYNAMIC=FALSE`.  
  
 Weitere Informationen finden Sie unter [4.4 OMP_NESTED](../../../parallel/openmp/4-4-omp-nested.md).  
  
## <a name="example"></a>Beispiel  
 Der folgende Befehl legt die `OMP_NESTED` -Umgebungsvariable auf "true":  
  
```  
set OMP_NESTED=TRUE  
```  
  
 Der folgende Befehl zeigt die aktuelle Einstellung der `OMP_NESTED` -Umgebungsvariablen angegeben:  
  
```  
set OMP_NESTED  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Umgebungsvariablen](../../../parallel/openmp/reference/openmp-environment-variables.md)