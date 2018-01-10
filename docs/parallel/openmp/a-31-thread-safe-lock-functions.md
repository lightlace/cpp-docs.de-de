---
title: A.31 Thread-sichere Sperre Funktionen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 3ad89eb8-076c-405a-be5e-88d3d707a832
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 34a1d9b2a923af68bb63fb29a7031a7efa433a26
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="a31---thread-safe-lock-functions"></a>A.31   Threadsichere Lock-Funktionen
Im folgende C++-Beispiel veranschaulicht, wie ein Array von Sperren in einem parallelen Bereich initialisiert werden, mithilfe von `omp_init_lock` ([Abschnitt 3.2.1](../../parallel/openmp/3-2-1-omp-init-lock-and-omp-init-nest-lock-functions.md) auf Seite "42").  
  
## <a name="example"></a>Beispiel  
  
### <a name="code"></a>Code  
  
```  
// A_13_omp_init_lock.cpp  
// compile with: /openmp  
#include <omp.h>  
  
omp_lock_t *new_locks() {  
   int i;  
   omp_lock_t *lock = new omp_lock_t[1000];  
   #pragma omp parallel for private(i)  
   for (i = 0 ; i < 1000 ; i++)  
      omp_init_lock(&lock[i]);  
  
   return lock;  
}  
  
int main () {}  
```