---
title: "const_mem_fun_t-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "const_mem_fun_t"
  - "std.const_mem_fun_t"
  - "xfunctional/std::const_mem_fun_t"
  - "std::const_mem_fun_t"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "const_mem_fun_t-Klasse"
ms.assetid: f169d381-019b-4a0e-a9a3-54da6d948270
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# const_mem_fun_t-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Adapterklasse, die einer const\-Memberfunktion, die keine Argumente akzeptiert, ermöglicht, als unäres Funktionsobjekt aufgerufen zu werden, wenn sie mit einem Verweisargument initialisiert wird.  
  
## Syntax  
  
```  
template<class Result, class Type>  
   class const_mem_fun_t : public unary_function <Type *, Result>   
   {  
   explicit const_mem_fun_t( Result ( Type::* _Pm )( ) const );  
   Result operator()(  
      const Type* _Pleft  
   ) const;  
   };  
```  
  
#### Parameter  
 `_Pm`  
 Ein Zeiger auf eine Memberfunktion einer Klasse einem Funktionsobjekt konvertiert werden, **Typ**.  
  
 `_Pleft`  
 Das Objekt, auf die die `_Pm`\-Memberfunktion aufgerufen wird.  
  
## Rückgabewert  
 Eine gültige unäre Funktion.  
  
## Hinweise  
 Die Vorlagenklasse speichert eine Kopie von `_Pm`, einen Zeiger auf eine Memberfunktion der Klasse **Typ** sein muss, in einem Objekt des privaten Members.  Es definiert die Memberfunktion `operator()` als Rückgabe \(`_Pleft`\-\>\* `_Pm`\)\(\) **const**.  
  
## Beispiel  
 Der Konstruktor des `const_mem_fun_t` wird in der Regel nicht direkt verwendet; die Hilfsfunktion `mem_fun` wird verwendet, um Memberfunktionen anzupassen.  Unter [mem\_fun](../Topic/mem_fun%20Function.md) finden Sie ein Beispiel, wie Memberfunktionsadapter verwendet.  
  
## Anforderungen  
 **Header:** \<functional\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Standard Template Library](../misc/standard-template-library.md)