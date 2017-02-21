---
title: "Compilerfehler C3020 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3020"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3020"
ms.assetid: f625c7a3-afaa-4bd8-9c1b-51891b832f36
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Compilerfehler C3020
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Variable': Die Indexvariable der for\-Schleife von OpenMP kann nicht innerhalb der Schleife geändert werden  
  
 Der Index \(Schleifenzähler\) innerhalb der `for`\-Schleife darf von einer OpenMP\-`for`\-Schleife nicht geändert werden.  
  
 Im folgenden Beispiel wird C3020 generiert:  
  
```  
// C3020.cpp  
// compile with: /openmp  
int main() {  
   int i = 0, n = 3;  
  
   #pragma omp parallel  
   {  
      #pragma omp for  
      for (i = 0; i < 10; i += n)  
         i *= 2;   // C3020  
         // try the following line instead  
         // n++;  
   }  
}  
```  
  
 Eine mit [lastprivate](../../parallel/openmp/reference/lastprivate.md) deklarierte Variable kann nicht als Index innerhalb einer parallelisierten Schleife verwendet werden.  
  
 Im folgenden Beispiel wird für das zweite lastprivate der Fehler C3020 ausgegeben, da dadurch eine Schreiboperation in idx\_a innerhalb der äußersten for\-Schleife ausgelöst wird.  Durch das erste lastprivate wird keine Fehlermeldung ausgegeben, da dadurch eine Schreiboperation in idx\_a außerhalb der äußersten for\-Schleife ausgelöst wird \(technisch gesehen ganz am Ende der letzten Iteration\).  Im folgenden Beispiel wird C3020 generiert.  
  
```  
// C3020b.cpp  
// compile with: /openmp /c  
float a[100][100];  
int idx_a, idx_b;  
void test(int first, int last)  
{  
   #pragma omp parallel for lastprivate(idx_a)  
   for (idx_a = first; idx_a <= last; ++idx_a) {  
      #pragma omp parallel for lastprivate(idx_a)   // C3020  
      for (idx_b = first; idx_b <= last; ++idx_b) {  
         a[idx_a][idx_b] += 1.0f;  
      }  
   }  
}  
```  
  
 Das folgende Beispiel veranschaulicht eine mögliche Auflösung:  
  
```  
// C3020c.cpp  
// compile with: /openmp /c  
float a[100][100];  
int idx_a, idx_b;  
void test(int first, int last)  
{  
   #pragma omp parallel for lastprivate(idx_a)  
   for (idx_a = first; idx_a <= last; ++idx_a) {  
      #pragma omp parallel for lastprivate(idx_b)  
      for (idx_b = first; idx_b <= last; ++idx_b) {  
         a[idx_a][idx_b] += 1.0f;  
      }  
   }  
}  
```