---
title: Compilerfehler C2991 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2991
dev_langs:
- C++
helpviewer_keywords:
- C2991
ms.assetid: a87e4404-26e8-4927-b3ee-5d02b3b8bee1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8b1605c7b12a08b0fdb3701a94b2b5cf2e649c98
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2991"></a>Compilerfehler C2991
Neudefinition des Typparameters „parameter“  
  
 Es ist ein Typenkonflikt zwischen zwei generischen oder Vorlagendefinitionen von `parameter`aufgetreten. Wenn Sie mehrere generische oder Vorlagenparameter definieren, müssen Sie äquivalente Typen verwenden.  
  
 Im folgenden Beispiel wird C2991 generiert:  
  
```  
// C2991.cpp  
// compile with: /c  
template<class T, class T> struct TC {};   // C2991  
// try the following line instead  
// template<class T, class T2> struct TC {};  
```  
  
 C2991 kann auch auftreten, wenn Generika verwendet werden:  
  
```  
// C2991b.cpp  
// compile with: /clr /c  
generic<class T,class T> ref struct GC {};   // C2991  
// try the following line instead  
// generic<class T,class T2> ref struct GC {};  
```