---
title: "#error-Direktive (C/C++)"
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
  - "#error"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "#error-Direktive"
  - "error-Direktive (#error directive)"
  - "Präprozessor, Direktiven"
ms.assetid: d550a802-ff19-4347-9597-688935d23b2b
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# #error-Direktive (C/C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die `#error`\-Direktive gibt eine benutzerdefinierte Fehlermeldung zur Kompilierzeit aus und beendet dann die Kompilierung.  
  
## Syntax  
  
```  
#error token-string  
```  
  
## Hinweise  
 Die Fehlermeldung, die diese Direktive ausgibt, umfasst den *token\-string*\-Parameter.  Der `token-string`\-Parameter unterliegt nicht der Makroerweiterung.  Diese Direktive ist während der Vorverarbeitung am hilfreichsten, denn sie informiert den Entwickler über eine Programminkonsistenz oder einen Verstoß gegen eine Einschränkung.  Das folgende Beispiel zeigt die Fehlerverarbeitung während der Vorverarbeitung:  
  
```  
#if !defined(__cplusplus)  
#error C++ compiler required.  
#endif  
```  
  
## Siehe auch  
 [Präprozessordirektiven](../preprocessor/preprocessor-directives.md)