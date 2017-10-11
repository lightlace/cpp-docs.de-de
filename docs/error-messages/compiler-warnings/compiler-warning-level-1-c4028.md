---
title: Compilerwarnung (Stufe 1) C4028 generiert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4028
dev_langs:
- C++
helpviewer_keywords:
- C4028
ms.assetid: c3e8b70b-e870-416c-a285-bba5f71dbfc6
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 0041d795ed5afce50592f21f41986d3f32c71fe3
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-warning-level-1-c4028"></a>Compilerwarnung (Stufe 1) C4028 generiert
formale Parameter 'Nummer' Deklaration unterscheiden  
  
 Der Typ des formalen Parameters stimmt nicht mit dem entsprechenden Parameter in der Deklaration überein. Der Typ in der ursprünglichen Deklaration wird verwendet.  
  
 Diese Warnung gilt nur für C#-Quellcode.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C4028 generiert.  
  
```  
// C4028.c  
// compile with: /W1 /Za  
void f(int , ...);  
void f(int i, int j) {}   // C4028  
  
void g(int , int);  
void g(int i, int j) {}   // OK  
  
int main() {}  
```
