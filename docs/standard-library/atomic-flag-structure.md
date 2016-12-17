---
title: "atomic_flag-Struktur"
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
  - "atomic/std::atomic_flag"
dev_langs: 
  - "C++"
ms.assetid: 17f0c2f5-fd39-4a44-873a-b569720a670e
caps.latest.revision: 14
caps.handback.revision: "4"
ms.author: "corob"
manager: "ghogen"
---
# atomic_flag-Struktur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beschreibt ein Objekt, das ein Flag `bool`\-Flag atomisch festlegt und löscht.  Vorgänge auf atomischen Flags sind immer sperrenfrei.  
  
## Syntax  
  
```  
struct atomic_flag;  
```  
  
## Member  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[atomic\_flag::clear\-Methode](../Topic/atomic_flag::clear%20Method.md)|Legt das gespeicherte Flag auf `false` fest.|  
|[atomic\_flag::test\_and\_set\-Methode](../Topic/atomic_flag::test_and_set%20Method.md)|Legt das gespeicherte Flag auf `true` fest und gibt den ursprünglichen Flagwert zurück.|  
  
## Hinweise  
 `atomic_flag`\-Objekte können den nicht Memberfunktionen [atomic\_flag\_clear](../Topic/atomic_flag_clear%20Function.md), [atomic\_flag\_clear\_explicit](../Topic/atomic_flag_clear_explicit%20Function.md), [atomic\_flag\_test\_and\_set](../Topic/atomic_flag_test_and_set%20Function.md) und [atomic\_flag\_test\_and\_set\_explicit](../Topic/atomic_flag_test_and_set_explicit%20Function.md) übergeben werden.  Sie können mithilfe des `ATOMIC_FLAG_INIT`\-Werts initialisiert werden.  
  
## Anforderungen  
 **Header:** atomisch  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<atomic\>](../standard-library/atomic.md)