---
title: "hash-Struktur (STL) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "thread/std::hash"
dev_langs: 
  - "C++"
ms.assetid: 4a8bf5bc-4334-4070-936b-98585f8a073b
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# hash-Struktur (STL)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Definiert eine Memberfunktion, die einen Wert, die vom eindeutig bestimmt zurückgibt `Val`. Die Member-Funktion definiert einen [Hash](hash%20Class.md) Funktion für die Zuordnung von Werten des Typs `thread::id` auf eine Verteilung von Indexwerten.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <>  
struct hash<thread::id> :   
    public unary_function<thread::id, size_t>  
{  
    size_t operator()(thread::id Val) const;

 
};  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Thread  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [\< Thread>](../standard-library/thread.md)   
 [Unary_function-Struktur](../standard-library/unary-function-struct.md)
