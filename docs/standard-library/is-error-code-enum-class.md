---
title: "is_error_code_enum-Klasse"
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
  - "system_error/std::is_error_code_enum"
  - "std.is_error_code_enum"
  - "is_error_code_enum"
  - "std::is_error_code_enum"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_error_code_enum-Klasse"
ms.assetid: cee5be2d-7c20-4cec-a352-1ab8b7d32601
caps.latest.revision: 15
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# is_error_code_enum-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Stellt ein Typprädikat dar, das zum [error\_code](../standard-library/error-code-class.md)\-Enumeration testet.  
  
## Syntax  
  
```  
template<_Enum>  
    class is_error_code_enum;  
```  
  
## Hinweise  
 Eine Instanz von diesem [Typprädikat](../standard-library/type-traits.md) enthält true an, wenn der `_Enum`\-Typ ein Enumerationswert ist, der zum Speichern in einem Objekt des Typs `error_code` geeignet ist.  
  
 Es ist zulässig, Spezialisierungen diesem Typ für benutzerdefinierte Typen hinzufügen.  
  
## Anforderungen  
 **Header:** \<system\_error\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [\<system\_error\>](../standard-library/system-error.md)