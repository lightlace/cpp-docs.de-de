---
title: Compilerwarnung (Stufe 4) C4456 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4456
dev_langs: C++
helpviewer_keywords: C4456
ms.assetid: 5ab39fc1-0e19-461b-842b-4da80560b044
caps.latest.revision: "0"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9e298f092f546c589606be42b6e7b9faed15ddd4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
