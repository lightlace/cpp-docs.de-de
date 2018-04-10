---
title: Compiler-Fehler C2784 generiert | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
f1_keywords:
- C2784
dev_langs:
- C++
helpviewer_keywords:
- C2784
ms.assetid: 3d761fe2-881c-48bd-afae-e2e714e20473
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7436f86da574763f3f19e7cc5eb44a9921471739
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2784"></a>Compiler-Fehler C2784 generiert
'declaration' : Vorlagenargument für 'type' aus 'type' konnte nicht hergeleitet werden  
  
 Der Compiler aus den bereitgestellten Funktionsargumenten kein Vorlagenargument ermitteln.  
  
 Im folgenden Beispiel wird C2784 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C2784.cpp  
template<class T> class X {};  
template<class T> void f(X<T>) {}  
  
int main() {  
   X<int> x;  
   f(1);   // C2784  
  
   // To fix it, try the following line instead  
   f(x);  
}  
```