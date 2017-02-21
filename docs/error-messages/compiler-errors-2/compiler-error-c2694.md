---
title: "Compilerfehler C2694 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2694"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2694"
ms.assetid: 8dc2cec2-67ae-4e16-8c0c-374425aca8bc
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C2694
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Überschreibung': Das Überschreiben der virtuellen Funktion hat eine weniger restriktive Ausnahmespezifikation als die virtuelle Memberfunktion einer Basisklasse 'Basis'  
  
 Eine virtuelle Funktion wurde überschrieben, bei Verwendung von [\/Za](../../build/reference/za-ze-disable-language-extensions.md) hatte die überschreibende Funktion jedoch eine weniger restriktive [Ausnahmespezifikation](../../cpp/exception-specifications-throw-cpp.md).  
  
 Im folgenden Beispiel wird C2694 generiert:  
  
```  
// C2694.cpp  
// compile with: /Za /c  
class MyBase {  
public:  
   virtual void f(void) throw(int) {  
   }  
};  
  
class Derived : public MyBase {  
public:  
   void f(void) throw(...) {}   // C2694  
   void f2(void) throw(int) {}   // OK  
};  
```