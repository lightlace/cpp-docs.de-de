---
title: "collate-Klasse"
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
  - "std::collate"
  - "locale/std::collate"
  - "std.collate"
  - "collate"
  - "Collate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "collate-Klasse"
ms.assetid: 92168798-9628-4a2e-be6e-fa62dcd4d6a6
caps.latest.revision: 18
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# collate-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Vorlagenklasse, die ein Objekt beschreibt, das als Gebietsschemafacet dienen kann, um die Reihenfolge und Gruppierung der Zeichen in einer Zeichenfolge, Vergleiche zwischen ihnen und das Hashing von Zeichenfolgen zu steuern.  
  
## Syntax  
  
```  
template <class CharType >  
   class collate : public locale::facet;  
```  
  
#### Parameter  
 `CharType`  
 Der Typ, der innerhalb eines Programms verwendet wird, um Zeichen zu codieren.  
  
## Hinweise  
 Wie bei jedem Gebietsschemafacet hat die statische Objekt\-ID einen anfänglichen gespeicherten Wert von NULL.  Beim ersten Versuch, auf den gespeicherten Wert zuzugreifen, wird ein eindeutiger positiver Wert in **ID** gespeichert. In einigen Sprachen werden Zeichen gruppiert und als einzelnes Zeichen behandelt. In anderen Sprachen hingegen werden einzelne Zeichen als zwei Zeichen behandelt.  Die sortierenden Dienste, die von der collate\-Klasse bereitgestellt werden, bieten die Möglichkeit zum Sortieren dieser Fälle.  
  
### Konstruktoren  
  
|||  
|-|-|  
|[collate](../Topic/collate::collate.md)|Der Konstruktor für Objekte der `collate`\-Klasse, die als Gebietsschemafacet dient, um Zeichenfolgensortierungskonventionen zu bearbeiten.|  
  
### Typedefs  
  
|||  
|-|-|  
|[char\_type](../Topic/collate::char_type.md)|Ein Typ, der ein Zeichen vom Typ `CharType` beschreibt.|  
|[string\_type](../Topic/collate::string_type.md)|Ein Typ, der eine Zeichenfolge vom Typ `basic_string` beschreibt, die Zeichen vom Typ `CharType` enthält.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[compare](../Topic/collate::compare.md)|Vergleicht zwei Zeichensequenzen nach ihren facetspezifischen Regeln für Gleichheit oder Ungleichheit.|  
|[do\_compare](../Topic/collate::do_compare.md)|Eine virtuelle Funktion, die aufgerufen wird, um zwei Zeichensequenzen gemäß ihren facetspezifischen Regeln in Bezug auf Gleichheit oder Ungleichheit zu vergleichen.|  
|[do\_hash](../Topic/collate::do_hash.md)|Eine virtuelle Funktion, die aufgerufen wird, um den Hashwert der Sequenzen anhand der facetspezifischen Regeln zu bestimmen.|  
|[do\_transform](../Topic/collate::do_transform.md)|Eine virtuelle Funktion, die aufgerufen wird, um eine Zeichenfolge aus einem Gebietsschema in eine Zeichenfolge zu konvertieren, die in den lexikografischen Vergleichen mit anderen Zeichensequenzen verwendet werden kann, die auf ähnliche Weise aus demselben Gebietsschema konvertiert wurden.|  
|[hash](../Topic/collate::hash.md)|Bestimmt den Hashwert der Sequenz nach ihren facetspezifischen Regeln.|  
|[Transformation](../Topic/collate::transform.md)|Konvertiert eine Zeichenfolge von einem Gebietsschema in eine Zeichenfolge, die in den lexikografischen Vergleichen mit anderen Zeichenfolgen verwendet wird, die auf ähnliche Weise aus dem gleichen Gebietsschema konvertiert wurden.|  
  
## Anforderungen  
 **Header:** \<Gebietsschema\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<locale\>](../standard-library/locale.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)