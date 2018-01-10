---
title: Compilerfehler C3145 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3145
dev_langs: C++
helpviewer_keywords: C3145
ms.assetid: f165c874-0f51-45c7-85e8-ebe321cbc168
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f9fb45f3fc90a0586f0f5b08dd12f0a244dd2332
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3145"></a>Compilerfehler C3145
'object': globale oder statische Variable hat möglicherweise nicht den verwalteten oder WinRT-Typ 'type'  
  
 Sie können nur CLR- oder WinRT-Objekte im Gültigkeitsbereich der Funktion definieren.  
  
 Im folgenden Beispiel wird C3145 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C3145.cpp  
// compile with: /clr  
using namespace System;   
ref class G {};   
  
G ^ ptr;   // C3145  
G ^ ptr2 = gcnew G;   // C3145  
  
ref class GlobalObjects {  
public:  
   static G ^ ptr;   // OK  
   static G ^ ptr2 = gcnew G;   // OK   
};   
  
int main() {  
   G ^ ptr;   // OK  
   G ^ ptr2 = gcnew G;   // OK  
}  
```  
  
 Im folgenden Beispiel wird C3145 generiert:  
  
```  
// C3145b.cpp  
// compile with: /clr  
ref class MyClass {  
public:  
   static int data;  
};  
  
interior_ptr<int> p = &(MyClass::data);   // C3145  
  
void Test(interior_ptr<int> x) {}  
  
int main() {  
   MyClass ^ h_MyClass = gcnew MyClass;  
   interior_ptr<int> p = &(h_MyClass->data);  
}  
```  
