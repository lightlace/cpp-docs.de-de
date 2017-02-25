---
title: "error_category-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::error_category"
  - "system_error/std::error_category"
  - "error_category"
  - "std.error_category"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "error_category-Klasse"
ms.assetid: e0a71e14-852d-4905-acd6-5f8ed426706d
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# error_category-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Stellt die abstrakte, allgemeine Basis für Objekte, die eine Kategorie von Fehlercodes beschreibt.  
  
## Syntax  
  
```  
class error_category;  
```  
  
## Hinweise  
 Implementieren Sie zwei vordefinierte Objekte `error_category`: [generic\_category](../Topic/generic_category.md) und [system\_category](../Topic/system_category.md).  
  
### TypeDefs  
  
|||  
|-|-|  
|[value\_type](../Topic/error_category::value_type.md)|Ein Typ, der Wert, der den gespeicherten Fehler darstellt.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[default\_error\_condition](../Topic/error_category::default_error_condition.md)|Speichert den Wert des Fehler\-Code für eine Bedingung Fehlerobjekt.|  
|[equivalent](../Topic/error_category::equivalent.md)|Gibt einen Wert, der angibt, ob Fehlerobjekte gleich sind.|  
|[message](../Topic/error_category::message.md)|Gibt den Namen des angegebenen Fehlercodes.|  
|[Name](../Topic/error_category::name.md)|Gibt den Namen der Kategorie.|  
  
### Operatoren  
  
|||  
|-|-|  
|[operator\=\=](../Topic/error_category::operator==.md)|Gleichheit zwischen `error_category` Objekte.|  
|[Operator\!\=](../Topic/error_category::operator!=.md)|Prüft auf Ungleichheit zwischen `error_category` Objekte.|  
|[Operator \<](../Topic/error_category::operator%3C.md)|Testet, ob die [Error\_category](../standard-library/error-category-class.md) Objekt ist kleiner als der `error_category` Objekt für den Vergleich übergeben.|  
  
## Anforderungen  
 **Header:** \<system\_error\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<system\_error\>](../standard-library/system-error.md)