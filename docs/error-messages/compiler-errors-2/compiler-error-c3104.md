---
title: Compilerfehler C3104 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3104
dev_langs: C++
helpviewer_keywords: C3104
ms.assetid: b5648d47-e5d3-4b45-a3c0-f46e04eae731
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b23007d4985319a7570b9efb4a0f14f639a0c0d7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3104"></a>Compilerfehler C3104
Unzulässiges Attributargument.  
  
 Sie haben ein ungültiges Argument für ein Attribut angegeben.  
  
 Finden Sie unter [Attributparametertypen](../../windows/attribute-parameter-types-cpp-component-extensions.md) für Weitere Informationen.  
  
 Dieser Fehler kann infolge einer konformitätsverbesserung für Visual C++ 2005 erstellt wurde, die generiert werden: beim Übergeben von verwalteten Arrays, benutzerdefinierte Attribute wird der Typ des Arrays nicht mehr aus der Liste aggregatinitialisierung hergeleitet. Es ist jetzt erforderlich, geben Sie den Typ des Arrays als auch in der Initialisiererliste.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3104 generiert.  
  
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
 Im folgenden Beispiel wird C3104 generiert.  
  
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
