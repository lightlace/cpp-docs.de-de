---
title: Compilerfehler C2891 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2891
dev_langs: C++
helpviewer_keywords: C2891
ms.assetid: e12cfb2d-df45-4b0d-b155-c51d17e812fa
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 979d77ad5b5bd0b68dd539695d6cb1b60b099c55
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2891"></a>Compilerfehler C2891
'Parameter': die Adresse eines Vorlagenparameters nicht übernehmen  
  
 Die Adresse eines Vorlagenparameters nicht akzeptiert werden, es sei denn, es sich um ein Lvalue ist. Typparameter sind nicht Lvalues, da sie keine Adresse besitzen. Nichttyp-Werte in Vorlagenparameterlisten, die nicht Lvalues sind auch eine Adresse keine. Dies ist ein Beispiel für Code, der bewirkt, Compilerfehler C2891 dass, weil der Wert mit dem Vorlagenparameter übergeben eine vom Compiler generierte Kopie das Vorlagenargument.  
  
```  
template <int i> int* f() { return &i; }  
```  
  
 Vorlagenparameter, die Lvalues, z. B. Verweistypen sind, kann ihre Adresse übernommen werden.  
  
```  
template <int& r> int* f() { return &r; }  
```  
  
 Um diesen Fehler zu beheben, führen Sie nicht die Adresse eines Vorlagenparameters, wenn es sich um ein Lvalue ist.