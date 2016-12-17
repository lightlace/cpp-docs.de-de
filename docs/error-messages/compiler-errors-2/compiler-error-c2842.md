---
title: "Compilerfehler C2842"
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
  - "C2842"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2842"
ms.assetid: 8674f08d-9f50-46ad-9229-abc6b74fa0e5
caps.latest.revision: 13
caps.handback.revision: "13"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2842
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

„Klasse“: Ein verwalteter oder WinRT\-Typ kann keinen eigenen „operator new“\- oder „operator delete“\-Operator definieren.  
  
 Sie können einen eigenen [operator new](../Topic/operator%20new%20\(%3Cnew%3E\).md)\- oder [operator delete](../Topic/operator%20delete%20\(%3Cnew%3E\).md)\-Operator definieren, um die Speicherbelegung auf dem systemeigenen Heap zu verwalten.  Verweisklassen können jedoch diese Operatoren nicht definieren, da sie nur dem verwalteten Heap zugewiesen sind.  
  
 Weitere Informationen finden Sie unter [Benutzerdefinierte Operatoren](../../dotnet/user-defined-operators-cpp-cli.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C2842 generiert.  
  
```  
// C2842.cpp  
// compile with: /clr /c  
ref class G {  
   void* operator new( size_t nSize );   // C2842  
};  
```  
  
## Beispiel  
 Im folgenden Beispiel wird C2842 generiert.  
  
```  
// C2842_b.cpp  
// compile with: /clr:oldSyntax /c  
__gc class G {  
   void* operator new( size_t nSize );   // C2842  
};  
```