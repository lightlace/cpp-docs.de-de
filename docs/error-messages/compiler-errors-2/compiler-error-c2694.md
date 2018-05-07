---
title: Compiler-Fehler C2694 generiert | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2694
dev_langs:
- C++
helpviewer_keywords:
- C2694
ms.assetid: 8dc2cec2-67ae-4e16-8c0c-374425aca8bc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1578b6d7c55272c4b798d0222a1da37f5a749ecc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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