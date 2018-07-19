---
title: Compilerfehler C2891 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2891
dev_langs:
- C++
helpviewer_keywords:
- C2891
ms.assetid: e12cfb2d-df45-4b0d-b155-c51d17e812fa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 01741d1cc67f0045c46ab392212625b9e1a2d8ca
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33246369"
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