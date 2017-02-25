---
title: "regex_error-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::tr1::regex_error"
  - "regex_error"
  - "std.tr1.regex_error"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "regex_error-Klasse [TR1]"
ms.assetid: 3333a1a3-ca6f-4612-84b2-1b4c7e3db5a4
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# regex_error-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Meldet ein ungültiges basic\_regex\-Objekt.  
  
## Syntax  
  
```  
class regex_error  
    : public std::runtime_error {  
public:  
    explicit regex_error(regex_constants::error_code error);  
    regex_constants::error_code code() const;  
    };  
```  
  
## Hinweise  
 Die Klasse beschreibt ein Ausnahmeobjekt, das ausgelöst wurde, um einen Fehler bei der Erstellung oder Verwendung eines `basic_regex`\-Objekts zu melden.  
  
## Anforderungen  
 **Header:** \<regex\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<regex\>](../standard-library/regex.md)   
 [regex\_error](../standard-library/regex-error-class.md)