---
title: "time_put_byname-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "time_put_byname"
  - "xloctime/std::time_put_byname"
  - "std.time_put_byname"
  - "std::time_put_byname"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "time_put_byname-Klasse"
ms.assetid: e08c2348-64d2-4ace-98b1-1496e14c7b1a
caps.latest.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 25
---
# time_put_byname-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die abgeleitete Vorlagenklasse beschreibt ein Objekt, das als gebietsschemafacet vom Typ dienen kann `time_put`\< CharType, OutputIterator \>.  
  
## Syntax  
  
```  
template<class CharType,  
 class OutIt = ostreambuf_iterator<CharType, char_traits<CharType> > >  
 class time_put_byname : public time_put<CharType, OutputIterator>  
{  
public:  
    explicit time_put_byname(  
        const char *_Locname,  
        size_t _Refs = 0  
    );  
    explicit time_put_byname(  
        const string& _Locname,  
        size_t _Refs = 0  
    );  
protected:  
    virtual ~time_put_byname();  
};  
```  
  
#### Parameter  
 `_Locname`  
 Eine Gebietsschemanamen.  
  
 `_Refs`  
 Ein Verweiszähler.  
  
## Hinweise  
 Das Verhalten richtet sich nach der [namens](../Topic/locale::name.md) Gebietsschema `_Locname`. Jeder Konstruktor initialisiert die Basisobjekt mit [Time\_put](../Topic/time_put::time_put.md)\< CharType, OutputIterator \> \(`_Refs`\).  
  
## Anforderungen  
 **Header:** \<Gebietsschema\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)