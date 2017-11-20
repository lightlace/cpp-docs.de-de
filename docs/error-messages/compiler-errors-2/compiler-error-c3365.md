---
title: Compilerfehler C3365 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3365
dev_langs:
- C++
helpviewer_keywords:
- C3365
ms.assetid: 875ec3a4-522c-4e3d-9b67-48808b857f6d
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 2352ff83181fe1127e1faa60829d00f03508bccd
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3365"></a>Compilerfehler C3365
Operator-Operator: Unterschiedliche Operanden vom Typ "Typ1" und "Typ2".  
  
Es wurde versucht, Delegaten mit unterschiedlichen Typen zu erstellen.  Finden Sie unter [wie: definieren und verwenden Delegaten (C + c++ / CLI)](../../dotnet/how-to-define-and-use-delegates-cpp-cli.md) für Weitere Informationen über Delegaten.  
  
## <a name="example"></a>Beispiel  
Im folgenden Beispiel wird C3365 generiert:  
  
```cpp  
// C3365.cpp  
// compile with: /clr  
delegate void D1();  
delegate void D2(int);  
  
ref class R {  
public:  
   void f(){}  
   void g(int){}  
};  
  
int main() {  
   D1^ d1 = gcnew D1(gcnew R, &R::f);  
   D2^ d2 = gcnew D2(gcnew R, &R::g);  
   D1^ d3 = gcnew D1(gcnew R, &R::f);  
  
   d1 += d2;   // C3365  
   d1 += d3;   // OK  
   d1();  
}  
```