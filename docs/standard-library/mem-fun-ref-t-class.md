---
title: "mem_fun_ref_t-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "xfunctional/std::mem_fun_ref_t"
  - "mem_fun_ref_t"
  - "std.mem_fun_ref_t"
  - "std::mem_fun_ref_t"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "mem_fun_ref_t-Klasse"
ms.assetid: 7dadcac3-8d33-4e4b-a792-81bd53d3df39
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# mem_fun_ref_t-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Adapterklasse, die einer **non\_const**\-Memberfunktion, die keine Argumente akzeptiert, ermöglicht, als unäres Funktionsobjekt aufgerufen zu werden, wenn sie mit einem Verweisargument initialisiert wird.  
  
## Syntax  
  
```  
template<class Result, class Type>  
   class mem_fun_ref_t : public unary_function<Type, Result> {  
      explicit mem_fun_ref_t(  
         Result ( Type::*_Pm )( )   
      );  
      Result operator()( Type& _Left ) const;  
   };  
```  
  
#### Parameter  
 `_Pm`  
 Ein Zeiger auf eine Memberfunktion einer Klasse einem Funktionsobjekt konvertiert werden, **Typ**.  
  
 `_Left`  
 Das Objekt, auf die die `_Pm`\-Memberfunktion aufgerufen wird.  
  
## Rückgabewert  
 Eine gültige unäre Funktion.  
  
## Hinweise  
 Die Vorlagenklasse speichert eine Kopie von `_Pm`, einen Zeiger auf eine Memberfunktion der Klasse **Typ** sein muss, in einem Objekt des privaten Members.  Es definiert die Memberfunktion `operator()` als Rückgabe \(**\_Left**. \*\) \( `_Pm`\).  
  
## Beispiel  
 Der Konstruktor des `mem_fun_ref_t` wird in der Regel nicht direkt verwendet; die Hilfsfunktion `mem_fun_ref` wird verwendet, um Memberfunktionen anzupassen.  Unter [mem\_fun\_ref](../Topic/mem_fun_ref%20Function.md) finden Sie ein Beispiel, wie Memberfunktionsadapter verwendet.  
  
## Anforderungen  
 **Header:** \<functional\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Standard Template Library](../misc/standard-template-library.md)