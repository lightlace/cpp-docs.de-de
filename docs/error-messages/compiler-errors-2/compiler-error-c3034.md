---
title: Compilerfehler C3034 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3034
dev_langs:
- C++
helpviewer_keywords:
- C3034
ms.assetid: 49db8bac-2720-4622-94e3-7988f1603fa3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 41918704bb00df2950079c80d2615e63fdfb4525
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33247011"
---
# <a name="compiler-error-c3034"></a>Compilerfehler C3034
Die OpenMP directive1-Direktive von kann nicht direkt in der directive1-Direktive geschachtelt werden.  
  
 Bestimmte Direktiven können nicht geschachtelt werden. Um diesen Fehler zu beheben, können Sie die Anweisungen der beiden Direktiven in den Block einer Direktive zusammenführen, oder Sie können aufeinander folgende Direktiven erstellen.  
  
 Im folgenden Beispiel wird C3034 generiert:  
  
```  
// C3034.cpp  
// compile with: /openmp /link vcomps.lib  
int main() {  
  
   #pragma omp single  
   {  
      #pragma omp single   // C3034   
      {  
      ;  
      }  
   }  
  
   // Two consecutive single clauses are OK.  
   #pragma omp single  
   {  
   }  
  
   #pragma omp single  
   {  
   }  
}  
```