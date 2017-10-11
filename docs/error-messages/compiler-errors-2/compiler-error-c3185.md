---
title: Compiler-Fehler C3185 generiert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3185
dev_langs:
- C++
helpviewer_keywords:
- C3185
ms.assetid: 5bf96279-043c-4981-9d02-b4550071b192
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 10b25fa08693e4fc6c4e495c84944d79ab6e73ae
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3185"></a>Compiler-Fehler C3185 generiert
"TypeId" verwendet für verwalteten oder WinRT-Typ "Typ"; verwenden Sie stattdessen "Operator".  
  
 Sie können nicht angewendet werden die [Typeid](../../cpp/typeid-operator.md) Operator, um ein verwaltetes oder WinRT-Typ; verwenden Sie [Typeid](../../windows/typeid-cpp-component-extensions.md) stattdessen.  
  
 Im folgenden Beispiel wird C3185 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C3185a.cpp  
// compile with: /clr  
ref class Base {};  
ref class Derived : public Base {};  
  
int main() {  
   Derived ^ pd = gcnew Derived;  
   Base ^pb = pd;  
   const type_info & t1 = typeid(pb);   // C3185  
   System::Type ^ MyType = Base::typeid;   // OK  
};  
```  

