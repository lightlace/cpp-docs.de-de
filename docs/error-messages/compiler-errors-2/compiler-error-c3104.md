---
title: Compilerfehler C3104 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3104
dev_langs:
- C++
helpviewer_keywords:
- C3104
ms.assetid: b5648d47-e5d3-4b45-a3c0-f46e04eae731
caps.latest.revision: 14
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
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: 5df018fe26e66ed480ed2464c19c876adfac8dd1
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3104"></a>Compilerfehler C3104
Unzulässiges Attributargument.  
  
 Sie haben ein ungültiges Argument für ein Attribut angegeben.  
  
 Finden Sie unter [Attributparametertypen](../../windows/attribute-parameter-types-cpp-component-extensions.md) Weitere Informationen.  
  
 Dieser Fehler kann aufgrund der Compilerkonformität, die für Visual C++ 2005 generiert werden: Wenn verwaltete Arrays an benutzerdefinierte Attribute übergeben werden, wird der Typ des Arrays nicht mehr aus der abgeleitet. Es ist nun erforderlich, den Typ des Arrays als auch die Initialisiererliste anzugeben.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C3104 generiert.  
  
```  
// C3104a.cpp  
// compile with: /clr /c  
using namespace System;  
  
[AttributeUsage(AttributeTargets::Class)]  
public ref struct ABC : public Attribute {  
   ABC(array<int>^){}  
   array<double> ^ param;  
};  
  
[ABC( {1,2,3}, param = {2.71, 3.14})]   // C3104  
// try the following line instead  
// [ABC( gcnew array<int> {1,2,3}, param = gcnew array<double>{2.71, 3.14})]   
ref struct AStruct{};  
```  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C3104 generiert.  
  
```  
// C3104b.cpp  
// compile with: /clr /c  
// C3104 expected  
using namespace System;  
  
int func() {  
   return 0;   
}  
  
[attribute(All)]  
ref class A {  
public:   
   A(int) {}  
};  
  
// Delete the following 2 lines to resolve.  
[A(func())]  
ref class B {};  
  
// OK  
[A(0)]  
ref class B {};  
```  

