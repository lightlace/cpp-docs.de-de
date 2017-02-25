---
title: "mem_fun_t-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "mem_fun_t"
  - "xfunctional/std::mem_fun_t"
  - "std::mem_fun_t"
  - "std.mem_fun_t"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "mem_fun_t-Klasse"
ms.assetid: 242566d4-750c-4c87-9d63-2e2c9d19ca2a
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# mem_fun_t-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Adapterklasse, die einer **non\_const**\-Memberfunktion, die keine Argumente akzeptiert, ermöglicht, als unäres Funktionsobjekt aufgerufen zu werden, wenn sie mit einem Zeigerargument initialisiert wird.  
  
## Syntax  
  
```  
template<class Result, class Type>  
   class mem_fun_t : public unary_function<Type *, Result> {  
      explicit mem_fun_t(Result ( Type::*_Pm )( ) );  
      Result operator()( Type* _Pleft ) const;  
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
 Die Vorlagenklasse speichert eine Kopie von `_Pm`, einen Zeiger auf eine Memberfunktion der Klasse **Typ** sein muss, in einem Objekt des privaten Members.  Sie definiert die Memberfunktion `operator()` als Rückgabe \(`_Pleft`\-\>\* `_Pm`\)\( \).  
  
## Beispiel  
 Der Konstruktor des `mem_fun_t` wird in der Regel nicht direkt verwendet; die Hilfsfunktion `mem_fun` wird verwendet, um Memberfunktionen anzupassen.  Unter [mem\_fun](../Topic/mem_fun%20Function.md) finden Sie ein Beispiel, wie Memberfunktionsadapter verwendet.  
  
## Anforderungen  
 **Header:** \<functional\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<functional\>](../standard-library/functional.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Standard Template Library](../misc/standard-template-library.md)