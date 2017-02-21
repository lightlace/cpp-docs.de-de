---
title: "is_error_code_enum-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
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
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
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