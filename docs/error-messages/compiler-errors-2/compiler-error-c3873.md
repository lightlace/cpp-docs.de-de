---
title: Compilerfehler C3873 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3873
helpviewer_keywords:
- C3873
ms.assetid: e68fd3be-2391-492b-ac3f-d2428901b2e9
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: b2e95250fd2bf789425585b704f50bd4d1c51b2c
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3873"></a>Compilerfehler C3873
„char“: Dieses Zeichen ist nicht als erstes Zeichen eines Bezeichners zulässig.  
  
 Der C++-Compiler folgt hinsichtlich Zeichen, die in einem Bezeichner zulässig sind, dem C++11-Standard. Nur bestimmte Bereiche von Zeichen und universelle Zeichennamen sind in einem Bezeichner zulässig. Zusätzliche Einschränkungen gelten für das erste Zeichen eines Bezeichners. Weitere Informationen hierzu und eine Liste der zulässigen Zeichen sowie Bereiche universeller Zeichennamen finden Sie unter [Identifiers](../../cpp/identifiers-cpp.md).  
  
 Der Bereich der in einem Bezeichner zulässigen Zeichen ist weniger restriktiv, wenn C++ /CLI-Code kompiliert wird. Bezeichner in Code, der mit „/clr“ kompiliert wurde, müssen dem folgenden Standard entsprechen:  [Standard ECMA-335: Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).  
  
 Im folgenden Beispiel wird C3873 generiert:  
  
```  
// C3873.cpp  
int main() {  
   int \u036F_abc;   // C3873, not in allowed range for initial character  
   int abc_\u036F;   // OK, in allowed range for non-initial character  
}  
```
