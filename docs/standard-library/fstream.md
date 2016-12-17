---
title: "&lt;fstream&gt;"
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
  - "std::<fstream>"
  - "<fstream>"
  - "std.<fstream>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fstream-Header"
ms.assetid: 660de351-0489-41df-b239-40e0cdcab46b
caps.latest.revision: 19
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# &lt;fstream&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Definiert mehrere Klassen, die iostreams\-Vorgänge für Sequenzen unterstützen, die in externen Dateien gespeichert sind.  
  
## Syntax  
  
```  
  
#include <fstream>  
  
```  
  
### TypeDefs  
  
|||  
|-|-|  
|[filebuf](../Topic/filebuf.md)|Ein `basic_filebuf`\-Typ, der auf `char`\-Vorlagenparameter spezialisiert ist.|  
|[fstream](../Topic/fstream.md)|Ein `basic_fstream`\-Typ, der auf `char`\-Vorlagenparameter spezialisiert ist.|  
|[ifstream](../Topic/ifstream.md)|Ein `basic_ifstream`\-Typ, der auf `char`\-Vorlagenparameter spezialisiert ist.|  
|[ofstream](../Topic/ofstream.md)|Ein `basic_ofstream`\-Typ, der auf `char`\-Vorlagenparameter spezialisiert ist.|  
|[wfstream](../Topic/wfstream.md)|Ein `basic_fstream`\-Typ, der auf `wchar_t`\-Vorlagenparameter spezialisiert ist.|  
|[wifstream](../Topic/wifstream.md)|Ein `basic_ifstream`\-Typ, der auf `wchar_t`\-Vorlagenparameter spezialisiert ist.|  
|[wofstream](../Topic/wofstream.md)|Ein `basic_ofstream`\-Typ, der auf `wchar_t`\-Vorlagenparameter spezialisiert ist.|  
|[wfilebuf](../Topic/wfilebuf.md)|Ein `basic_filebuf`\-Typ, der auf `wchar_t`\-Vorlagenparameter spezialisiert ist.|  
  
### Klassen  
  
|||  
|-|-|  
|[basic\_filebuf](../standard-library/basic-filebuf-class.md)|Die Vorlagenklasse beschreibt einen Streampuffer, der steuert, wie Elemente des Typs **Elem**, dessen Zeichenmerkmale durch die Klasse **Tr** bestimmt sind, in eine oder aus einer Sequenz von Elementen übertragen werden, die in einer externen Datei gespeichert sind.|  
|[basic\_fstream](../standard-library/basic-fstream-class.md)|Die Vorlagenklasse beschreibt ein Objekt, das das Einfügen und Extrahieren von Elementen und codierten Objekten mit einem Streampuffer der Klasse [basic\_stringbuf](../standard-library/basic-filebuf-class.md)\<**Elem**, **Tr**\> mit Elementen des Typs **Elem** steuert, dessen Zeichenmerkmale durch die Klasse **Tr** bestimmt sind.|  
|[basic\_ifstream](../standard-library/basic-ifstream-class.md)|Die Vorlagenklasse beschreibt ein Objekt, das das Extrahieren von Elementen und codierten Objekten aus einem Streampuffer der Klasse [basic\_stringbuf](../standard-library/basic-filebuf-class.md)\<**Elem**, **Tr**\> mit Elementen des Typs **Elem** steuert, dessen Zeichenmerkmale durch die Klasse **Tr** bestimmt sind.|  
|[basic\_ofstream](../standard-library/basic-ofstream-class.md)|Die Vorlagenklasse beschreibt ein Objekt, das das Einfügen von Elementen und codierten Objekten in einen Streampuffer der Klasse [basic\_stringbuf](../standard-library/basic-filebuf-class.md)\<**Elem**, **Tr**\> mit Elementen des Typs **Elem** steuert, dessen Zeichenmerkmale durch die Klasse **Tr** bestimmt sind.|  
  
## Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream\-Programmierung](../standard-library/iostream-programming.md)   
 [iostreams\-Konventionen](../standard-library/iostreams-conventions.md)