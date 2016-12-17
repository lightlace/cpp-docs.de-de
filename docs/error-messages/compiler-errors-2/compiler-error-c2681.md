---
title: "Compilerfehler C2681"
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
  - "C2681"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2681"
ms.assetid: eb42da6d-8d2c-43fd-986b-e73e2b004885
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2681
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Typ': Ungültiger Ausdruckstyp für Name  
  
 Ein Umwandlungsoperator hat versucht, einen ungültigen Typ zu konvertieren.  Wenn Sie z. B. den Operator [dynamic\_cast](../../cpp/dynamic-cast-operator.md) verwenden, um einen Ausdruck in einen Zeigertyp zu konvertieren, muss der Quellausdruck ein Zeiger sein.  
  
 Im folgenden Beispiel wird C2681 generiert:  
  
```  
// C2681.cpp  
class A { virtual void f(); };  
  
void g(int i) {  
    A* pa;  
    pa = dynamic_cast<A*>(i);  // C2681  
}  
```