---
title: Compiler-Fehler C2681 generiert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2681
dev_langs:
- C++
helpviewer_keywords:
- C2681
ms.assetid: eb42da6d-8d2c-43fd-986b-e73e2b004885
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 9978a520b4682e4e2c7c4856d4e42675be0ab901
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2681"></a>Compiler-Fehler C2681 generiert
'Typ': Ungültiger Ausdruckstyp für Namen  
  
 Ein Typumwandlungsoperator wurde versucht, einen ungültigen Typ zu konvertieren. Angenommen, Sie verwenden die [Dynamic_cast](../../cpp/dynamic-cast-operator.md) -Operator konvertiert einen Ausdruck in einen Zeigertyp, der Quellausdruck muss ein Zeiger sein.  
  
 Im folgende Beispiel wird C2681 generiert:  
  
```  
// C2681.cpp  
class A { virtual void f(); };  
  
void g(int i) {  
    A* pa;  
    pa = dynamic_cast<A*>(i);  // C2681  
}  
```
