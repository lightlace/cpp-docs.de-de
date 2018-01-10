---
title: Compilerfehler C3004 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3004
dev_langs: C++
helpviewer_keywords: C3004
ms.assetid: 819c2b57-8366-4ca7-9135-1f0c5e5b6bb6
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1e1e82f2128725b585e7ed266fd1e977e79196f8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3004"></a>Compilerfehler C3004
„clause“: Die Klausel ist für die directive-Direktive von OpenMP nicht gültig.  
  
 Eine OpenMP-Klausel wurde in einer Direktive verwendet, für die sie nicht aktiviert ist.  
  
 Im folgenden Beispiel wird C3004 generiert:  
  
```  
// C3004.c  
// compile with: /openmp  
int main()  
{  
   int x, y, z;  
  
   // Shared clause not allowed for 'single' directive.  
   #pragma omp single shared(x, y)   // C3004  
  
   x = y;  
}  
```