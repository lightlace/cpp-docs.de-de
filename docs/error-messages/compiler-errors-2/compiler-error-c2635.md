---
title: "Compilerfehler C2635"
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
  - "C2635"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2635"
ms.assetid: 9deca2a8-2d61-42eb-9783-6578132ee3fb
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2635
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Konvertierung von 'Bezeichner1\*' in 'Bezeichner2\*' nicht möglich; implizite Konvertierung einer virtuellen Basisklasse  
  
 Für die Konvertierung ist eine Typumwandlung von einer `virtual`\-Basisklasse in eine abgeleitete Klasse erforderlich. Dies ist jedoch nicht zulässig.  
  
 Im folgenden Beispiel wird C2635 generiert:  
  
```  
// C2635.cpp  
class B {};  
class D : virtual public B {};  
class E : public B {};  
  
int main() {  
   B b;  
   D d;  
   E e;  
  
   D * pD = &d;  
   E * pE = &e;  
   pD = (D*)&b;   // C2635  
   pE = (E*)&b;   // OK  
}  
```