---
title: "Compilerfehler C3722"
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
  - "C3722"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3722"
ms.assetid: 3cb28363-5eff-4548-bd0d-d5c615846353
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3722
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ein generisches Ereignis ist nicht zulässig  
  
 Der Compiler lässt nur generische Klassen, Strukturen und Funktionen zu.  Weitere Informationen finden Sie unter [Generics](../../windows/generics-cpp-component-extensions.md).  
  
 Im folgenden Beispiel wird C3722 generiert:  
  
```  
// C3722.cpp  
// compile with: /clr  
generic <typename T>  
public delegate void MyEventHandler(System::Object^ sender, System::EventArgs^ e, T optional);  
  
generic <class T>  
public ref struct MyButton {  
   generic<typename U>  
   event MyEventHandler<U>^ Click;   // C3722  
};  
```