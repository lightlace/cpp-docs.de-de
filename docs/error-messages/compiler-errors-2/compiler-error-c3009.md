---
title: Compilerfehler C3009 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3009
dev_langs:
- C++
helpviewer_keywords:
- C3009
ms.assetid: aded5985-f5fd-4c3e-a157-16be55ec1313
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: e005fc24ee9b8325215709cf5728315cb7c7d9ff
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3009"></a>Compilerfehler C3009
'bezeichnung': Einsprung in strukturierten Block von OpenMP ist nicht zulässig.  
  
 Code kann nicht in einen oder aus einem OpenMP-Block springen.  
  
 Im folgenden Beispiel wird C3009 generiert:  
  
```  
// C3009.c  
// compile with: /openmp  
int main() {  
   #pragma omp parallel   
   {  
   lbl2:;  
   }  
   goto lbl2;   // C3009  
}  
```