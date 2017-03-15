---
title: "Gewusst wie: Test auf Gleichheit (C++/CLI)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Gleichheit, Testen auf"
ms.assetid: 9115e298-9f75-452d-bdfb-6eeb0fa0b3c6
caps.latest.revision: 15
caps.handback.revision: "15"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Test auf Gleichheit (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Im folgenden Beispiel basiert ein Test auf Gleichheit, für den Managed Extensions for C\+\+ verwendet wird, auf dem Bezug der Handles.  
  
## Beispiel  
  
```  
// mcppv2_equality_test.cpp  
// compile with: /clr /LD  
using namespace System;  
  
bool Test1() {  
   String ^ str1 = "test";  
   String ^ str2 = "test";  
   return (str1 == str2);  
}  
```  
  
 Die IL für dieses Programm zeigt, dass der Rückgabewert mit dem Aufruf von "op\_Equality" implementiert wird.  
  
```  
IL_0012:  call       bool [mscorlib]System.String::op_Equality(string,  
                                                               string)  
```  
  
## Siehe auch  
 [Verwaltete Typen](../dotnet/managed-types-cpp-cli.md)