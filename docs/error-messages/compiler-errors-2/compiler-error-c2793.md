---
title: Compilerfehler Fehler C2793 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2793
dev_langs:
- C++
helpviewer_keywords:
- C2793
ms.assetid: ce35f4e8-c357-40ca-95c4-15ff001ad69d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ea378b2a875542eab431cf9cc30217f50c971af6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2793"></a>Compilerfehler Fehler C2793
"token": Unerwartetes token Folgendes "::", Bezeichner oder ein Schlüsselwort "Operator" erwartet  
  
 Die einzigen Token, die folgen können `__super::` sind ein Bezeichner oder das Schlüsselwort `operator`.  
  
 Im folgende Beispiel wird C2793 generiert:  
  
```  
// C2793.cpp  
struct B {  
   void mf();  
};  
  
struct D : B {  
   void mf() {  
      __super::(); // C2793  
   }  
};  
```