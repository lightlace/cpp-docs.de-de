---
title: "unchecked_array_iterator-Klasse"
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
  - "unchecked_array_iterator"
  - "stdext::unchecked_array_iterator"
dev_langs: 
  - "C++"
ms.assetid: 693b3b30-4e3a-465b-be06-409700bc50b1
caps.latest.revision: 15
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# unchecked_array_iterator-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die `unchecked_array_iterator`\-Klasse ermöglicht es Ihnen, ein Array oder einen Zeiger in einen deaktivierten Iterator zu umschließen.  Verwenden Sie diese Klasse \(mithilfe der [make\_unchecked\_array\_iterator](../Topic/make_unchecked_array_iterator.md)\-Funktion\) als Wrapper für unformatierte Zeiger oder Arrays als entsprechende Methode zum Verwalten nicht aktivierter Zeigerwarnungen, anstatt diese Warnungen global zu deaktivieren.  Verwenden Sie, wenn möglich, die aktivierte Version der Klasse [checked\_array\_iterator](../standard-library/checked-array-iterator-class.md).  
  
> [!NOTE]
>  Bei dieser Klasse handelt es sich um eine Microsoft\-Erweiterung der C\+\+\-Standardbibliothek.  Der Code, der mit dieser Funktion implementiert wird, ist nicht auf C\+\+\-Standardbuildumgebungen übertragbar, die die Microsoft\-Erweiterung nicht unterstützen.  
  
## Syntax  
  
```  
template <class Iterator>  
    class unchecked_array_iterator;  
```  
  
## Hinweise  
 Diese Klasse wird im [stdext](../standard-library/stdext-namespace.md)\-Namespace definiert.  
  
 Das ist die nicht aktivierte Version der [checked\_array\_iterator\-Klasse](../standard-library/checked-array-iterator-class.md), und sie unterstützt dieselben Überladungen und Member.  Weitere Informationen zur aktivierten Iteratorfunktion mit Codebeispielen finden Sie unter [Überprüfte Iteratoren](../standard-library/checked-iterators.md).  
  
## Anforderungen  
 **Header:** \<Iterator\>  
  
 **Namespace:** stdext  
  
## Siehe auch  
 [\<iterator\>](../standard-library/iterator.md)   
 [Standard Template Library](../misc/standard-template-library.md)