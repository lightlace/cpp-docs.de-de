---
title: "Compilerfehler C2825"
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
  - "C2825"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2825"
ms.assetid: c832f1c1-5184-4fc2-9356-12b21daa7af3
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2825
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

var: muss eine Klasse oder ein Namespace sein, wenn '::' darauf folgt  
  
 Der Versuch, einen gekennzeichneten Namen zu erstellen, ist fehlgeschlagen.  
  
 Stellen Sie beispielsweise sicher, dass der Code keine Funktionsdeklaration enthält, deren Funktionsname mit `::` beginnt.  
  
## Beispiel  
 Im folgenden Beispiel wird C2825 generiert:  
  
```  
// C2825.cpp  
typedef int i;  
int main() {  
   int* p = new int;  
   p->i::i();   // C2825  
   // try the following line instead  
   // p->i::~i();  
}  
```