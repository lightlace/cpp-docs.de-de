---
title: "Unicode: Der Breitzeichensatz | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.international"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Unicode [C++], Breitzeichensatz"
  - "Breitzeichen [C++], Unicode"
ms.assetid: b6a05a21-59a5-4d30-8c85-2dbe185f7a74
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Unicode: Der Breitzeichensatz
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Bei einem Breitzeichen handelt es sich um einen mehrsprachigen Zeichencode mit zwei Bytes.  Jedes Zeichen in Verwendung im modernen Computertechnik weltweit, einschließlich technischer Symbole und spezielle Veröffentlichungszeichen, kann entsprechend der Unicode\-Spezifikation als Breitzeichen dargestellt werden.  Sich entwickelt und durch ein großes Konsortium verwaltet, das Microsoft beinhaltet, wurde der Unicode\-Standard jetzt weit akzeptiert.  
  
 Bei einem Breitzeichen ist vom Typ `wchar_t`.  Eine Zeichenfolge mit Breitzeichen wird als `wchar_t[]` Array dargestellt und auf von einem Zeiger `wchar_t*` gezeigt.  Sie können jedes ASCII\-Zeichens als Breitzeichen darstellen, indem Sie die Buchstaben `L` auf Zeichen voranstellen.  Beispielsweise ist L"\\0" ist schließende breite \(16\-Bit\) `NULL` Zeichen.  Sie können auch jedes beliebige ASCII\-Zeichenfolgenliteral als Breitzeichen\-Zeichenfolgenliteral einfach darstellen, indem Sie der Buchstabe L dem ASCII\-Literal voranstellen \(L " Hello"\).  
  
 Im Allgemeinen nehmen Breitzeichen auf mehr Speicherplatz als Mehrbytezeichen, können jedoch schneller verarbeitet werden.  Darüber hinaus kann bei Mehrbytecodierung nur jeweils ein Gebietsschema dargestellt werden; Unicode ermöglicht dagegen die gleichzeitige Darstellung sämtlicher internationaler Zeichensätze.  
  
## Siehe auch  
 [Internationalisierung](../c-runtime-library/internationalization.md)   
 [Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)