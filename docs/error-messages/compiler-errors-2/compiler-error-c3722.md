---
title: "Compilerfehler C3722 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3722"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3722"
ms.assetid: 3cb28363-5eff-4548-bd0d-d5c615846353
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
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