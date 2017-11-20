---
title: Compilerfehler C3021 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3021
dev_langs: C++
helpviewer_keywords: C3021
ms.assetid: 0cef6d97-e267-438a-ac8b-0daf5bbbc2cf
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2dd19610cdb548fa3b9a81181fa8857d8c8e8644
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3021"></a>Compilerfehler C3021
"arg": Das Argument der "directive"-Direktive von OpenMP ist leer  
  
 Ein Argument ist für eine Direktive von OpenMP erforderlich.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3021 generiert:  
  
```  
// C3021.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include "omp.h"  
  
int g = 0;  
  
int main()  
{  
    int x, y, i;  
  
    #pragma omp parallel for schedule(static,)   // C3021  
    for (i = 0; i < 10; ++i) ;  
  
    #pragma omp parallel for schedule()   // C3021  
    for (i = 0; i < 10; ++i)  
        printf_s("Hello world, thread %d, iteration %d\n",  
                 omp_get_thread_num(), i);  
  
    #pragma omp parallel reduction()   // C3021  
      ;  
  
    #pragma omp parallel reduction(+ :)   // C3021  
      ;  
  
    //   
    // The following shows correct syntax examples.  
    //  
    #pragma omp parallel reduction(+ : x, y)  
      ;  
  
    #pragma omp parallel reduction(* : x, y)  
      ;  
  
    #pragma omp parallel reduction(- : x, y)  
      ;  
  
    #pragma omp parallel reduction(& : x, y)  
      ;  
  
    #pragma omp parallel reduction(^ : x, y)  
      ;  
  
    #pragma omp parallel reduction(| : x, y)  
      ;  
  
    #pragma omp parallel reduction(&& : x, y)  
      ;  
  
    #pragma omp parallel reduction(|| : x, y)  
      ;  
}  
```