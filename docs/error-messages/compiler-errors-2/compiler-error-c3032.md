---
title: Compilerfehler C3032 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3032
dev_langs: C++
helpviewer_keywords: C3032
ms.assetid: 6a92bd8e-319f-4a99-aef4-a9021f6f9928
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2bc15f7f1989a7cec11506a445b985fa6e863ba2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3032"></a>Compilerfehler C3032
"var": Die Variable in der Klausel-Klausel kann keinen unvollständigen Typ "Typ" aufweisen.  
  
 Typen, die an bestimmte Klauseln übergeben werden, müssen für den Compiler vollständig sichtbar sein.  
  
 Im folgenden Beispiel wird C3032 generiert:  
  
```  
// C3032.cpp  
// compile with: /openmp /link vcomps.lib  
#include "omp.h"  
  
struct Incomplete;  
extern struct Incomplete inc;  
  
int main() {  
   int i = 9;  
   #pragma omp parallel private(inc)   // C3032  
      ;  
  
   #pragma omp parallel private(i)     // OK  
      ;  
  
}  
```