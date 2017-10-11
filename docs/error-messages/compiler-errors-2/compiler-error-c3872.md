---
title: Compilerfehler C3872 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3872
dev_langs:
- C++
helpviewer_keywords:
- C3872
ms.assetid: 519e95be-5641-40cc-894c-da4819506604
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: e42ebb3e1fc286e40662eb7fcce83893b1e4007f
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3872"></a>Compilerfehler C3872
„char“: Dieses Zeichen ist in einem Bezeichner nicht zulässig.  
  
 Der C++-Compiler folgt hinsichtlich Zeichen, die in einem Bezeichner zulässig sind, dem C++11-Standard. Nur bestimmte Bereiche von Zeichen und universelle Zeichennamen sind in einem Bezeichner zulässig. Zusätzliche Einschränkungen gelten für das erste Zeichen eines Bezeichners. Weitere Informationen hierzu und eine Liste der zulässigen Zeichen sowie Bereiche universeller Zeichennamen finden Sie unter [Identifiers](../../cpp/identifiers-cpp.md).  
  
 Der Bereich der in einem Bezeichner zulässigen Zeichen ist weniger restriktiv, wenn C++ /CLI-Code kompiliert wird. Bezeichner in Code, der mit „/clr“ kompiliert wurde, müssen dem folgenden Standard entsprechen:  [Standard ECMA-335: Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).  
  
 Im folgenden Beispiel wird C3872 generiert:  
  
```  
// C3872.cpp  
int main() {  
   int abc_\u0040;   // C3872, U+0040 is in base char set  
   int abc_\u3001;   // C3872, U+3001 is not in allowed range  
   int \u30A2_abc_\u3042;   // OK, UCNs in allowed range  
}  
```
