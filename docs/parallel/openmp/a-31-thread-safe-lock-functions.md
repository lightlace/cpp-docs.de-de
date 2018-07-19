---
title: A.31 Thread-sichere Sperre Funktionen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 3ad89eb8-076c-405a-be5e-88d3d707a832
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: efac1091b2245b9368451e8b5148bbfe478410f4
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33690441"
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