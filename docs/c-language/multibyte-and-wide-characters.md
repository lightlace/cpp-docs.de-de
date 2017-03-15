---
title: "Mehrbyte- und Breitzeichen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Zeichencodes [C++], Mehrbyte"
  - "Zeichencodes [C++], Breit"
  - "Zeichendatentypen [C]"
  - "Zeichen [C++], Codes"
  - "Zeichen [C++], Breit"
  - "Globalisierung [C++], Zeichensätze"
  - "Internationale Anwendungen [C++], Zeichenanzeige"
  - "Mehrbytezeichen [C++]"
  - "Typen [C], Zeichen"
  - "Unicode [C++], Breitzeichensatz"
  - "Breitzeichen [C++]"
ms.assetid: 1943c469-200d-4724-b18f-781d70520f9e
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Mehrbyte- und Breitzeichen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein Mehrbytezeichen ist ein Zeichen, das aus einem oder mehreren Bytesequenzen besteht.  Jede Bytesequenz stellt ein einzelnes Zeichen im erweiterten Zeichensatz dar.  Mehrbytezeichen werden in Zeichensätzen wie Kanji verwendet.  
  
 Breitzeichen sind mehrsprachige Zeichencodes, deren Breite immer 16 Bit beträgt.  Der Typ für Zeichenkonstanten ist `char`. Der Typ ist für Breitzeichen ist `wchar_t`.  Da Breitzeichen stets eine feste Größe aufweisen, vereinfachen diese das Programmieren mit internationalen Zeichensätzen.  
  
 Das Breitzeichen\-Zeichenfolgenliteral `L"hello"` wird zu einem Array mit sechs Ganzzahlen vom Typ `wchar_t`.  
  
```  
{L'h', L'e', L'l', L'l', L'o', 0}  
```  
  
 Die Unicode\-Spezifikation entspricht der Spezifikation für Breitzeichen.  Die Laufzeitbibliotheksroutinen für Übersetzungen zwischen Multibyte\- und Breitzeichen enthalten `mbstowcs`, `mbtowc`, `wcstombs` und `wctomb`.  
  
## Siehe auch  
 [C\-Bezeichner](../c-language/c-identifiers.md)