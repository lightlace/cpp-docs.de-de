---
title: "Compilerfehler C2594 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2594"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2594"
ms.assetid: 68cd708f-266e-44b0-a211-3e3ab63b11bf
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# Compilerfehler C2594
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Operator': Mehrdeutige Konvertierung von 'Typ1' in 'Typ2'  
  
 Keine Konvertierung von *type1* in *type2* war direkter als die andere.  Es werden zwei mögliche Lösungen zum Konvertieren von *type1* in *type2* vorgeschlagen.  Die erste Möglichkeit ist, eine direkte Konvertierung von *type1* in *type2* zu definieren, und die zweite Option ist, einer Sequenz von Konvertierungen von *type1* in *type2* festlegen.  
  
 Im folgenden Beispiel wird C2594 generiert.  Für die Behebung des Fehlers wird eine Abfolge von Konvertierungen vorgeschlagen:  
  
```  
// C2594.cpp  
// compile with: /c  
struct A{};  
struct I1 : A {};  
struct I2 : A {};  
struct D : I1, I2 {};  
  
A *f (D *p) {  
   return (A*) (p);    // C2594  
  
// try the following line instead  
// return static_cast<A *>(static_cast<I1 *>(p));  
}  
```