---
title: "Compilerfehler C2694"
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
  - "C2694"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2694"
ms.assetid: 8dc2cec2-67ae-4e16-8c0c-374425aca8bc
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
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