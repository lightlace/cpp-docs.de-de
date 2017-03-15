---
title: "Compilerfehler C2681 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2681"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2681"
ms.assetid: eb42da6d-8d2c-43fd-986b-e73e2b004885
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
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