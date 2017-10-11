---
title: Compilerfehler C3023 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3023
dev_langs:
- C++
helpviewer_keywords:
- C3023
ms.assetid: 89dcce98-3cd7-4931-a50f-87df1d2ebc9b
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: be45b364bbc87b03fd6898b1cdee339a3cf9e8b6
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3023"></a>Compilerfehler C3023
"Wert": Im Argument für die "Klausel"-Klausel von OpenMP wurde ein unerwartetes Token gefunden.  
  
 Die an eine Klausel übergebenen Werte waren nicht gültig.  
  
 Im folgenden Beispiel wird C3023 generiert:  
  
```  
// C3023.cpp  
// compile with: /openmp /link vcomps.lib  
#include <stdio.h>  
#include "omp.h"  
  
int main() {  
   int i;  
  
   #pragma omp parallel for schedule(dynamic 10)   // C3023  
   for (i = 0; i < 10; ++i) ;  
  
   #pragma omp parallel for schedule(dynamic;10)   // C3023  
   for (i = 0; i < 10; ++i) ;  
  
   // OK  
   #pragma omp parallel for schedule(dynamic, 10)  
   for (i = 0; i < 10; ++i)  
   ;  
}  
```
