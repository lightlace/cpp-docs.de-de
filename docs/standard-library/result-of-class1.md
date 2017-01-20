---
title: "result_of-Klasse"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "result_of"
  - "std.result_of"
  - "std::result_of"
  - "type_traits/std::result_of"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "result_of"
ms.assetid: 5374a096-4b4a-4712-aa97-6852c5cdd6be
caps.latest.revision: 13
caps.handback.revision: "3"
ms.author: "corob"
manager: "ghogen"
---
# result_of-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Bestimmt den Rückgabetyp des Typs aufgerufen werden kann, die die angegebenen Argumenttypen akzeptiert.  
  
## Syntax  
  
```  
template <class Fn, class... ArgTypes>  
    struct result_of<Fn(ArgTypes...)>;  
```  
  
#### Parameter  
 `Fn`  
 Der abzufragende Typ aufgerufen werden kann.  
  
 `ArgTypes`  
 Die Typen der Argumentliste in den aufrufbaren Typ Abfrage.  
  
## Hinweise  
 Verwenden Sie diese Vorlage zum Zeitpunkt der Kompilierung bestimmen den Ergebnistyp des `Fn`\(`ArgTypes`\), wobei `Fn` eines aufrufbaren Typs aufgerufen wird, mit der Typen in einer Argumentliste ist `ArgTypes`. Die `type` der Vorlagenklasse Membernamen der Ergebnistyp des `decltype(INVOKE(declval<Fn>(), declval<ArgTypes>()...))` Wenn der ausgewertete Ausdruck `INVOKE(declval<Fn>(), declval<ArgTypes>()...)` wohlgeformt ist. Andernfalls hat die Vorlagenklasse kein Member `type`. Der Typ `Fn` und alle Typen im parameterpaket `ArgTypes` vollständige Typen sein `void`, oder Arrays von unbekannten gebunden.  
  
## Anforderungen  
 **Header:** \<type\_traits\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<type\_traits\>](../standard-library/type-traits.md)