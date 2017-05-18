---
title: Compilerwarnung (Stufe 4) C4458 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4458
dev_langs:
- C++
helpviewer_keywords:
- C4458
ms.assetid: 7bdaa1b1-0caf-4d68-98c4-6bdd441c23fb
caps.latest.revision: 0
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 128bd124c2536d86c8b673b54abc4b5505526b41
ms.openlocfilehash: 07b8db673b2db27f456f0e7228695c83497d1278
ms.contentlocale: de-de
ms.lasthandoff: 05/10/2017

---
# <a name="compiler-warning-level-4-c4458"></a>Compilerwarnung (Stufe 4) C4458
  
> Deklaration von "*Bezeichner*" Blendet den Klassenmember
  
Die Deklaration von *Bezeichner* im lokalen Gültigkeitsbereich Blendet Sie aus der Deklaration der identisch benannt *Bezeichner* im Gültigkeitsbereich einer Klasse. Diese Warnung teilt Ihnen, die Verweise auf *Bezeichner* in diesem Bereich auf die lokal deklarierte-Version nicht der Klasse Member Version, die nicht unbedingt Ihren Zweck zu beheben. Um dieses Problem zu beheben, wird empfohlen, dass Sie lokale Variablennamen, die nicht in Konflikt stehen mit Elementnamen Klasse geben.  
    
## <a name="example"></a>Beispiel
  
Im folgende Beispiel wird C4458 generiert, da der Parameter `x` und die lokale Variable `y` in `member_fn` haben die gleichen Namen als Datenmember in der Klasse. Um dieses Problem zu beheben, verwenden Sie unterschiedliche Namen für die Parameter und lokaler Variablen.  
  
```cpp  
// C4458_hide.cpp
// compile with: cl /W4 /c C4458_hide.cpp

struct S {
    int x;
    float y;
    void member_fn(long x) {   // C4458
        double y;  // C4458
        y = x;  
        // To fix this issue, change the parameter name x
        // and local name y to something that does not 
        // conflict with the data member names.
    }
} s;
```  

