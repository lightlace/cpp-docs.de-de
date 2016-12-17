---
title: "Compiler-Grenzen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cl.exe-Compiler, Grenzen für verschiedene Sprachkonstrukte"
ms.assetid: f1fa59c6-55b4-414b-80c5-3df72952160d
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Compiler-Grenzen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der C\+\+\-Standard empfiehlt Grenzen für verschiedene Sprachkonstrukte.  Es folgt eine Liste von Fällen, bei denen der Visual C\+\+\-Compiler keine empfohlenen Limits implementiert.  Die erste Nummer ist das im ISO C\+\+ 11\-Standard \(INCITS\/ISO\/IEC 14882\-2011\[2012\], Anhang B\) definierte Limit, und die zweite Nummer ist das von Visual C\+\+ implementierte Limit:  
  
-   Schachtelungsebenen von Verbundanweisungen, Iterationssteuerungsstrukturen und Auswahlsteuerungsstrukturen \[C\+\+\-Standard: 256\] \(Visual C\+\+\-Compiler: abhängig von der Kombination der geschachtelten Anweisungen, typischerweise jedoch zwischen 100 und 110\).  
  
-   Parameter in einer Makrodefinition \[C\+\+\-Standard: 256\] \(Visual C\+\+\-Compiler: 127\).  
  
-   Argumente in einer Makrodefinition \[C\+\+\-Standard: 256\] \(Visual C\+\+\-Compiler 127\).  
  
-   Zeichen in einem Zeichenfolgenliteral oder in einem breiten Zeichenfolgenliteral \(nach Verkettung\) \[C\+\+\-Standard: 65536\] \(Visual C\+\+\-Compiler: 65535 Einzelbytezeichen inklusive des `null`\-Abschlusszeichens, und 32767 Doppelbytezeichen inklusive des `null`\-Abschlusszeichens\).  
  
-   Ebenen geschachtelter Klassen\-, Struktur\- oder Union\-Definitionen in einer einzelnen `struct-declaration-list` \[C\+\+\-Standard: 256\] \(Visual C\+\+\-Compiler: 16\).  
  
-   Memberinitialisierer in einer Konstruktordefinition \[C\+\+\-Standard: 6144\] \(Visual C\+\+\-Compiler: mindestens 6144\).  
  
-   Bereichsqualifikationen eines einzigen Bezeichners \[C\+\+\-Standard: 256\] \(Visual C\+\+\-Compiler: 127\).  
  
-   Geschachtelte `extern`\-Spezifikationen \[C\+\+\-Standard: 1024\] \(Visual C\+\+\-Compiler: 9 \(ohne die explizite `extern`\-Spezifikation im globalen Bereich, oder 10 inklusive der expliziten `extern`\-Spezifikation im globalen Bereich.\).  
  
-   Vorlagenargumente in einer Vorlagendeklaration \[C\+\+\-Standard: 1024\] \(Visual C\+\+\-Compiler: 2046\).  
  
## Siehe auch  
 [Nicht dem Standard entsprechendes Verhalten](../cpp/nonstandard-behavior.md)