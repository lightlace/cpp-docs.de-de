---
title: "&lt;filesystem&gt;-Operatoren"
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
  - "FILESYSTEM/std::experimental::filesystem::v1::operator=="
  - "std::experimental::filesystem::v1::operator=="
  - "FILESYSTEM/std::experimental::filesystem::v1::operator!="
  - "std::experimental::filesystem::v1::operator!="
  - "FILESYSTEM/std::experimental::filesystem::v1::operator<"
  - "std::experimental::filesystem::v1::operator<"
  - "FILESYSTEM/std::experimental::filesystem::v1::operator<="
  - "std::experimental::filesystem::v1::operator<="
  - "FILESYSTEM/std::experimental::filesystem::v1::operator>"
  - "std::experimental::filesystem::v1::operator>"
  - "FILESYSTEM/std::experimental::filesystem::v1::operator>="
  - "std::experimental::filesystem::v1::operator>="
  - "FILESYSTEM/std::experimental::filesystem::v1::operator/"
  - "std::experimental::filesystem::v1::operator/"
  - "FILESYSTEM/std::experimental::filesystem::v1::operator<<"
  - "std::experimental::filesystem::v1::operator<<"
  - "FILESYSTEM/std::experimental::filesystem::v1::operator>>"
  - "std::experimental::filesystem::v1::operator>>"
dev_langs: 
  - "C++"
ms.assetid: 102c4833-aa3b-41a8-8998-f5003c546bfd
caps.latest.revision: 12
caps.handback.revision: "3"
ms.author: "corob"
manager: "ghogen"
---
# &lt;filesystem&gt;-Operatoren
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Operatoren führen einen lexikalischen Vergleich von zwei Pfaden als Zeichenfolgen aus. Verwenden Sie die **equivalent**\-Funktion, um zu bestimmen, ob zwei Pfade \(beispielsweise ein relativer Pfad und ein absoluter Pfad\) auf dieselbe Datei oder dasselbe Verzeichnis auf dem Datenträger verweisen.  
  
```  
C:\root > D:\root: false  
C:\root > C:\root\sub: false  
C:\root > C:\roo: true  
  
```  
  
 Weitere Informationen finden Sie unter [Dateisystemnavigation \(C\+\+\)](../standard-library/file-system-navigation.md).  
  
## operator\=\=  
  
```  
bool operator==(const path& left, const path& right) noexcept;  
```  
  
 Die Funktion gibt „left.native\(\) \=\= right.native\(\)“ zurück.  
  
## Operator\!\=  
  
```  
bool operator!=(const path& left, const path& right) noexcept;  
```  
  
 Die Funktion gibt „\!\(left \=\= right\)“ zurück.  
  
## Operator \<  
  
```  
bool operator<(const path& left, const path& right) noexcept;  
```  
  
 Die Funktion gibt „left.native\(\) \< right.native\(\)“ zurück.  
  
## Operator \<\=  
  
```  
bool operator<=(const path& left, const path& right) noexcept;  
```  
  
 Die Funktion gibt „\!\(right \< left\)“ zurück.  
  
## Operator \>  
  
```  
bool operator>(const path& left, const path& right) noexcept;  
```  
  
 Die Funktion gibt „right \< left“ zurück.  
  
## Operator \>\=  
  
```  
bool operator>=(const path& left, const path& right) noexcept;  
```  
  
 Die Funktion gibt „\!\(left \< right\)“ zurück.  
  
## operator\/  
  
```  
path operator/(const path& left, const path& right);  
```  
  
 Die Funktion führt Folgendes aus:  
  
```  
basic_string<Elem, Traits> str;  
path ans = left;  
return (ans /= right);  
  
```  
  
## Operator \<\<  
  
```  
template<class Elem, class Traits>    basic_ostream<Elem, Traits>&    operator<<(basic_ostream<Elem, Traits>& os, const path& pval);  
```  
  
 Die Funktion gibt „os \<\< pval.string\<Elem, Traits\>\(\)“ zurück.  
  
## Operator \>\>  
  
```  
template<class Elem, class Traits>    basic_istream<Elem, Traits>&    operator<<(basic_istream<Elem, Traits>& is, const path& pval);  
```  
  
 Die Funktion führt Folgendes aus:  
  
```  
basic_string<Elem, Traits> str;  
is >> str;  
pval = str;  
return (is);  
  
```  
  
## operator\=\=  
  
```  
bool operator==(const path& left, const path& right) noexcept;  
```  
  
 Die Funktion gibt „left.native\(\) \=\= right.native\(\)“ zurück.  
  
## Siehe auch  
 [path\-Klasse \(C\+\+\-Standardvorlagenbibliothek\)](../standard-library/path-class-cpp-standard-template-library.md)   
 [Dateisystemnavigation \(C\+\+\)](../standard-library/file-system-navigation.md)   
 [\<filesystem\>](../standard-library/filesystem.md)