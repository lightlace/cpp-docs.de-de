---
title: "directory_iterator-Klasse. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "filesystem/std::tr2::sys::directory_iterator"
  - "directory_iterator"
  - "filesystem/std::experimental::filesystem::v1::_Directory_iterator::_Directory_iterator"
  - "filesystem/std::experimental::filesystem::v1::directory_iterator"
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_iterator::directory_iterator"
  - "std::experimental::filesystem::v1::directory_iterator::directory_iterator"
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_iterator::increment"
  - "std::experimental::filesystem::v1::directory_iterator::increment"
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_iterator::operator="
  - "std::experimental::filesystem::v1::directory_iterator::operator="
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_iterator::operator=="
  - "std::experimental::filesystem::v1::directory_iterator::operator=="
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_iterator::operator!="
  - "std::experimental::filesystem::v1::directory_iterator::operator!="
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_iterator::operator*"
  - "std::experimental::filesystem::v1::directory_iterator::operator*"
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_iterator::operator->"
  - "std::experimental::filesystem::v1::directory_iterator::operator->"
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_iterator::operator++"
  - "std::experimental::filesystem::v1::directory_iterator::operator++"
dev_langs: 
  - "C++"
ms.assetid: dca2ecf8-3e69-4644-a83d-705061e10cc8
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# directory_iterator-Klasse.
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beschreibt einen Eingabeiterator, der alle Dateinamen in einem Verzeichnis durchläuft. Für einen Iterator „X“ wird der Ausdruck „\*X“ zu einem „directory\_entry“\-Objekt ausgewertet, das den Dateinamen und alles umschließt, was zu dessen Status bekannt ist.  
  
 Die Klasse speichert ein Objekt des Typs „path“, das hier zur Veranschaulichung den Namen „mydir“ erhält, der den Namen des zu sequenzierenden Verzeichnisses darstellt, und ein Objekt des Typs „directory\_entry“, das hier als „myentry“ bezeichnet wird und den aktuellen Dateinamen in der Verzeichnissequenz darstellt. Ein standardmäßig erstelltes Objekt des Typs „directory\_entry“ verfügt über einen leeren „mydir“\-Pfadnamen und stellt den Sequenzende\-Iterator dar.  
  
 Für das Verzeichnis „abc“ mit den Einträgen „def“ und „ghi“ würde der Code:  
  
 `for (directory_iterator next(path("abc")), end; next != end; ++next)     visit(next->path());`  
  
 z. B. „visit“ mit den Argumenten „path\("abc\/def"\)“ und „path\("abc\/ghi"\)“ aufrufen.  
  
 Weitere Informationen und Codebeispiele finden Sie unter [Dateisystemnavigation \(C\+\+\)](../standard-library/file-system-navigation.md).  
  
## Syntax  
  
```  
class directory_iterator;  
```  
  
## directory\_iterator::directory\_iterator  
  
```cpp  
directory_iterator() noexcept;  
explicit directory_iterator(const path& pval);  
directory_iterator(const path& pval,  
    error_code& ec) noexcept;  
directory_iterator(const directory_iterator&) = default;  
directory_iterator(directory_iterator&&) noexcept = default;  
```  
  
 Der erste Konstruktor erzeugt einen Sequenzende\-Iterator. Die zweiten und dritten Konstruktoren speichern „pval“ in „mydir“ und versuchen dann, „mydir“ zu öffnen und als Verzeichnis zu lesen. Bei Erfolg speichern sie den ersten Dateinamen im Verzeichnis in „myentry“. Andernfalls erzeugen sie einen Sequenzende\-Iterator.  
  
 Die als Standard festgelegten Konstruktoren verhalten sich wie erwartet.  
  
## directory\_iterator::increment  
  
```cpp  
directory_iterator& increment(  
    error_code& ec) noexcept;  
```  
  
 Die Funktion versucht, zum nächsten Dateinamen im Verzeichnis zu gelangen. Ist sie erfolgreich, speichert sie diesen Dateinamen in „myentry“. Andernfalls erstellt sie einen Sequenzende\-Iterator.  
  
## directory\_iterator::operator\!\=  
  
```cpp  
bool operator!=(const directory_iterator& right) const;  
```  
  
 Der Memberoperator gibt „\!\(\*this \=\= right\)“ zurück.  
  
## directory\_iterator::operator\=  
  
```cpp  
directory_iterator& operator=(const directory_iterator&) = default;  
directory_iterator& operator=(directory_iterator&&) noexcept = default;  
```  
  
 Die als Standard festgelegten Memberzuweisungsoperatoren verhalten sich wie erwartet.  
  
## directory\_iterator::operator\=\=  
  
```cpp  
bool operator==(const directory_iterator& right) const;  
  
```  
  
 Der Memberoperator gibt nur dann „true“ zurück, wenn sowohl „\*this“ als auch „right“ Sequenzende\-Iteratoren oder beide keine Sequenzende\-Iteratoren sind.  
  
## directory\_iterator::operator\*  
  
```cpp  
const directory_entry& operator*() const;  
```  
  
 Der Memberoperator gibt „myentry“ zurück.  
  
## directory\_iterator::operator\-\>  
  
```cpp  
const directory_entry *operator->() const;  
```  
  
 Die Memberfunktion gibt „&\*\*this“ zurück.  
  
## directory\_iterator::operator\+\+  
  
```cpp  
directory_iterator& operator++();  
directory_iterator& operator++(int);  
```  
  
 Die erste Memberfunktion ruft „increment\(\)“ auf und gibt dann „\*this“ zurück. Die zweite Memberfunktion erstellt eine Kopie des Objekts, ruft „increment\(\)“ auf und gibt dann die Kopie zurück.  
  
## Anforderungen  
 **Header:** Dateisystem  
  
 **Namespace:** std::experimental::filesystem::v1  
  
## Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [\<filesystem\>](../standard-library/filesystem.md)   
 [Dateisystemnavigation \(C\+\+\)](../standard-library/file-system-navigation.md)