---
title: "error_code-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "error_code"
  - "std.error_code"
  - "std::error_code"
  - "system_error/std::error_code"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "error_code-Klasse"
ms.assetid: c09b4a96-cb14-4281-a319-63543f9b2b4a
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# error_code-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Stellt Systemfehler auf niedriger Ebene dar, die implementierungsabhängig sind.  
  
## Syntax  
  
```  
class error_code;  
```  
  
## Hinweise  
 Ein Objekt vom Typ `error_code`\-Klasse speichert eine Fehlercodecodierte darstellung und einen Zeiger auf ein Objekt, das das [Kategorie](../standard-library/error-category-class.md) von Fehlercodes, die darstellt gemeldete Systemfehler auf niedriger Ebene beschreiben.  
  
### Konstruktoren  
  
|||  
|-|-|  
|[error\_code](../Topic/error_code::error_code.md)|Konstruiert ein Objekt vom Typ `error_code`.|  
  
### Typedefs  
  
|||  
|-|-|  
|[value\_type](../Topic/error_code::value_type.md)|Ein Typ, der die gespeicherten Fehlercodecodierte darstellung darstellt.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[assign](../Topic/error_code::assign.md)|Weist eine Fehlercodecodierte darstellung und \-Kategorie einem Fehlercode zu.|  
|[Kategorie](../Topic/error_code::category.md)|Gibt der Fehlerkategorie zurück.|  
|[clear](../Topic/error_code::clear.md)|Löscht die Fehlercodecodierte darstellung und \-Kategorie.|  
|[default\_error\_condition](../Topic/error_code::default_error_condition.md)|Gibt den Standardfehlerzustand zurück.|  
|[message](../Topic/error_code::message.md)|Gibt den Namen des Fehlercodes zurück.|  
  
### Operatoren  
  
|||  
|-|-|  
|[operator\=\=](../Topic/error_code::operator==.md)|Tests für Gleichheit zwischen `error_code`\-Objekten.|  
|[operator\!\=](../Topic/error_code::operator!=.md)|Tests auf Ungleichheit zwischen `error_code`\-Objekten.|  
|[Operator implementiert.\<](../Topic/error_code::operator%3C.md)|Testet, ob das `error_code`\-Objekt weniger ist, als das `error_code`\-Objekt übergeben für den Vergleich.|  
|[operator\=](../Topic/error_code::operator=.md)|Weist einen neuen Enumerationswert zum `error_code`\-Objekt zu.|  
|[Operator bool](../Topic/error_code::operator%20bool.md)|Wandelt eine Variable des Typs `error_code` um.|  
  
## Anforderungen  
 **Header:** \<system\_error\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [error\_category\-Klasse](../standard-library/error-category-class.md)   
 [\<system\_error\>](../standard-library/system-error.md)