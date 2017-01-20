---
title: "Compilerfehler C3142"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C3142"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3142"
ms.assetid: 795137ad-d00a-4a9c-9665-0cd8bfb5da8b
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3142
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'property\_name' : Sie können die Adresse einer Eigenschaft nicht verwenden  
  
 Die Adresse einer Eigenschaft ist dem Programmierer nicht zugänglich.  
  
 Im folgenden Beispiel wird C3142 generiert:  
  
```  
// C3142_2.cpp  
// compile with: /clr  
using namespace System;  
ref class CSize {  
private:  
   property int Size {  
      int get();  
   }  
};  
  
int main() {  
    &CSize::Size; // C3142  
}  
```  
  
 Im folgenden Beispiel wird C3142 generiert:  
  
```  
// C3142.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
using namespace System;  
  
__gc class CSize  
{  
   __property int get_Size();  
};  
  
int main()  
{  
   &CSize::Size;   // C3142  
}  
```