---
title: "Eingabe-/Ausgabestreams | Microsoft Docs"
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
  - "E/A [C++], Stream"
  - "Stream-E/A"
ms.assetid: 21a97566-91a7-42d6-b2f8-a4c16bc926f1
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Eingabe-/Ausgabestreams
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`basic_iostream`, das im istream \>Headerdatei \<definiert ist, ist die Klassenvorlage für Objekte, die Eingabe und Ausgabe zeichenbasierte E\/A\-Streams behandeln.  
  
 Es gibt zwei Typdefinitionen, die Zeichenbesonderespezialisierungen von `basic_iostream` definieren und helfen, Code verständlicher zu gestalten: `iostream` \(nicht mit dem Headerdatei \<iostream\-Bibliothek\>verwechselt werden darf\) ist ein E\/A\-Stream, der auf `basic_iostream<char>` basiert; `wiostream` ist ein E\/A\-Stream, der auf `basic_iostream<wchar_t>` basiert.  
  
 Weitere Informationen finden Sie unter [basic\_iostream\-Klasse](../standard-library/basic-iostream-class.md), [iostream](../Topic/iostream.md) und [wiostream](../Topic/wiostream.md).  
  
 Die Ableitung von `basic_iostream` ist die Klassenvorlage `basic_fstream`, die verwendet wird, um Textdaten nach und Dateien zu übertragen.  
  
 Es gibt auch Typdefinitionen, die Zeichenbesonderespezialisierungen von `basic_fstream` bereitstellen.  Sie sind `fstream`, das ein Datei\-E\/A\-Stream ist, der auf `char` basiert, und `wfstream`, das ein Datei\-E\/A\-Stream ist, der auf `wchar_t` basiert.  Weitere Informationen finden Sie unter [basic\_fstream\-Klasse](../standard-library/basic-fstream-class.md), [fstream](../Topic/fstream.md) und [wfstream](../Topic/wfstream.md).  Verwenden dieser Typdefinitionen erfordert die Verwendung des fstream \>Headerdatei \<.  
  
> [!NOTE]
>  Wenn ein `basic_fstream`\-Objekt verwendet wird, um Datei\-E\/A auszuführen, obwohl der zugrunde liegende Puffer separat die Positionen für das Lesen und Schreiben enthält, werden typisierte und aktuelle Ausgabepositionen des aktuellen und daher zusammen gebunden und lesen einigen sich Daten die Ausgabeposition.  
  
 Die Klassenvorlage `basic_stringstream` und dessen allgemeine Spezialisierung, `stringstream`, werden häufig verwendet, mit E\/A\-Streamobjekten zu arbeiten, um Textdaten einzufügen und zu extrahieren.  Weitere Informationen finden Sie unter [basic\_stringstream\-Klasse](../standard-library/basic-stringstream-class.md).  
  
## Siehe auch  
 [stringstream](../Topic/stringstream.md)   
 [basic\_stringstream\-Klasse](../standard-library/basic-stringstream-class.md)   
 [\<sstream\>](../standard-library/sstream.md)   
 [iostream\-Programmierung](../standard-library/iostream-programming.md)   
 [C\+\+\-Standardbibliothek](../standard-library/cpp-standard-library-reference.md)