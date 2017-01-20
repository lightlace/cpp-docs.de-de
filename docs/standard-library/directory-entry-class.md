---
title: "directory_entry-Klasse"
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
  - "filesystem/std::tr2::sys::directory_entry"
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::operator const std::experimental::filesystem::v1::path &"
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::directory_entry"
  - "std::experimental::filesystem::v1::directory_entry::directory_entry"
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::operator="
  - "std::experimental::filesystem::v1::directory_entry::operator="
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::assign"
  - "std::experimental::filesystem::v1::directory_entry::assign"
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::replace_filename"
  - "std::experimental::filesystem::v1::directory_entry::replace_filename"
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::path"
  - "std::experimental::filesystem::v1::directory_entry::path"
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::status"
  - "std::experimental::filesystem::v1::directory_entry::status"
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::symlink_status"
  - "std::experimental::filesystem::v1::directory_entry::symlink_status"
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::operator<"
  - "std::experimental::filesystem::v1::directory_entry::operator<"
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::operator=="
  - "std::experimental::filesystem::v1::directory_entry::operator=="
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::operator!="
  - "std::experimental::filesystem::v1::directory_entry::operator!="
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::operator<="
  - "std::experimental::filesystem::v1::directory_entry::operator<="
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::operator>"
  - "std::experimental::filesystem::v1::directory_entry::operator>"
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::operator>="
  - "std::experimental::filesystem::v1::directory_entry::operator>="
dev_langs: 
  - "C++"
ms.assetid: 1827c67b-4137-4548-adb0-f955f7acaf08
caps.latest.revision: 17
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# directory_entry-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beschreibt ein Objekt, das durch `*X` zurückgegeben wird, wobei *X* ist ein [directory\_iterator](../standard-library/directory-iterator-class.md) oder ein [recursive\_directory\_iterator](../standard-library/recursive-directory-iterator-class.md) ist.  
  
## Syntax  
  
```  
class directory_entry;  
```  
  
## Hinweise  
 Die Klasse speichert ein Objekt des Typs [path Class](../standard-library/path-class-cpp-standard-template-library.md).`path` kann entweder ein [path](../standard-library/path-class-cpp-standard-template-library.md) oder ein Typ sein, der von `path` abgeleitet wird. Sie speichert zudem zwei [file\_type](../Topic/file_type%20Enumeration.md)\-Werte. Einer davon repräsentiert das, was über den Status des gespeicherten Dateinamens bekannt ist. Der andere repräsentiert das, was über den symbolischen Linkstatus des Dateinamens bekannt ist.  
  
 Weitere Informationen und Codebeispiele finden Sie unter [Dateisystemnavigation \(C\+\+\)](../standard-library/file-system-navigation.md).  
  
## assign  
  
```  
void assign(const PFX path& pval,  
    file_status stat_arg = file_status(),  
    file_status symstat_arg = file_status());  
```  
  
 Die Memberfunktion weist „pval“ zu „mypath“, „stat“ zu „mystat“ und „symstat“ zu „mysymstat“ zu.  
  
## directory\_entry  
  
```  
directory_entry() = default;  
directory_entry(const directory_entry&) = default;  
directory_entry(directory_entry&&) noexcept = default;  
explicit directory_entry(const PFX path& pval,  
    file_status stat_arg = file_status(),  
    file_status symstat_arg = file_status());  
```  
  
 Die als Standard festgelegten Konstruktoren verhalten sich wie erwartet. Der vierte Konstruktor initialisiert „mypath“ für „pval“, „mystat“ für „stat\_arg“ und „mysymstat“ für „symstat\_arg“.  
  
## Operator\!\=  
  
```  
bool operator!=(const directory_entry& right) const noexcept;  
  
```  
  
 Die Memberfunktion gibt „\!\(\*this \=\= right\)“ zurück.  
  
## operator \=  
  
```  
directory_entry& operator=(const directory_entry&) = default;  
directory_entry& operator=(directory_entry&&) noexcept = default;  
  
```  
  
 Die als Standard festgelegten Memberzuweisungsoperatoren verhalten sich wie erwartet.  
  
## operator\=\=  
  
```  
bool operator==(const directory_entry& right) const noexcept;  
```  
  
 Die Memberfunktion gibt „mypath \=\= right.mypath“ zurück.  
  
## Operator \<  
  
```  
  
bool operator<(const directory_entry& right) const noexcept;  
  
```  
  
 Die Memberfunktion gibt „mypath \< right.mypath“ zurück.  
  
## Operator \<\=  
  
```  
bool operator<=(const directory_entry& right) const noexcept;  
```  
  
 Die Memberfunktion gibt „\!\(right \< \*this\)“ zurück.  
  
## Operator \>  
  
```  
bool operator>(const directory_entry& right) const noexcept;  
```  
  
 Die Memberfunktion gibt „right \< \*this“ zurück.  
  
## Operator \>\=  
  
```  
bool operator>=(const directory_entry& right) const noexcept;  
  
```  
  
 Die Memberfunktion gibt „\!\(\*this \< right\)“ zurück.  
  
## operator const path\_type&  
  
```  
operator const path&() const; // retained  
```  
  
 Der Memberoperator gibt „mypath“ zurück.  
  
## path  
  
```  
const PFX path& path() const noexcept;  
```  
  
 Die Memberfunktion gibt „mypath“ zurück.  
  
## replace\_filename  
  
```  
void replace_filename(const PFX path& pval,  
    file_status stat_arg = file_status(),  
    file_status symstat_arg = file_status());  
```  
  
 Die Memberfunktion ersetzt „mypath“ durch „mypath.parent\_path\(\) \/ pval“, „mystat“ durch „stat\_arg“ und „mysymstat“ durch „symstat\_arg“.  
  
## Status  
  
```  
file_status status() const;  
file_status status(  
    error_code& ec) const noexcept;  
Otherwise, mystat = status(mypval).  
  
```  
  
 Beide Memberfunktionen geben „mystat“ möglicherweise zunächst wie folgt geändert zurück:  
  
1.  Bei „status\_known\(mystat\)“ keinen weiteren Schritt ausführen.  
  
2.  Andernfalls gilt bei „\!status\_known\(mysymstat\) && \!is\_symlink\(mysymstat\)“ dann „mystat \= mysymstat“.  
  
## symlink\_status  
  
```  
file_status symlink_status() const;  
file_status symlink_status(  
    error_code& ec) const noexcept;  
```  
  
 Beide Memberfunktionen geben „mysymstat“ möglicherweise zunächst wie folgt geändert zurück: Bei „status\_known\(mysymstat\)“ keinen weiteren Schritt ausführen. Andernfalls gilt „mysymstat \= symlink\_status\(mypval\)“.  
  
## Anforderungen  
 **Header:** filesystem  
  
 **Namespace:** std::tr2::sys  
  
## Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [\<filesystem\>](../standard-library/filesystem.md)