---
title: "Gewusst wie: Definieren eines statischen Schnittstellenkonstruktors (C++/CLI)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Konstruktoren [C++]"
  - "Statische Schnittstellenkonstruktoren"
  - "Statische Konstruktoren, Schnittstelle"
ms.assetid: 1f031cb2-e94f-43dc-819b-44cf2faaaa49
caps.latest.revision: 10
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Definieren eines statischen Schnittstellenkonstruktors (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Schnittstelle kann keinen statischen Konstruktor haben, der verwendet werden kann, um Member der statischen Daten zu initialisieren.  Ein statischer Konstruktor wird höchstens einmal aufgerufen und wird zuvor aufgerufen, wenn auf einen statischen Schnittstellenmember zugegriffen wird.  
  
 Weitere Informationen zu statischen Konstruktoren, finden Sie unter [Gewusst wie: Definieren eines statischen Konstruktors in einer Klasse oder Struktur](../misc/how-to-define-static-constructors-in-a-class-or-struct.md).  
  
## Beispiel  
  
```  
// mcppv2_interface_class2.cpp  
// compile with: /clr  
using namespace System;  
  
interface struct MyInterface {  
   static int i;  
   static void Test() {  
      Console::WriteLine(i);  
   }  
  
   static MyInterface() {   
      Console::WriteLine("in MyInterface static constructor");  
      i = 99;  
   }  
};  
  
ref class MyClass : public MyInterface {};  
  
int main() {  
   MyInterface::Test();  
   MyClass::MyInterface::Test();  
  
   MyInterface ^ mi = gcnew MyClass;  
   mi->Test();  
}  
```  
  
  **in statischen Konstruktor MyInterface**  
**99**  
**99**  
**99**   
## Siehe auch  
 [interface class](../windows/interface-class-cpp-component-extensions.md)