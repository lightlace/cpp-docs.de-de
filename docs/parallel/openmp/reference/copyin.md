---
title: Copyin | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: copyin
dev_langs: C++
helpviewer_keywords: copyin OpenMP clause
ms.assetid: 369efa88-613c-4cb1-9e11-7b9ee08a4b25
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: af833219039a03e7e403f7e3cd10210057f3abfa
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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
 `copyin`gilt für die folgenden Direktiven:  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [Abschnitte](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Weitere Informationen finden Sie unter [2.7.2.7 Copyin](../../../parallel/openmp/2-7-2-7-copyin.md).  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [Threadprivate](../../../parallel/openmp/reference/threadprivate.md) ein Beispiel der Verwendung von `copyin`.  
  
## <a name="see-also"></a>Siehe auch  
 [Klauseln](../../../parallel/openmp/reference/openmp-clauses.md)