---
title: "iostreams-Konventionen"
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
helpviewer_keywords: 
  - "iostream-Header"
  - "C++-Standardbibliothek, iostreams"
ms.assetid: 9fe5ded0-37a1-48d1-9671-c81ffc4760ad
caps.latest.revision: 10
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# iostreams-Konventionen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die iostreams Header unterstützen Konvertierungen zwischen Text und codierten Formularen, und die Eingabe und Ausgabe auf externe Dateien:  
  
|||  
|-|-|  
|[\<fstream\>](../standard-library/fstream.md)|[\< Iomanip \>](../standard-library/iomanip.md)|  
|[\<ios\>](../standard-library/ios.md)|[\<iosfwd\>](../standard-library/iosfwd.md)|  
|[\<iostream\>](../standard-library/iostream.md)|[\< Istream \>](../standard-library/istream.md)|  
|[\<ostream\>](../standard-library/ostream.md)|[\<sstream\>](../standard-library/sstream.md)|  
|[\< Streambuf \>](../standard-library/streambuf.md)|[\<strstream\>](../standard-library/strstream.md)|  
  
 Der einfachste Verwendung von iostreams nur erforderlich, dass Sie die Header\- [\<iostream\>](../standard-library/iostream.md) enthalten.  Sie können Werte von [cin](../Topic/cin.md) oder [wcin](../Topic/wcin.md) dann extrahieren, um die Standardeingabe zu lesen.  Die Regeln hierfür werden in der Beschreibung der [basic\_istream\-Klasse](../standard-library/basic-istream-class.md) erläutert.  Sie können Werte von [cout](../Topic/cout.md) oder [wcout](../Topic/wcout.md) auch einfügen, um die Standardausgabe zu schreiben.  Die Regeln hierfür werden in der Beschreibung der [basic\_ostream\-Klasse](../standard-library/basic-ostream-class.md) erläutert.  Formatsteuercommon beiden Extraktionsprogrammen und insertors wird von der Klasse [basic\_ios\-Klasse](../standard-library/basic-ios-class.md).  Diese Formatinformationen unter dem Mantel des Extrahierens und Einfügen von Objekten werden bearbeitet die Provinz von Manipulatoren.  
  
 Sie können die gleichen iostreams Vorgänge für Dateien, die Sie mit Namen öffnen, mit Klassen ausführen, die in [\<fstream\>](../standard-library/fstream.md) deklariert werden.  Um zwischen iostreams und Objekte der Klasse [basic\_string\-Klasse](../standard-library/basic-string-class.md) zu konvertieren, verwenden Sie die Klassen, die in [\<sstream\>](../standard-library/sstream.md) deklariert werden.  Um identisch mit C\-Zeichenfolgen auszuführen, verwenden Sie die Klassen, die in [\<strstream\>](../standard-library/strstream.md) deklariert werden.  
  
 Die verbleibenden Header stellen Die Supportangebote, normalerweise des direkten relevanten nur zu den höchstentwickelten Benutzer der iostreams Klassen bereit.  
  
## Siehe auch  
 [STL\-Übersicht](../standard-library/cpp-standard-library-overview.md)   
 [iostream\-Programmierung](../standard-library/iostream-programming.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)