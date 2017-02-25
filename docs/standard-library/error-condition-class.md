---
title: "error_condition-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "system_error/std::error_condition"
  - "std::error_condition"
  - "error_condition"
  - "std.error_condition"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "error_condition-Klasse"
ms.assetid: 6690f481-97c9-4554-a0ff-851dc96b7a06
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# error_condition-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Stellt benutzerdefinierte Fehlercodes dar.  
  
## Syntax  
  
```  
class error_condition;  
```  
  
## Hinweise  
 Ein Objekt des Typs `error_condition` speichert eine Fehlercodecodierte darstellung und einen Zeiger auf ein Objekt, das das [Kategorie](../standard-library/error-category-class.md) von Fehlercodes darstellt, die für berichtete benutzerdefinierte Fehlermeldung verwendet werden.  
  
### Konstruktoren  
  
|||  
|-|-|  
|[error\_condition](../Topic/error_condition::error_condition.md)|Konstruiert ein Objekt vom Typ `error_condition`.|  
  
### Typedefs  
  
|||  
|-|-|  
|[value\_type](../Topic/error_condition::value_type.md)|Ein Typ, der die gespeicherten Fehlercodecodierte darstellung darstellt.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[assign](../Topic/error_condition::assign.md)|Weist eine Fehlercodecodierte darstellung und \-Kategorie einem Fehlerzustand zu.|  
|[Kategorie](../Topic/error_condition::category.md)|Gibt der Fehlerkategorie zurück.|  
|[clear](../Topic/error_condition::clear.md)|Löscht die Fehlercodecodierte darstellung und \-Kategorie.|  
|[message](../Topic/error_condition::message.md)|Gibt den Namen des Fehlercodes zurück.|  
  
### Operatoren  
  
|||  
|-|-|  
|[operator\=\=](../Topic/error_condition::operator==.md)|Tests für Gleichheit zwischen `error_condition`\-Objekten.|  
|[operator\!\=](../Topic/error_condition::operator!=.md)|Tests auf Ungleichheit zwischen `error_condition`\-Objekten.|  
|[Operator implementiert.\<](../Topic/error_condition::operator%3C.md)|Testet, ob das `error_condition`\-Objekt weniger ist, als das `error_code`\-Objekt übergeben für den Vergleich.|  
|[operator\=](../Topic/error_condition::operator=.md)|Weist einen neuen Enumerationswert zum `error_condition`\-Objekt zu.|  
|[Operator bool](../Topic/error_condition::operator%20bool.md)|Wandelt eine Variable des Typs `error_condition` um.|  
  
## Anforderungen  
 **Header:** \<system\_error\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [error\_category\-Klasse](../standard-library/error-category-class.md)   
 [\<system\_error\>](../standard-library/system-error.md)