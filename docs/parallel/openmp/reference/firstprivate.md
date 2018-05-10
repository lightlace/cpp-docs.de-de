---
title: Firstprivate | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- firstprivate
dev_langs:
- C++
helpviewer_keywords:
- firstprivate OpenMP clause
ms.assetid: db479766-6d3b-4bbd-b28e-b192d826788c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 10b5a270feb638a98c060b58e90af8146ff97325
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="firstprivate"></a>firstprivate
Gibt an, dass jeder Thread eine eigene Instanz einer Variablen zugewiesen werden soll, und die Variable mit dem Wert der Variablen, initialisiert werden soll, da sie bevor Sie das parallele Konstrukt vorhanden ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
firstprivate(var)  
```  
  
#### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`var`|Die Variable, Instanzen in jeder Thread und wird mit dem Wert der Variablen, initialisiert werden, da es vorhanden, bevor das parallele Konstrukt ist. Wenn mehr als eine Variable angegeben wird, trennen Sie Namen durch ein Komma.|  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="remarks"></a>Hinweise  
 `firstprivate` gilt für die folgenden Direktiven:  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [Abschnitte](../../../parallel/openmp/reference/sections-openmp.md)  
  
-   [single](../../../parallel/openmp/reference/single.md)  
  
 Weitere Informationen finden Sie unter [2.7.2.2 Firstprivate](../../../parallel/openmp/2-7-2-2-firstprivate.md).  
  
## <a name="example"></a>Beispiel  
 Ein Beispiel der Verwendung von `firstprivate`, siehe das Beispiel in [private](../../../parallel/openmp/reference/private-openmp.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Klauseln](../../../parallel/openmp/reference/openmp-clauses.md)