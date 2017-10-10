---
title: Compilerfehler Fehler C3120 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3120
dev_langs:
- C++
helpviewer_keywords:
- C3120
ms.assetid: 9b6b210f-9948-4517-a4cc-b4aaadebde68
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 6bdd5f5fe41fa794b536f71b3f88db01de99c646
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3120"></a>Compilerfehler Fehler C3120
"keine Variablenargumentlisten verwenden": Schnittstellenmethoden keine Liste variabler Argumente akzeptiert  
  
 Eine Schnittstellenmethode akzeptiert keine Liste variabler Argumente. Die folgende Schnittstellendefinition wird z. B. C3120 generiert:  
  
```  
// C3120.cpp  
__interface A {  
int X(int i, ...);    // C3120  
};  
  
int main(void) { return(0); }  
```
