---
title: Compilerfehler C3033 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3033
dev_langs: C++
helpviewer_keywords: C3033
ms.assetid: 8628b6bb-a650-4ed2-af13-57acd2f7ddbb
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c005874c7a11f5ec250daa42f8857070bbfad8dc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3033"></a>Compilerfehler C3033
"Var": Die Variable in der Klausel-Klausel kann keinen konstant qualifizierten Typ aufweisen.  
  
 Werte, die an bestimmte Klauseln übergeben werden, dürfen keine `const` -Variablen sein.  
  
 Im folgenden Beispiel wird C3033 generiert:  
  
```  
// C3033.cpp  
// compile with: /openmp /link vcomps.lib  
int main() {  
   const int val = 1;  
   int val2 = 1;  
  
   #pragma omp parallel reduction(+ : val)   // C3033  
   ;  
  
   #pragma omp parallel reduction(+ : val2)   // OK  
   ;  
}  
```