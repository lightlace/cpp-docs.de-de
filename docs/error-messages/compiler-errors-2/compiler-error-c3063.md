---
title: "Compilerfehler C3063 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3063"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3063"
ms.assetid: 0ecf6f1f-e4a7-487a-9fd5-79d8ac470001
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C3063
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Operator 'Operator': Alle Operanden müssen den gleichen Enumerationstyp aufweisen  
  
 Wenn Sie Operatoren auf Enumeratoren verwenden, müssen beide Operanden vom Enumerationstyp sein.  Weitere Informationen finden Sie unter [Verwenden von Operatoren und Enumerationen](../../misc/operators-and-enumerations.md).  
  
 Im folgenden Beispiel wird C3063 generiert:  
  
```  
// C3063.cpp  
// compile with: /clr  
enum class E { a, b } e, mask;  
int main() {  
   if ( ( e & mask ) != 0 ) ;   // C3063 no operator!= (E, int)  
  
   if ( ( e & mask ) != E() )   // OK  
      ;  
}  
```