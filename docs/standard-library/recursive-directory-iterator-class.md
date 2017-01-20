---
title: "recursive_directory_iterator-Klasse"
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
  - "filesystem/std::tr2::sys::recursive_directory_iterator"
dev_langs: 
  - "C++"
ms.assetid: 79a061bd-5b64-404c-97e8-749c888c2ced
caps.latest.revision: 15
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# recursive_directory_iterator-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beschreibt einen Eingabeiterator, der der Reihe nach die Dateinamen in einem Verzeichnis durchläuft und dabei möglicherweise rekursiv Unterverzeichnisse absteigend durchläuft. Für einen Iterator X wird der Ausdruck \*X zu einem directory\_entry\-Objekt ausgewertet, das den Dateinamen und alles umschließt, was zu dessen Status bekannt ist.  
  
 Weitere Informationen und Codebeispiele finden Sie unter [Dateisystemnavigation \(C\+\+\)](../standard-library/file-system-navigation.md).  
  
## Syntax  
  
```  
class recursive_directory_iterator;  
```  
  
## Hinweise  
 Die Vorlagenklasse speichert Folgendes:  
  
1.  ein Objekt des Typs „stack\<pair\<directory\_iterator, path\>\>“, das hier aus Gründen des Verfügbarmachens als „mystack“ bezeichnet wird und die Schachtelung von Verzeichnissen darstellt, die nacheinander durchlaufen werden sollen  
  
2.  ein Objekt des Typs „directory\_entry“, das hier als „myentry“ bezeichnet wird und den aktuellen Dateinamen in der Verzeichnissequenz darstellt  
  
3.  ein Objekt des Typs „bool“, das hier als „no\_push“ bezeichnet wird und festhält, ob rekursives Durchlaufen von Unterverzeichnissen deaktiviert ist  
  
4.  ein Objekt des Typs „directory\_options“, das hier als „myoptions“ bezeichnet wird und die Optionen festhält, die bei der Erstellung eingerichtet wurden  
  
 Ein standardmäßig erstelltes Objekt des Typs „recursive\_directory\_entry“ hat einen Sequenzende\-Iterator bei „mystack.top\(\).first“ und entspricht dem Sequenzende\-Iterator. Angenommen, es gibt das Verzeichnis „abc“ mit den Einträgen „def“ \(ein Verzeichnis\), „def\/ghi“ und „jkl“, dann wird im Code:  
  
```  
for (recursive_directory_iterator next(path("abc")), end; next != end; ++next)  
    visit(next->path());  
  
```  
  
 „visit“ mit den folgenden Argumenten aufgerufen: `path("abc/def/ghi") and path("abc/jkl").`Sie können absteigendes Durchlaufen einer Verzeichnisunterstruktur auf zwei Arten bestimmen:  
  
1.  Eine symbolische Verzeichnisverknüpfung \(Verzeichnis\-Symlink\) wird nur dann durchsucht, wenn Sie einen „recursive\_directory\_iterator“ mit einem directory\_options\-Argument erstellen, das den Wert „directory\_options::follow\_directory\_symlink“ hat.  
  
2.  Wenn Sie „disable\_recursion\_pending“ aufrufen, wird ein nachfolgendes Verzeichnis, das während eines Inkrements erkannt wird, nicht rekursiv durchsucht.  
  
## recursive\_directory\_iterator::depth  
  
```  
int depth() const;  
```  
  
 Gibt „mystack.size\(\) \- 1“ zurück, sodass „pval“ die Tiefe 0 \(null\) hat.  
  
## recursive\_directory\_iterator::disable\_recursion\_pending  
  
```  
void disable_recursion_pending();  
```  
  
 Die Memberfunktion speichert „true“ in „no\_push“.  
  
## recursive\_directory\_iterator::operator\!\=  
  
```  
bool operator!=(const recursive_directory_iterator& right) const;  
  
```  
  
 Der Memberoperator gibt „\!\(\*this \=\= right\)“ zurück.  
  
## recursive\_directory\_iterator::operator\=  
  
```  
recursive_directory_iterator& operator=(const recursive_directory_iterator&) = default;  
recursive_directory_iterator& operator=(recursive_directory_iterator&&) noexcept = default;  
  
```  
  
 Die als Standard \(default\) festgelegten Memberzuweisungsoperatoren verhalten sich wie erwartet.  
  
