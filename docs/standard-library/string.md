---
title: "&lt;string&gt;"
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
  - "std::<string>"
  - "string/std::<string>"
  - "std.<string>"
  - "<string>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "string-Header"
ms.assetid: a2fb9d00-d7ae-4170-bfea-2dc337aa37cf
caps.latest.revision: 23
caps.handback.revision: "13"
ms.author: "corob"
manager: "ghogen"
---
# &lt;string&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Definiert die Containervorlagenklasse `basic_string` und verschiedene unterstützende Vorlagen.  
  
 Weitere Informationen zu `basic_string` finden Sie unter [basic\_string\-Klasse](../standard-library/basic-string-class.md).  
  
## Syntax  
  
```  
#include <string>  
```  
  
## Hinweise  
 Die Programmiersprache C\+\+ und die C\+\+\-Standardbibliothek unterstützen zwei Arten von Zeichenfolgen:  
  
-   Auf NULL endende Zeichenarrays werden häufig als C\-Zeichenfolgen bezeichnet.  
  
-   Vorlagenklassenobjekte des Typs `basic_string`, die alle `char`\-ähnlichen Vorlagenargumente verarbeiten.  
  
### Typedefs  
  
|||  
|-|-|  
|[string](../Topic/string%20\(C++%20STL%20%3Cstring%3E\).md)|Ein Typ, der eine Spezialisierung der Vorlagenklasse `basic_string` mit Elementen des Typs `char` als `string` beschreibt.|  
|[wstring](../Topic/wstring.md)|Ein Typ, der eine Spezialisierung der Vorlagenklasse `basic_string` mit Elementen des Typs `wchar_t` als `wstring` beschreibt.|  
|[u16string](../Topic/u16string.md)|Ein Typ, der eine Spezialisierung der Vorlagenklasse `basic_string` basierend auf Elementen des Typs `char16_t` beschreibt.|  
|[u32string](../Topic/u32string.md)|Ein Typ, der eine Spezialisierung der Vorlagenklasse `basic_string` basierend auf Elementen des Typs `char32_t` beschreibt.|  
  
### Operatoren  
  
|||  
|-|-|  
|[operator\+](../Topic/operator+%20\(%3Cstring%3E\).md)|Verkettet zwei Zeichenfolgenobjekte.|  
|[operator\!\=](../Topic/operator!=%20\(%3Cstring%3E\).md)|Testet, ob das Zeichenfolgenobjekt links vom Operator ungleich dem Zeichenfolgenobjekt rechts vom Operator ist.|  
|[operator\=\=](../Topic/operator==%20\(%3Cstring%3E\).md)|Testet, ob das Zeichenfolgenobjekt links vom Operator gleich dem Zeichenfolgenobjekt rechts vom Operator ist.|  
|[Operator \<](../Topic/operator%3C%20\(%3Cstring%3E\).md)|Testet, ob das Zeichenfolgenobjekt links vom Operator kleiner als das Zeichenfolgenobjekt rechts vom Operator ist.|  
|[Operator \<\=](../Topic/operator%3C=%20\(in%20%3Cstring%3E\).md)|Testet, ob das Zeichenfolgenobjekt links vom Operator kleiner als oder gleich dem Zeichenfolgenobjekt rechts vom Operator ist.|  
|[Operator \<\<](../Topic/operator%3C%3C%20\(%3Cstring%3E\).md)|Eine Vorlagenfunktion, die eine Zeichenfolge in den Ausgabestream einfügt.|  
|[Operator \>](../Topic/operator%3E%20\(%3Cstring%3E\).md)|Testet, ob das Zeichenfolgenobjekt links vom Operator größer als das Zeichenfolgenobjekt rechts vom Operator ist.|  
|[Operator \>\=](../Topic/operator%3E=%20\(%3Cstring%3E\).md)|Testet, ob das Zeichenfolgenobjekt links vom Operator größer als oder gleich dem Zeichenfolgenobjekt rechts vom Operator ist.|  
|[Operator \>\>](../Topic/operator%3E%3E%20\(%3Cstring%3E\).md)|Eine Vorlagenfunktion, die eine Zeichenfolge aus dem Eingabestream extrahiert.|  
  
### Spezialisierte Vorlagenfunktionen  
  
|||  
|-|-|  
|[swap](../Topic/swap%20\(C++%20STL%20%3Cstring%3E\).md)|Tauscht die Arrays von Zeichen für zwei Zeichenfolgen aus.|  
|[stod](../Topic/stod.md)|Konvertiert eine Zeichenfolge in ein `double.`.|  
|[stof](../Topic/stof.md)|Konvertiert eine Zeichenfolge in ein `float`.|  
|[stoi](../Topic/stoi.md)|Konvertiert eine Zeichenfolge in eine Ganzzahl.|  
|[stold](../Topic/stold.md)|Konvertiert eine Zeichenfolge in ein `long double`.|  
|[stoll](../Topic/stoll.md)|Konvertiert eine Zeichenfolge in ein `long long`.|  
|[stoul](../Topic/stoul.md)|Konvertiert eine Zeichenfolge in ein `unsigned long`.|  
|[stoull](../Topic/stoull.md)|Konvertiert eine Zeichenfolge in ein `unsigned long long`.|  
|[to\_string](../Topic/to_string.md)|Konvertiert einen Wert in einen `string`\-Wert.|  
|[to\_wstring](../Topic/to_wstring.md)|Konvertiert einen Wert in eine breite `string`.|  
  
### Funktionen  
  
|||  
|-|-|  
|[getline](../Topic/getline%20Template%20Function.md)|Extrahiert Zeichenfolgen aus dem Eingabestream zeilenweise.|  
  
### Klassen  
  
|||  
|-|-|  
|[basic\_string\-Klasse](../standard-library/basic-string-class.md)|Eine Vorlagenklasse, die Objekte beschreibt, die eine Sequenz von beliebigen zeichenartigen Objekten speichern können.|  
|[char\_traits\-Struktur](../standard-library/char-traits-struct.md)|Eine Vorlagenklasse, die Attribute beschreibt, die mit einem Zeichen des Typs "CharType" zugeordnet sind.|  
  
### Spezialisierungen  
  
|||  
|-|-|  
|[char\_traits\<char\>\-Struktur](../standard-library/char-traits-char-struct.md)|Eine Struktur, die eine Spezialisierung der Vorlagenstruktur `char_traits`\<CharType\> für ein Element des Typs `char` ist.|  
|[char\_traits\<wchar\_t\>\-Struktur](../standard-library/char-traits-wchar-t-struct.md)|Eine Struktur, die eine Spezialisierung der Vorlagenstruktur `char_traits`\<CharType\> für ein Element des Typs `wchar_t` ist.|  
|[char\_traits\<char16\_t\>\-Struktur](../standard-library/char-traits-char16-t-struct.md)|Eine Struktur, die eine Spezialisierung der Vorlagenstruktur `char_traits`\<CharType\> für ein Element des Typs `char16_t` ist.|  
|[char\_traits\<char32\_t\>\-Struktur](../standard-library/char-traits-char32-t-struct.md)|Eine Struktur, die eine Spezialisierung der Vorlagenstruktur `char_traits`\<CharType\> für ein Element des Typs `char32_t` ist.|  
  
## Anforderungen  
  
-   **Header:** \<string\>  
  
-   **Namespace:** std  
  
## Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)