---
title: Compilerfehler C3894 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3894
dev_langs:
- C++
helpviewer_keywords:
- C3894
ms.assetid: 6d5ac903-1dea-431d-8e3a-cebca4342983
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 46dffabb57e871e1635738434e7efb4812850379
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3894"></a>Compilerfehler C3894
'Var': Verwendung statischer Datenmember Initonly l-Wert ist nur zulässig, in den Konstruktor der Klasse der Klasse "Klasse"  
  
 Statische [Initonly](../../dotnet/initonly-cpp-cli.md) Datenmember können nur als l-Werte zum Zeitpunkt der Deklaration oder in einem statischen Konstruktor verwendet werden.  
  
 Instanz (nicht statische) Initonly-Datenmember können nur als l-Werte zum Zeitpunkt der Deklaration oder in der Instanz (nicht statische) Konstruktoren verwendet werden.  
  
 Im folgende Beispiel wird C3894 generiert:  
  
```  
// C3894.cpp  
// compile with: /clr  
ref struct Y1 {  
   initonly static int data_var = 0;  
  
public:  
   // class constructor  
   static Y1() {  
      data_var = 99;   // OK  
      System::Console::WriteLine("in static constructor");  
   }  
  
   // not the class constructor  
   Y1(int i) {  
      data_var = i;   // C3894  
   }  
  
   static void Test() {}  
  
};  
  
int main() {  
   Y1::data_var = 88;   // C3894  
   int i = Y1::data_var;  
   Y1 ^ MyY1 = gcnew Y1(99);  
   Y1::Test();  
}  
```
