---
title: Compilerfehler C3001 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3001
dev_langs: C++
helpviewer_keywords: C3001
ms.assetid: d0e03478-1b44-47e5-8f5b-70415fa1f8bc
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: bd853b18d53684237481791002d6089b1b664cfb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3001"></a>Compilerfehler C3001
"Fehler_Text": Es wurde ein OpenMP-Direktivenname erwartet.  
  
 #pragma `omp` muss eine Direktive folgen.  
  
 Im folgenden Beispiel wird C3001 generiert:  
  
```  
// C3001.c  
// compile with: /openmp  
int main()  
{  
   #pragma omp   // C3001 missing token  
}  
```