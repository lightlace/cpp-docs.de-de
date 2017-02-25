---
title: "is_error_condition_enum-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::is_error_condition_enum"
  - "std.is_error_condition_enum"
  - "is_error_condition_enum"
  - "system_error/std::is_error_condition_enum"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_error_condition_enum-Klasse"
ms.assetid: 752bb87a-c61c-4304-9254-5aaf228b59c0
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# is_error_condition_enum-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Stellt ein Typprädikat dar, das zum [error\_condition](../standard-library/error-condition-class.md)\-Enumeration testet.  
  
## Syntax  
  
```  
template<_Enum>  
    class is_error_condition_enum;  
```  
  
## Hinweise  
 Eine Instanz von diesem [Typprädikat](../standard-library/type-traits.md) enthält true an, wenn der `_Enum`\-Typ ein Enumerationswert ist, der zum Speichern in einem Objekt des Typs `error_condition` geeignet ist.  
  
 Es ist zulässig, Spezialisierungen diesem Typ für benutzerdefinierte Typen hinzufügen.  
  
## Anforderungen  
 **Header:** \<system\_error\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [\<system\_error\>](../standard-library/system-error.md)