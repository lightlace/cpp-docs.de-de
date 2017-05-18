---
title: Compilerwarnung (Stufe 4) C4456 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4456
dev_langs:
- C++
helpviewer_keywords:
- C4456
ms.assetid: 5ab39fc1-0e19-461b-842b-4da80560b044
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
ms.openlocfilehash: 8698c9a430a79bbec1f6e82b8ac58067317c59a1
ms.contentlocale: de-de
ms.lasthandoff: 05/10/2017

---
# <a name="compiler-warning-level-4-c4456"></a>Compilerwarnung (Stufe 4) C4456
  
> Deklaration von "*Bezeichner*" Blendet die frühere lokalen Deklaration
  
Die Deklaration von *Bezeichner* im lokalen Gültigkeitsbereich Blendet Sie aus der Deklaration der frühere lokalen Deklaration mit demselben Namen. Diese Warnung teilt Ihnen, die Verweise auf *Bezeichner* im lokalen Gültigkeitsbereich auf die lokal deklarierte-Version nicht der vorherigen lokalen, die möglicherweise nicht Ihre Absicht zu beheben. Um dieses Problem zu beheben, wird empfohlen, dass Sie lokale Variablennamen, die nicht in Konflikt stehen und anderen lokalen Namen geben.  
    
## <a name="example"></a>Beispiel
  
Im folgende Beispiel wird C4456 generiert, da die Schleife steuern Variable `int x` und die lokale Variable `double x` in `member_fn` denselben Namen haben. Um dieses Problem zu beheben, verwenden Sie unterschiedliche Namen für die lokalen Variablen.  
  
```cpp  
// C4456_hide.cpp
// compile with: cl /W4 /c C4456_hide.cpp

struct S {
    void member_fn(unsigned u) {
        double x = 0;
        for (int x = 0; x < 10; ++x) {  // C4456
            u += x; // uses local int x
        } 
        x += u; // uses local double x
    }
} s;
```  

