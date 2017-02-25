---
title: "codecvt_byname-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.codecvt_byname"
  - "codecvt_byname"
  - "std::codecvt_byname"
  - "xlocale/std::codecvt_byname"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "codecvt_byname-Klasse"
ms.assetid: b63b6c04-f60c-47b9-8e30-a933f24a8ffb
caps.latest.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 24
---
# codecvt_byname-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine abgeleitete Vorlagenklasse, die ein Objekt beschrieben wird, das als sortierensfacet eines angegebenen Gebietsschemas dienen kann, den der jeweilige zu einem kulturellen Bereich hinsichtlich der Konvertierungen aktiviert.  
  
## Syntax  
  
```  
template<Class CharType, class Byte, class StateType>  
    class codecvt_byname: public codecvt<CharType, Byte, StateType> {  
public:  
    explicit codecvt_byname(  
        const char* _Locname,  
        size_t _Refs = 0  
    );  
```  
  
```  
explicit codecvt_byname(  
    const string& _Locname,  
    size_t _Refs = 0  
);  
```  
  
```  
protected:  
    virtual ~codecvt_byname( );  
};  
```  
  
#### Parameter  
 `_Locname`  
 Ein benanntes Gebietsschema.  
  
 `_Refs`  
 Ein ursprünglicher Verweiszähler.  
  
## Hinweise  
 Byname\-Facets werden automatisch erstellt, wenn ein benanntes Gebietsschema erstellt wurde.  
  
 Das Verhalten wird durch das Gebietsschema benannte `_Locname` bestimmt.  Jeder Konstruktor initialisiert sein Basisobjekt mit [codecvt](../standard-library/codecvt-class.md)\<CharType, byte, StateType\>\(`_Refs`\).  
  
## Anforderungen  
 Gebietsschema **Header:** \<\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)