---
title: Compilerfehler C3699 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3699
dev_langs: C++
helpviewer_keywords: C3699
ms.assetid: 47c29afc-ab8b-4238-adfe-788dd6e00b3b
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2d4b89c2b91aab1869c97731731ed03a363767e8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3699"></a>Compilerfehler C3699
'Operator': Diese Dereferenzierung für Typ 'Typ' können keine  
  
 Es wurde versucht, Dereferenzierung zu verwenden, die für nicht zulässig ist `type`.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C3699 generiert.  
  
```  
// C3699.cpp  
// compile with: /clr /c  
using namespace System;  
int main() {  
   String * s;   // C3699  
   // try the following line instead  
   // String ^ s2;  
}  
```  
  
## <a name="example"></a>Beispiel  
 Eine triviale-Eigenschaft kann nicht Verweistyp aufweisen. Weitere Informationen finden Sie unter [property](../../windows/property-cpp-component-extensions.md) . Im folgende Beispiel wird C3699 generiert.  
  
```  
// C3699_b.cpp  
// compile with: /clr /c  
ref struct C {  
   property System::String % x;   // C3699  
   property System::String ^ y;   // OK  
};  
```  
  
## <a name="example"></a>Beispiel  
 Die Entsprechung von "Zeiger auf einen Zeiger"-Syntax ist ein Handle zu einem Nachverfolgungsverweis. Im folgende Beispiel wird C3699 generiert.  
  
```  
// C3699_c.cpp  
// compile with: /clr /c  
using namespace System;  
void Test(String ^^ i);   // C3699  
void Test2(String ^% i);  
```