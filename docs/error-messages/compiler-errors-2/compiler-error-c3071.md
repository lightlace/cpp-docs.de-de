---
title: "Compilerfehler C3071"
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
  - "C3071"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3071"
ms.assetid: 69879e66-a60e-4058-9bbd-d5c5e2d8ee37
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3071
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der „operator“\-Operator kann nur auf eine Instanz einer Verweisklasse oder auf einen Werttyp angewendet werden.  
  
 Ein CLR\-Operator kann nicht für einen systemeigenen Typ verwendet werden.  Der Operator kann für eine Verweisklasse oder einer Referenzstruktur \(Werttyp\), jedoch nicht für einen systemeigenen Typ, z. B. Int, oder einen Alias für einen systemeigenen Typ, z. B. System::Int32 verwendet werden.  Diese Typen können nicht vom C\+\+\-Code so geschachtelt werden, dass sie auf die systemeigene Variable verweisen, sodass der Operator nicht verwendet werden kann.  
  
 Weitere Informationen finden Sie unter [Tracking Reference Operator](../../windows/tracking-reference-operator-cpp-component-extensions.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C3071 generiert.  
  
```  
// C3071.cpp  
// compile with: /clr  
class N {};  
ref struct R {};  
  
int main() {  
   N n;  
   %n;   // C3071  
  
   R r;  
   R ^ r2 = %r;   // OK  
}  
```