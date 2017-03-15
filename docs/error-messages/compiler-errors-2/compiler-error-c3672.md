---
title: "Compilerfehler C3672 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3672"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3672"
ms.assetid: da971041-1766-467a-aecf-1d8655c6cb7a
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
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