---
title: Compilerwarnung (Stufe 4) C4457 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4457
dev_langs: C++
helpviewer_keywords: C4457
ms.assetid: 02fd149a-917d-4f67-97a6-eb714572271f
caps.latest.revision: "0"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 77965ba08b311768b54788692d3f5b7fa724f5b8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
