---
title: Compilerwarnung (Stufe 2) C4285 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4285
dev_langs:
- C++
helpviewer_keywords:
- C4285
ms.assetid: fa14de1f-fc19-4eec-8bea-81003636e12f
caps.latest.revision: 6
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: ab81b59a711aa5ed623e2976c3d5eabfea58a5e3
ms.contentlocale: de-de
ms.lasthandoff: 04/01/2017

---
# <a name="compiler-warning-level-2-c4285"></a>Compilerwarnung (Stufe 2) C4285
Rückgabetyp für '-> Identifier:: Operator' ist rekursiv, wenn mit Infix-Notation verwendet  
  
 Das angegebene **operator->()** Funktion kann nicht der Rückgabetyp für die er definiert ist oder ein Verweis auf den Typ für die es definiert ist.  
  
 Im folgenden Beispiel wird C4285 generiert:  
  
```  
// C4285.cpp  
// compile with: /W2  
class C  
{  
public:  
    C operator->();   // C4285  
   // C& operator->();  C4285, also  
};  
  
int main()  
{  
}  
```
