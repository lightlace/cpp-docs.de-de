---
title: "decay-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "decay"
  - "std.tr1.decay"
  - "std::tr1::decay"
  - "std.decay"
  - "std::decay"
  - "type_traits/std::decay"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "decay-Klasse[TR1]"
ms.assetid: 96baa2fd-c8e0-49af-be91-ba375ba7f9dc
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# decay-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der Typ wird erzeugt, als Wert übergeben. Erstellt die nicht\-Verweis, nicht konstanter, permanenten oder erstellt einen Zeiger auf den Typ von einer Funktion oder einen Arraytyp.  
  
## Syntax  
  
```  
template<class T>  
    struct decay;  
  
template<class T> using decay_t = typename decay<T>::type;  
```  
  
#### Parameter  
 `T`  
 Der zu ändernde Typ.  
  
## Hinweise  
 Verwenden Sie die Vorlage Decay, den resultierenden Typ erzeugt, als ob der Typ durch einen Wert als Argument übergeben wurde. Die Vorlage Klasse Member Typedef `type` enthält einen geänderten Typ, der in den folgenden Phasen definiert ist:  
  
-   Der Typ `U` ist als `remove_reference<T>::type` definiert.  
  
-   Wenn `is_array<U>::value` gilt der geänderte Typ `type` ist `remove_extent<U>::type *`.  
  
-   Andernfalls gilt: Wenn `is_function<U>::value` gilt der geänderte Typ `type` ist `add_pointer<U>::type`.  
  
-   Andernfalls den geänderten Typ `type` ist `remove_cv<U>::type`.  
  
## Anforderungen  
 **Header:** \<type\_traits\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<type\_traits\>](../standard-library/type-traits.md)