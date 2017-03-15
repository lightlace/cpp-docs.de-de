---
title: "ctype_byname-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "xlocale/std::ctype_byname"
  - "std::ctype_byname"
  - "ctype_byname"
  - "std.ctype_byname"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ctype_byname-Klasse"
ms.assetid: a5cec021-a1f8-425f-8757-08e6f064b604
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# ctype_byname-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die abgeleitete Vorlagenklasse beschreibt ein Objekt, das als Cfacet eines angegebenen Gebietsschemas dienen kann und die Klassifizierung von Zeichen aktivieren und Konvertierung von Zeichen zwischen Groß\-\/Kleinschreibung und systemeigene und Gebietsschema angegebene Zeichensätze.  
  
## Syntax  
  
```  
template<class _Elem>  
class ctype_byname : public ctype<_Elem>  
{  
public:  
    explicit ctype_byname(  
        const char *_Locname,  
        size_t _Refs = 0  
    );  
    explicit ctype_byname(  
        const string& _Locname,  
        size_t _Refs = 0  
    );  
protected:  
    virtual __CLR_OR_THIS_CALL ~ctype_byname();  
};  
```  
  
## Hinweise  
 Das Verhalten wird durch das Gebietsschema benannte `_Locname` bestimmt.  Jeder Konstruktor initialisiert sein Basisobjekt mit [C](../standard-library/ctype-class.md)\<CharType\>\(`_Refs`\) oder die Entsprechung für Basisklasse `ctype<char>`.  
  
## Anforderungen  
 Gebietsschema **Header:** \<\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)