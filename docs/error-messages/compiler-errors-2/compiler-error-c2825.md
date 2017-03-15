---
title: "Compilerfehler C2825 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2825"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2825"
ms.assetid: c832f1c1-5184-4fc2-9356-12b21daa7af3
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
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