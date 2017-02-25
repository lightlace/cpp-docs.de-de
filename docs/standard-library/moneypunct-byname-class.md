---
title: "moneypunct_byname-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.moneypunct_byname"
  - "std::moneypunct_byname"
  - "xlocmon/std::moneypunct_byname"
  - "moneypunct_byname"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "moneypunct_byname-Klasse"
ms.assetid: e8a544d2-6aee-420d-b513-deb385c9b416
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# moneypunct_byname-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine abgeleitete Vorlagenklasse, die ein Objekt beschrieben wird, das als `moneypunct` Aspekt eines angegebenen Gebietsschemas verwendet werden kann und das Formatierungswährungseingabefeld oder Währungsdie ausgabefelder aktivieren.  
  
## Syntax  
  
```  
template<class CharType, bool Intl = false>  
class moneypunct_byname : public moneypunct<CharType, Intl>  
{  
public:  
    explicit moneypunct_byname(  
        const char *_Locname,  
        size_t _Refs = 0  
    );  
    explicit moneypunct_byname(  
        const string& _Locname,  
        size_t _Refs = 0  
    );   
protected:  
    virtual ~moneypunct_byname();  
};  
```  
  
## Hinweise  
 Das Verhalten wird durch das Gebietsschema benannte `_Locname` bestimmt.  Jeder Konstruktor initialisiert sein Basisobjekt mit [moneypunct](../Topic/moneypunct::moneypunct.md)\<CharType, international\>\(`_Refs`\).  
  
## Anforderungen  
 Gebietsschema **Header:** \<\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)