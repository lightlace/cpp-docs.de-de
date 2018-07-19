---
title: Copyin | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- copyin
dev_langs:
- C++
helpviewer_keywords:
- copyin OpenMP clause
ms.assetid: 369efa88-613c-4cb1-9e11-7b9ee08a4b25
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 32137534a43eeb0b038eae547f9bc19283412159
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33688244"
---
# <a name="copyin"></a>copyin
Können Threads für die master-Thread-Wert, den Zugriff auf eine [Threadprivate](../../../parallel/openmp/reference/threadprivate.md) Variable.  
  
## <a name="syntax"></a>Syntax  
  
```  
copyin(var)  
```  
  
## <a name="remarks"></a>Hinweise  
 wobei  
  
 `var`  
 Die `threadprivate` Variable, die mit dem Wert der Variablen in der master-Thread initialisiert wird, wie sie bevor Sie das parallele Konstrukt vorhanden ist.  
  
## <a name="remarks"></a>Hinweise  
 `copyin` gilt für die folgenden Direktiven:  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [Abschnitte](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Weitere Informationen finden Sie unter [2.7.2.7 Copyin](../../../parallel/openmp/2-7-2-7-copyin.md).  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [Threadprivate](../../../parallel/openmp/reference/threadprivate.md) ein Beispiel der Verwendung von `copyin`.  
  
## <a name="see-also"></a>Siehe auch  
 [Klauseln](../../../parallel/openmp/reference/openmp-clauses.md)