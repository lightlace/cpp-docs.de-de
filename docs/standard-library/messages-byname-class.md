---
title: "messages_byname-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "messages_byname"
  - "std::messages_byname"
  - "std.messages_byname"
  - "xlocmes/std::messages_byname"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "messages_byname-Klasse"
ms.assetid: c6c64841-3e80-43c8-b54c-fed41833ad6b
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# messages_byname-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die abgeleitete Vorlagenklasse beschreibt ein Objekt, das als Meldungsfacet eines angegebenen Gebietsschemas dienen kann aktiviert und den Abruf von lokalisierten Meldungen.  
  
## Syntax  
  
```  
template<class CharType>  
    class messages_byname : public messages<CharType> {  
public:  
    explicit messages_byname(  
        const char *_Locname,  
        size_t _Refs = 0  
    );  
    explicit messages_byname(  
        const string& _Locname,  
        size_t _Refs = 0  
    );   
protected:  
    virtual ~messages_byname();  
};  
```  
  
#### Parameter  
 `_Locname`  
 Ein benanntes Gebietsschema.  
  
 `_Refs`  
 Ein ursprünglicher Verweiszähler.  
  
## Hinweise  
 Das Verhalten wird durch das Gebietsschema benannte `_Locname` bestimmt.  Jeder Konstruktor initialisiert sein Basisobjekt mit [Meldungen](../Topic/messages::messages.md)\<CharType\>\(`_Refs`\).  
  
## Anforderungen  
 Gebietsschema **Header:** \<\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)