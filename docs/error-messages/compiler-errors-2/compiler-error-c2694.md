---
title: Compiler-Fehler C2694 generiert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2694
dev_langs:
- C++
helpviewer_keywords:
- C2694
ms.assetid: 8dc2cec2-67ae-4e16-8c0c-374425aca8bc
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: b81a6ee838a1d30928e8cebb8ef581c23644afcf
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2694"></a>Compiler-Fehler C2694 generiert
"override": Überschreiben der virtuellen Funktion hat eine weniger restriktive Ausnahmespezifikation als Basisklasse virtuellen Member-Funktion "Base"  
  
 Eine virtuelle Funktion überschrieben wurde, jedoch unter ["/ Za"](../../build/reference/za-ze-disable-language-extensions.md)der überschreibenden Funktion hat eine weniger restriktive [Ausnahmespezifikation](../../cpp/exception-specifications-throw-cpp.md).  
  
 Im folgende Beispiel wird C2694 generiert:  
  
```  
// C2694.cpp  
// compile with: /Za /c  
class MyBase {  
public:  
   virtual void f(void) throw(int) {  
   }  
};  
  
class Derived : public MyBase {  
public:  
   void f(void) throw(...) {}   // C2694  
   void f2(void) throw(int) {}   // OK  
};  
```
