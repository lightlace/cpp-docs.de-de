---
title: "raw_storage_iterator-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::raw_storage_iterator"
  - "raw_storage_iterator"
  - "std.raw_storage_iterator"
  - "memory/std::raw_storage_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "raw_storage_iterator-Klasse"
ms.assetid: 6f033f15-f48e-452a-a326-647ea2cf346f
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# raw_storage_iterator-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Adapterklasse, die bereitgestellt wird, um Algorithmen das Speichern ihrer Ergebnisse in nicht initialisiertem Speicher zu ermöglichen.  
  
## Syntax  
  
```  
  
        template <class   
        OutputIterator,  
         class   
        Type>  
class raw_storage_iterator  
```  
  
#### Parameter  
 `OutputIterator`  
 Gibt den Ausgabeiterator für das Objekt an, das gespeichert wird.  
  
 *Typ*  
 Der Typ des Objekts, dem Speicher zugeordnet wird.  
  
## Hinweise  
 Die Klasse beschreibt einen Ausgabeiterator, der Objekte des Typs **Type** in der Sequenz erstellt, die von ihm generiert wird.  Ein aus der Klasse `raw_storage_iterator`\<**ForwardIterator**, **Type**\> abgeleitetes Objekt greift über ein Vorwärtsiteratorobjekt \(Klasse **ForwardIterator**\), das Sie beim Erstellen des Objekts angegeben haben, auf Speicher zu.  Für ein first\-Objekt der Klasse **ForwardIterator** muss der Ausdruck **&\*first** nicht erstellten Speicher für das nächste Objekt \(des Typs **Type**\) in der generierten Sequenz bestimmen.  
  
 Diese Adapterklasse wird verwendet, wenn es erforderlich ist, Speicherbelegung und Objekterstellung zu trennen.  `raw_storage_iterator` kann verwendet werden, um Objekte in nicht initialisierten Speicher zu kopieren, beispielsweise Arbeitsspeicher, der über die `malloc`\-Funktion zugeordnet wurde.  
  
## Member  
  
### Konstruktoren  
  
|||  
|-|-|  
|[raw\_storage\_iterator](../Topic/raw_storage_iterator::raw_storage_iterator.md)|Erstellt einen unformatierten Speicheriterator mit einem angegebenen zugrunde liegenden Ausgabeiterator.|  
  
### TypeDefs  
  
|||  
|-|-|  
|[element\_type](../Topic/raw_storage_iterator::element_type.md)|Stellt einen Typ bereit, der ein Element beschreibt, das in einem unformatierten Speicheriterator gespeichert werden soll.|  
|[iter\_type](../Topic/raw_storage_iterator::iter_type.md)|Stellt einen Typ bereit, der einen Iterator beschreibt, der einem unformatierten Speicheriterator zugrunde liegt.|  
  
### Operatoren  
  
|||  
|-|-|  
|[operator\*](../Topic/raw_storage_iterator::operator*.md)|Ein Dereferenzierungsoperator, der zum Implementieren des Ausgabeiteratorausdrucks \*`ii` \= `x` verwendet wird.|  
|[operator \=](../Topic/raw_storage_iterator::operator=.md)|Ein Zuweisungsoperator, der dazu verwendet wird, den für einen unformatierten Speicheriterator verwendeten Ausdruck \*`i`\=`x` zu implementieren, damit er im Arbeitsspeicher gespeichert werden kann.|  
|[operator\+\+](../Topic/raw_storage_iterator::operator++.md)|Inkrementoperatoren in Präfix\- und Postfix\-Notation für unformatierte Speicheriteratoren.|  
  
## Anforderungen  
 **Header:** \<memory\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)