## recursive\_directory\_iterator::operator\=\=  
  
```  
bool operator==(const recursive_directory_iterator& right) const;  
```  
  
 Der Memberoperator gibt nur dann „true“ zurück, wenn sowohl „\*this“ als auch „right“ Sequenzende\-Iteratoren oder beide keine Sequenzende\-Iteratoren sind.  
  
## recursive\_directory\_iterator::operator\*  
  
```  
const directory_entry& operator*() const;  
  
```  
  
 Der Memberoperator gibt „myentry“ zurück.  
  
## recursive\_directory\_iterator::operator\-\>  
  
```  
const directory_entry *operator->() const;  
```  
  
 Gibt „&\*\*this“ zurück.  
  
## recursive\_directory\_iterator::operator\+\+  
  
```  
recursive_directory_iterator& operator++();  
recursive_directory_iterator& operator++(int);  
  
```  
  
 Die erste Memberfunktion ruft „increment\(\)“ auf und gibt dann „\*this“ zurück. Die zweite Memberfunktion erstellt eine Kopie des Objekts, ruft „increment\(\)“ auf und gibt dann die Kopie zurück.  
  
## recursive\_directory\_iterator::options  
  
```  
directory_options options() const;  
```  
  
 Gibt „myoptions“ zurück.  
  
## recursive\_directory\_iterator::pop  
  
```  
void pop();  
```  
  
 Ist „depth\(\) \=\= 0“, wird das Objekt ein Sequenzende\-Iterator. Andernfalls beendet die Memberfunktion das Durchsuchen des aktuellen \(tiefsten\) Verzeichnisses und setzt das Durchsuchen auf der nächstniedrigeren Tiefe fort.  
  
## recursive\_directory\_iterator::recursion\_pending  
  
```  
bool recursion_pending() const;  
```  
  
 Gibt „\!no\_push“ zurück.  
  
## recursive\_directory\_iterator::recursive\_directory\_iterator  
  
```  
recursive_directory_iterator() noexcept;  
explicit recursive_directory_iterator(const path& pval);  
recursive_directory_iterator(const path& pval,  
    error_code& ec) noexcept;  
recursive_directory_iterator(const path& pval,  
    directory_options opts);  
recursive_directory_iterator(const path& pval,  
    directory_options opts,  
    error_code& ec) noexcept;  
recursive_directory_iterator(const recursive_directory_iterator&) = default;  
recursive_directory_iterator(recursive_directory_iterator&&) noexcept = default;  
  
```  
  
 Der erste Konstruktor erzeugt einen Sequenzende\-Iterator. Der zweite und der dritte Konstruktoren speichern „false“ in „no\_push“ und „directory\_options::none“ in „myoptions“ und versuchen dann, „pval“ als Verzeichnis zu öffnen und zu lesen. Sind die Konstruktoren erfolgreich, initialisieren sie „mystack“ und „myentry“, um den ersten Nicht\-Verzeichnis\-Dateinamen in der geschachtelten Sequenz anzugeben. Andernfalls erstellen sie einen Sequenzende\-Iterator.  
  
 Der vierte und der fünfte Konstruktor verhalten sich so wie der zweite und der dritte mit dem Unterschied, dass sie zuerst „opts“ in „myoptions“ speichern. Die als Standard festgelegten Konstruktoren verhalten sich wie erwartet.  
  
## recursive\_directory\_iterator::increment  
  
```  
recursive_directory_iterator& increment(  
    error_code& ec) noexcept;  
```  
  
 Die Funktion versucht, zum nächsten Dateinamen in der geschachtelten Sequenz zu gelangen. Ist sie erfolgreich, speichert sie diesen Dateinamen in „myentry“. Andernfalls erstellt sie einen Sequenzende\-Iterator.  
  
## Anforderungen  
 **Header:** Dateisystem  
  
 **Namespace:** std::tr2::sys  
  
## Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [\<filesystem\>](../standard-library/filesystem.md)   
 [Dateisystemnavigation \(C\+\+\)](../standard-library/file-system-navigation.md)