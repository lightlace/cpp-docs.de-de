---
title: "messages-Klasse"
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
  - "messages"
  - "xlocmes/std::messages"
  - "std.messages"
  - "std::messages"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "messages-Klasse"
ms.assetid: c4c71f40-4f24-48ab-9f7c-daccd8d5bd83
caps.latest.revision: 18
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# messages-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Vorlagenklasse beschreibt ein Objekt, das als Gebietsschemafacet dienen kann, um lokalisierte Meldungen aus einem Katalog von internationalisierten Meldungen für ein bestimmtes Gebietsschema abzurufen.  
  
 Während die Nachrichtenklasse implementiert wird, sind derzeit keine Meldungen vorhanden.  
  
## Syntax  
  
```  
template <class CharType>  
   class messages : public messages_base;  
```  
  
#### Parameter  
 `CharType`  
 Der Typ, der innerhalb eines Programms zum Codieren von Zeichen in einem Gebietsschema verwendet wird.  
  
## Hinweise  
 Wie bei jedem Gebietsschemafacet hat die statische Objekt\-ID einen anfänglichen gespeicherten Wert von NULL. Beim erste Versuch, den gespeicherten Wert zuzugreifen speichert einen eindeutigen positiven Wert in **ID**  
  
 Dieses Facet öffnet im Grunde einen Katalog von Meldungen, die in der messages\_base\-Basisklasse definiert sind, ruft die erforderlichen Informationen ab und schließt den Katalog.  
  
### Konstruktoren  
  
|||  
|-|-|  
|[Meldungen](../Topic/messages::messages.md)|Die Meldungsfacet\-Konstruktorfunktion.|  
  
### TypeDefs  
  
|||  
|-|-|  
|[char\_type](../Topic/messages::char_type.md)|Ein Zeichentyp, mit dem Meldungen angezeigt werden.|  
|[string\_type](../Topic/messages::string_type.md)|Ein Typ, der eine Zeichenfolge vom Typ `basic_string` beschreibt, die Zeichen vom Typ `CharType` enthält.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[schließen](../Topic/messages::close.md)|Schließt den Meldungskatalog.|  
|[do\_close](../Topic/messages::do_close.md)|Eine virtuelle Funktion, die aufgerufen wird, um den Meldungskatalog zu schließen.|  
|[do\_get](../Topic/messages::do_get.md)|Eine virtuelle Funktion, die aufgerufen wird, um den Meldungskatalog abzurufen.|  
|[do\_open](../Topic/messages::do_open.md)|Eine virtuelle Funktion, die aufgerufen wird, um den Meldungskatalog zu öffnen.|  
|[Abrufen](../Topic/messages::get.md)|Ruft den Meldungskatalog ab.|  
|[open](../Topic/messages::open.md)|Öffnet den Meldungskatalog.|  
  
## Anforderungen  
 **Header:** \<Gebietsschema\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<locale\>](../standard-library/locale.md)   
 [messages\_base\-Klasse](../standard-library/messages-base-class.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)