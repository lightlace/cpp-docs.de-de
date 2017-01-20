---
title: "Standardumwandlungen und implizites Boxing"
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
  - "Boxing, Implizite"
ms.assetid: 33f7fc7d-5674-44a2-a859-0e6a04fae519
caps.latest.revision: 6
caps.handback.revision: "4"
ms.author: "mblome"
manager: "ghogen"
---
# Standardumwandlungen und implizites Boxing
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Standardkonvertierung wird vom Compiler zur einer Konvertierung, die ausgewählt Boxing erfordert.  
  
## Beispiel  
  
```  
// clr_implicit_boxing_Std_conversion.cpp  
// compile with: /clr  
int f3(int ^ i) {   // requires boxing  
   return 1;  
}  
  
int f3(char c) {   // no boxing required, standard conversion  
   return 2;  
}  
  
int main() {  
   int i = 5;  
   System::Console::WriteLine(f3(i));  
}  
```  
  
 **2**   
## Siehe auch  
 [Boxing](../windows/boxing-cpp-component-extensions.md)