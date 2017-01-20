---
title: "Compilerfehler C3019"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C3019"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3019"
ms.assetid: 31a6d9b6-d29f-4499-9ad8-48dd751e87c7
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3019
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Inkrementierung in OpenMP\-'for'\-Anweisung weist ein falsches Format auf  
  
 Der Inkrementierungsabschnitt einer OpenMP\-`for`\-Schleife muss die Indexvariable sowohl links als auch rechts vom Operator verwenden.  
  
 Im folgenden Beispiel wird C3019 generiert:  
  
```  
// C3019.cpp  
// compile with: /openmp  
int main()  
{  
   int i = 0, j = 1, n = 3;  
  
   #pragma omp parallel  
   {  
      #pragma omp for  
      for (i = 0; i < 10; i = j + n)   // C3019  
      // Try the following line instead:  
      // for (i = 0; i < 10; i++)  
         j *= 2;  
   }  
}  
```