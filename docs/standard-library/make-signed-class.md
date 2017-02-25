---
title: "make_signed-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::tr1::make_signed"
  - "make_signed"
  - "std.tr1.make_signed"
  - "std.make_signed"
  - "std::make_signed"
  - "type_traits/std::make_signed"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "make_signed-Klasse[TR1]"
  - "make_signed"
ms.assetid: 686247c0-247c-496b-9b1b-ba9dcd633621
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# make_signed-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Macht den Typ oder den kleinsten Typ mit Vorzeichen größer oder gleich dem Typ.  
  
## Syntax  
  
```  
template<class T>  
    struct make_signed;  
  
template<class T>  
    using make_signed_t = typename make_signed<T>::type;  
```  
  
#### Parameter  
 `T`  
 Der zu ändernde Typ.  
  
## Hinweise  
 Eine Instanz des Typmodifizierers enthält einen GeänderteTyp an, wenn der `T` als `is_signed<T>` true ist. Andernfalls ist der kleinste Datentyp mit Vorzeichen `UT`, für den `sizeof (T) <= sizeof (UT)`.  
  
## Anforderungen  
 **Header:** \<type\_traits\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<type\_traits\>](../standard-library/type-traits.md)