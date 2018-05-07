---
title: Compilerwarnung (Stufe 4) C4457 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4457
dev_langs:
- C++
helpviewer_keywords:
- C4457
ms.assetid: 02fd149a-917d-4f67-97a6-eb714572271f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 80eac0ade54df1626e993bfed12468b2aa34402f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4457"></a>Compilerwarnung (Stufe 4) C4457
  
> Deklaration von "*Bezeichner*" Blendet Parameter-Funktion
  
Die Deklaration von *Bezeichner* im lokalen Gültigkeitsbereich Blendet Sie aus der Deklaration des Parameters der Funktion mit identischem Namen. Diese Warnung teilt Ihnen, die Verweise auf *Bezeichner* im lokalen Gültigkeitsbereich auf die lokal deklarierte Version, die nicht den Parameter, der nicht unbedingt Ihre Absicht zu beheben. Um dieses Problem zu beheben, wird empfohlen, dass Sie lokale Variablennamen, die keinen Konflikt mit dem Parameternamen erteilen.  
    
## <a name="example"></a>Beispiel
  
Im folgende Beispiel wird C4457 generiert, da der Parameter `x` und die lokale Variable `x` in `member_fn` denselben Namen haben. Um dieses Problem zu beheben, verwenden Sie unterschiedliche Namen für die Parameter und lokaler Variablen.  
  
```cpp  
// C4457_hide.cpp
// compile with: cl /W4 /c C4457_hide.cpp

struct S {
    void member_fn(unsigned x) {
        double a = 0;
        for (int x = 0; x < 10; ++x) {  // C4457
            a += x; // uses local x
        } 
        a += x; // uses parameter x
    }
} s;
```  
