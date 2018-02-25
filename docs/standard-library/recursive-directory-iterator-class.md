---
title: recursive_directory_iterator-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- filesystem/std::tr2::sys::recursive_directory_iterator
dev_langs:
- C++
ms.assetid: 79a061bd-5b64-404c-97e8-749c888c2ced
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c432cde8a4c565e6195658ab27ce5f2cb1838f6a
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="recursivedirectoryiterator-class"></a>recursive_directory_iterator-Klasse
Beschreibt einen Eingabeiterator, der der Reihe nach die Dateinamen in einem Verzeichnis durchläuft und dabei möglicherweise rekursiv Unterverzeichnisse absteigend durchläuft. Für einen Iterator X wird der Ausdruck *X zu einem directory_entry-Objekt ausgewertet, das den Dateinamen und alles umschließt, was zu dessen Status bekannt ist.  
  
 Weitere Informationen und Codebeispiele finden Sie unter [Dateisystemnavigation (C++)](../standard-library/file-system-navigation.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
class recursive_directory_iterator;  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Vorlagenklasse speichert Folgendes:  
  
1.  ein Objekt des Typs „stack<pair\<directory_iterator, path>>“, das hier aus Gründen des Verfügbarmachens als „mystack“ bezeichnet wird, stellt die Schachtelung von Verzeichnissen dar, die nacheinander durchlaufen werden sollen  
  
2.  ein Objekt des Typs „directory_entry“, das hier als „myentry“ bezeichnet wird und den aktuellen Dateinamen in der Verzeichnissequenz darstellt  
  
3.  ein Objekt des Typs „bool“, das hier als „no_push“ bezeichnet wird und festhält, ob rekursives Durchlaufen von Unterverzeichnissen deaktiviert ist  
  
4.  ein Objekt des Typs „directory_options“, das hier als „myoptions“ bezeichnet wird und die Optionen festhält, die bei der Erstellung eingerichtet wurden  
  
 Ein standardmäßig erstelltes Objekt des Typs „recursive_directory_entry“ hat einen Sequenzende-Iterator bei „mystack.top().first“ und entspricht dem Sequenzende-Iterator. Angenommen, es gibt das Verzeichnis „abc“ mit den Einträgen „def“ (ein Verzeichnis), „def/ghi“ und „jkl“, dann wird im Code:  
  
```  
for (recursive_directory_iterator next(path("abc")), end; next != end; ++next)  
    visit(next->path());
```  
  
 „visit“ mit den folgenden Argumenten aufgerufen: `path("abc/def/ghi") and path("abc/jkl").`Sie können absteigendes Durchlaufen einer Verzeichnisunterstruktur auf zwei Arten bestimmen:  
  
1.  Eine symbolische Verzeichnisverknüpfung (Verzeichnis-Symlink) wird nur dann durchsucht, wenn Sie einen „recursive_directory_iterator“ mit einem directory_options-Argument erstellen, das den Wert „directory_options::follow_directory_symlink“ hat.  
  
2.  Wenn Sie „disable_recursion_pending“ aufrufen, wird ein nachfolgendes Verzeichnis, das während eines Inkrements erkannt wird, nicht rekursiv durchsucht.  
  
## <a name="recursivedirectoryiteratordepth"></a>recursive_directory_iterator::depth  
  
```  
int depth() const;
```  
  
 Gibt „mystack.size() - 1“ zurück, sodass „pval“ die Tiefe 0 (null) hat.  
  
## <a name="recursivedirectoryiteratordisablerecursionpending"></a>recursive_directory_iterator::disable_recursion_pending  
  
```  
void disable_recursion_pending();
```  
  
 Die Memberfunktion speichert „true“ in „no_push“.  
  
## <a name="recursivedirectoryiteratoroperator"></a>recursive_directory_iterator::operator!=  
  
```  
bool operator!=(const recursive_directory_iterator& right) const;
```  
  
 Der Memberoperator gibt „!(*this == right)“ zurück.  
  
## <a name="recursivedirectoryiteratoroperator"></a>recursive_directory_iterator::operator=  
  
```  
recursive_directory_iterator& operator=(const recursive_directory_iterator&) = default;  
recursive_directory_iterator& operator=(recursive_directory_iterator&&) noexcept = default;  
```  
  
 Die als Standard (default) festgelegten Memberzuweisungsoperatoren verhalten sich wie erwartet.  
  
## <a name="recursivedirectoryiteratoroperator"></a>recursive_directory_iterator::operator==  
  
```  
bool operator==(const recursive_directory_iterator& right) const;
```  
  
 Der Memberoperator gibt nur dann „true“ zurück, wenn sowohl „*this“ als auch „right“ Sequenzende-Iteratoren oder beide keine Sequenzende-Iteratoren sind.  
  
## <a name="recursivedirectoryiteratoroperator"></a>recursive_directory_iterator::operator*  
  
```  
const directory_entry& operator*() const;
```  
  
 Der Memberoperator gibt „myentry“ zurück.  
  
## <a name="recursivedirectoryiteratoroperator-"></a>recursive_directory_iterator::operator->  
  
```  
const directory_entry * operator->() const;
```  
  
 Gibt „&**this“ zurück.  
  
## <a name="recursivedirectoryiteratoroperator"></a>recursive_directory_iterator::operator++  
  
```  
recursive_directory_iterator& operator++();

recursive_directory_iterator& operator++(int);
```  
  
 Die erste Memberfunktion ruft „increment()“ auf und gibt dann „*this“ zurück. Die zweite Memberfunktion erstellt eine Kopie des Objekts, ruft „increment()“ auf und gibt dann die Kopie zurück.  
  
## <a name="recursivedirectoryiteratoroptions"></a>recursive_directory_iterator::options  
  
```  
directory_options options() const;
```  
  
 Gibt „myoptions“ zurück.  
  
## <a name="recursivedirectoryiteratorpop"></a>recursive_directory_iterator::pop  
  
```  
void pop();
```  
  
 Ist „depth() == 0“, wird das Objekt ein Sequenzende-Iterator. Andernfalls beendet die Memberfunktion das Durchsuchen des aktuellen (tiefsten) Verzeichnisses und setzt das Durchsuchen auf der nächstniedrigeren Tiefe fort.  
  
## <a name="recursivedirectoryiteratorrecursionpending"></a>recursive_directory_iterator::recursion_pending  
  
```  
bool recursion_pending() const;
```  
  
 Gibt „!no_push“ zurück.  
  
## <a name="recursivedirectoryiteratorrecursivedirectoryiterator"></a>recursive_directory_iterator::recursive_directory_iterator  
  
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
  
 Der erste Konstruktor erzeugt einen Sequenzende-Iterator. Der zweite und der dritte Konstruktoren speichern „false“ in „no_push“ und „directory_options::none“ in „myoptions“ und versuchen dann, „pval“ als Verzeichnis zu öffnen und zu lesen. Sind die Konstruktoren erfolgreich, initialisieren sie „mystack“ und „myentry“, um den ersten Nicht-Verzeichnis-Dateinamen in der geschachtelten Sequenz anzugeben. Andernfalls erstellen sie einen Sequenzende-Iterator.  
  
 Der vierte und der fünfte Konstruktor verhalten sich so wie der zweite und der dritte mit dem Unterschied, dass sie zuerst „opts“ in „myoptions“ speichern. Die als Standard festgelegten Konstruktoren verhalten sich wie erwartet.  
  
## <a name="recursivedirectoryiteratorincrement"></a>recursive_directory_iterator::increment  
  
```  
recursive_directory_iterator& increment(error_code& ec) noexcept;  
```  
  
 Die Funktion versucht, zum nächsten Dateinamen in der geschachtelten Sequenz zu gelangen. Ist sie erfolgreich, speichert sie diesen Dateinamen in „myentry“. Andernfalls erstellt sie einen Sequenzende-Iterator.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<filesystem>  
  
 **Namespace:** std::tr2::sys  
  
## <a name="see-also"></a>Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [\<filesystem>](../standard-library/filesystem.md)   
 [Dateisystemnavigation (C++)](../standard-library/file-system-navigation.md)

