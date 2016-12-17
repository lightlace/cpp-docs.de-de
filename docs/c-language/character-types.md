---
title: "Zeichentypen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Zeichendatentypen [C]"
  - "Typen [C], Zeichen"
ms.assetid: d3ca8cda-c0d7-43af-9472-697e8ef015ce
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Zeichentypen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine ganzzahlige Zeichenkonstante, der nicht der Buchstabe **L** vorangestellt ist, ist vom Typ `int`.  Der Wert einer ganzzahligen Zeichenkonstante, die ein einzelnes Zeichen enthält, ist der numerische Wert des Zeichens, das als ganze Zahl interpretiert wird.  Beispielsweise ist der numerische Wert des Zeichens `a` 97 in dezimalen und 61 in hexadezimalen Zahlen.  
  
 Syntaktisch ist eine "Breitzeichenkonstante" eine Zeichenkonstante, der der Buchstabe **L** vorangestellt ist.  Eine Breitzeichenkonstante hat den Typ `wchar_t`, ein ganzzahliger Typ, der in der STDDEF.H\-Headerdatei definiert ist.  Beispiel:  
  
```  
char    schar =  'x';   /* A character constant          */  
wchar_t wchar = L'x';   /* A wide-character constant for   
                            the same character           */  
```  
  
 Breitzeichenkonstanten sind 16 Bit breit und geben Member des erweiterten Ausführungszeichensatzes an.  Sie ermöglichen es, Zeichen in Alphabeten auszudrücken, die zu groß sind, um durch den Typ `char` dargestellt zu werden.  Weitere Informationen über Breitzeichen erhalten Sie unter [Multibyte and Wide Characters](../c-language/multibyte-and-wide-characters.md).  
  
## Siehe auch  
 [C\-Zeichenkonstanten](../c-language/c-character-constants.md)