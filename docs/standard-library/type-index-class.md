---
title: "type_index-Klasse"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "typeindex/std::type_index"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "type_index-Klasse"
ms.assetid: db366119-74cb-43e8-aacf-9679e561fa2f
caps.latest.revision: 14
caps.handback.revision: "4"
ms.author: "corob"
manager: "ghogen"
---
# type_index-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die `type_index`\-Klasse umschließt einen Zeiger auf eine [type\_info\-Klasse](../cpp/type-info-class.md) ein, um die Indizierung durch diese Objekte zu unterstützen.  
  
```  
class type_index {  
public:  
    type_index(const type_info& tinfo);  
    const char *name() const;  
    size_t hash_code() const;  
    bool operator==(const type_info& right) const;  
    bool operator!=(const type_info& right) const;  
    bool operator<(const type_info& right) const;  
    bool operator<=(const type_info& right) const;  
    bool operator>(const type_info& right) const;  
    bool operator>=(const type_info& right) const;  
};  
```  
  
 Der Konstruktor initialisiert `ptr` zu `&tinfo`.  
  
 `name` gibt `ptr->name()` zurück.  
  
 `hash_code` gibt `ptr->hash_code().` zurück.  
  
 `operator==` gibt `*ptr == right.ptr` zurück.  
  
 `operator!=` gibt `!(*this == right)` zurück.  
  
 `operator<` gibt `*ptr->before(*right.ptr)` zurück.  
  
 `operator<=` gibt `!(right < *this).` zurück.  
  
 gibt `right < *this``operator>`.  
  
 `operator>=` gibt `!(*this < right)` zurück.  
  
## Siehe auch  
 [Laufzeit\-Typinformationen](../cpp/run-time-type-information.md)   
 [\<typeindex\>](../standard-library/typeindex.md)