---
title: "Compilerfehler C3114 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3114"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3114"
ms.assetid: b5d2df4f-87d0-4292-9981-25c6a6013c05
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerfehler C3114
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Argument': Kein gültiges benanntes Attributargument  
  
 Damit eine Datenmember einer Attributklasse ein gültiges benanntes Argument sein kann, darf es nicht mit `static`, `const` oder `literal` gekennzeichnet werden.  Wenn es sich um eine Eigenschaft handelt, darf die Eigenschaft nicht `static` sein, und sie muss über get\- und set\-Accessoren verfügen.  
  
 Weitere Informationen finden Sie unter [property](../../windows/property-cpp-component-extensions.md) und [User\-Defined Attributes](../../windows/user-defined-attributes-cpp-component-extensions.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C3114 generiert.  
  
```  
// C3114.cpp  
// compile with: /clr /c  
public ref class A : System::Attribute {  
public:  
   static property int StaticProp {  
      int get();  
   }  
  
   property int Prop2 {  
      int get();  
      void set(int i);  
   }  
};  
  
[A(StaticProp=123)]   // C3114  
public ref class R {};  
  
[A(Prop2=123)]   // OK  
public ref class S {};  
```