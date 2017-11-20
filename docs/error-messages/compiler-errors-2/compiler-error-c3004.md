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
ms.openlocfilehash: 6468ecdf001789a487658d80d50bc843e2df8e96
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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