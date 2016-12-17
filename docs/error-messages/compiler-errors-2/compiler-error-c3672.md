---
title: "Compilerfehler C3672"
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
  - "C3672"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3672"
ms.assetid: da971041-1766-467a-aecf-1d8655c6cb7a
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3672
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Pseudodestruktor\-Ausdruck kann nur als Teil eines Funktionsaufrufs verwendet werden  
  
 Eine Destruktor wurde nicht ordnungsgemäß aufgerufen.  Weitere Informationen finden Sie unter [Destruktoren](../../cpp/destructors-cpp.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C3672 generiert.  
  
```  
// C3672.cpp  
template<typename T>  
void f(T* pT) {  
   &pT->T::~T;   // C3672  
   pT->T::~T();   // OK  
};  
  
int main() {  
   int i;  
   f(&i);  
}  
```