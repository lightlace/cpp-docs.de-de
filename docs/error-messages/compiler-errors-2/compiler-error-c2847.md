---
title: "Compilerfehler C2847"
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
  - "C2847"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2847"
ms.assetid: 9ad9a0e0-8b16-49d9-a5be-f8eda2372aa9
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2847
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

sizeof kann nicht auf verwalteten oder WinRT\-Typ „Klasse“ angewendet werden.  
  
 Der [sizeof](../../cpp/sizeof-operator.md) \-Operator ruft den Wert eines Objekts zur Kompilierungszeit ab.  Die Größe einer verwalteten oder WinRT\-Klasse, Schnittstelle oder eines Werttyps ist dynamisch und ist zur Kompilierzeit nicht bekannt.  
  
 Im folgenden Beispiel wird C2847 generiert:  
  
```  
// C2847.cpp  
// compile with: /clr  
ref class A {};  
  
int main() {  
   A ^ xA = gcnew A;  
   sizeof(*xA);   // C2847 cannot use sizeof on managed object  
}  
```  
  
 Im folgenden Beispiel wird C2847 generiert:  
  
```  
// C2847_b.cpp  
// compile with: /clr:oldSyntax  
__gc class A {};  
  
int main() {  
   A *xA = new A;  
   sizeof(*xA);   // C2847 cannot use sizeof on managed object  
}  
```