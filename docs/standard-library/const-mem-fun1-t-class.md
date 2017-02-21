---
title: "const_mem_fun1_t-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.const_mem_fun1_t"
  - "xfunctional/std::const_mem_fun1_t"
  - "std::const_mem_fun1_t"
  - "const_mem_fun1_t"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "const_mem_fun1_t-Klasse"
ms.assetid: 250fac30-9663-4133-9051-6303f76ea259
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# const_mem_fun1_t-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Adapterklasse, die eine **const**\-Memberfunktion zulässig, die ein einzelnes als akzeptiert binäres Funktionsobjekt aufgerufen werden Argument, wenn sie mit einem Zeigerargument initialisiert wird.  
  
## Syntax  
  
```  
template<class Result, class Type, class Arg>  
   class const_mem_fun1_t  
      : public binary_function<const Type *, Arg, Result>   
   {  
   explicit const_mem_fun1_t( Result ( Type::* _Pm )( Arg ) const );  
   Result operator()(  
      const Type* _Pleft,   
      Arg _Right  
   ) const;  
   };  
```  
  
#### Parameter  
 `_Pm`  
 Ein Zeiger auf eine Memberfunktion einer Klasse einem Funktionsobjekt konvertiert werden, **Typ**.  
  
 `_Pleft`  
 Das **const**\-Objekt, dass die `_Pm`\-Memberfunktion aufgerufen wird.  
  
 `_Right`  
 Das Argument `_Pm`, das angegeben wird.  
  
## Rückgabewert  
 Eine entsprechende binäre Funktion.  
  
## Hinweise  
 Die Vorlagenklasse speichert eine Kopie von `_Pm`, einen Zeiger auf eine Memberfunktion der Klasse **Typ** sein muss, in einem Objekt des privaten Members.  Es definiert die Memberfunktion `operator()` als Rückgabe \(**\_Pleft**\-\>\* *Pm\)\(***Right**\) **const**.  
  
## Beispiel  
 Der Konstruktor des `const_mem_fun1_t` wird in der Regel nicht direkt verwendet; die Hilfsfunktion `mem_fun` wird verwendet, um Memberfunktionen anzupassen.  Unter [mem\_fun](../Topic/mem_fun%20Function.md) finden Sie ein Beispiel, wie Memberfunktionsadapter verwendet.  
  
## Anforderungen  
 **Header:** \<functional\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Standard Template Library](../misc/standard-template-library.md)