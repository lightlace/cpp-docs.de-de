---
title: "Compilerfehler C3255"
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
  - "C3255"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3255"
ms.assetid: 877ffca2-fd92-44b6-9060-6091b928b1c1
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3255
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Werttyp': Werttypobjekt kann nicht dynamisch auf systemeigenem Heap zugewiesen werden  
  
 Instanzen eines Werttyps \(siehe [Classes and Structs](../../windows/classes-and-structs-cpp-component-extensions.md)\), die verwaltete Member enthalten, können zwar auf dem Stapel, nicht aber auf dem Heap erstellt werden.  
  
 Im folgenden Beispiel wird C3255 generiert:  
  
```  
// C3255.cpp  
// compile with: /clr  
using namespace System;  
value struct V {  
   Object^ o;  
};  
  
value struct V2 {  
   int i;  
};  
  
int main() {  
   V* pv = new V;   // C3255  
   V2* pv2 = new V2;  
   V v2;  
}  
```  
  
 **Managed Extensions for C\+\+**  
  
 Im folgenden Beispiel wird C3255 generiert:  
  
```  
// C3255b.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
using namespace System;  
  
__value struct V {  
   Object* o;  
};  
  
__value struct V2 {  
   int i;  
};  
  
int main() {  
   V* pv = __nogc new V;   // C3255  
   V2* pv2 = __nogc new V2;   // OK  
}  
```