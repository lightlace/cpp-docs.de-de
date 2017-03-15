---
title: "__raise | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__raise"
  - "__raise_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__raise-Schlüsselwort [C++]"
ms.assetid: 6f1ae418-5f0f-48b6-9f6e-8ea7e66b239a
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# __raise
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Hebt die Aufrufsite eines Ereignisses hervor.  
  
## Syntax  
  
```  
  
__raise   
method-declarator  
;  
  
```  
  
## Hinweise  
 Aus verwaltetem Code kann ein Ereignis nur innerhalb der Klasse ausgelöst werden, in der es definiert ist.  Weitere Informationen finden Sie unter [event](../windows/event-cpp-component-extensions.md).  
  
 Das Schlüsselwort `__raise` bewirkt die Ausgabe eines Fehlers bei einem nicht ereignisgebundenen Aufruf.  
  
> [!NOTE]
>  Eine von einer Vorlage gebildete Klasse oder Struktur kann keine Ereignisse enthalten.  
  
## Beispiel  
  
```  
// EventHandlingRef_raise.cpp  
struct E {  
   __event void func1();  
   void func1(int) {}  
  
   void func2() {}  
  
   void b() {  
      __raise func1();  
      __raise func1(1);  // C3745: 'int Event::bar(int)':   
                         // only an event can be 'raised'  
      __raise func2();   // C3745  
   }  
};  
  
int main() {  
   E e;  
   __raise e.func1();  
   __raise e.func1(1);  // C3745  
   __raise e.func2();   // C3745  
}  
```  
  
## Siehe auch  
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)   
 [Ereignisbehandlung](../cpp/event-handling.md)   
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)