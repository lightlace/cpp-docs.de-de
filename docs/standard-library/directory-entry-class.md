---
title: directory_entry-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- filesystem/std::experimental::filesystem::directory_entry
- FILESYSTEM/std::experimental::filesystem::directory_entry::operator const std::experimental::filesystem::path &
- FILESYSTEM/std::experimental::filesystem::directory_entry::directory_entry
- FILESYSTEM/std::experimental::filesystem::directory_entry::operator=
- FILESYSTEM/std::experimental::filesystem::directory_entry::assign
- FILESYSTEM/std::experimental::filesystem::directory_entry::replace_filename
- FILESYSTEM/std::experimental::filesystem::directory_entry::path
- FILESYSTEM/std::experimental::filesystem::directory_entry::status
- FILESYSTEM/std::experimental::filesystem::directory_entry::symlink_status
- FILESYSTEM/std::experimental::filesystem::directory_entry::operator<
- FILESYSTEM/std::experimental::filesystem::directory_entry::operator==
- FILESYSTEM/std::experimental::filesystem::directory_entry::operator!=
- FILESYSTEM/std::experimental::filesystem::directory_entry::operator<=
- FILESYSTEM/std::experimental::filesystem::directory_entry::operator>
- FILESYSTEM/std::experimental::filesystem::directory_entry::operator>=
dev_langs:
- C++
ms.assetid: 1827c67b-4137-4548-adb0-f955f7acaf08
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 0bd6b73c99eccffc7661cc4b43f97ab46890c5ee
ms.contentlocale: de-de
ms.lasthandoff: 04/29/2017

---
# <a name="directoryentry-class"></a>directory_entry-Klasse
Beschreibt ein Objekt, das durch `*X` zurückgegeben wird, wobei *X* ein [directory_iterator](../standard-library/directory-iterator-class.md) oder ein [recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md) ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
class directory_entry;  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Klasse speichert ein Objekt vom Typ [path](../standard-library/path-class.md). Bei dem gespeicherten `path`-Objekt kann es sich um eine Instanz der [path-Klasse](../standard-library/path-class.md) oder um einen von `path` abgeleiteten Typ handeln. Die Klasse speichert zudem zwei [file_type](../standard-library/filesystem-enumerations.md#file_type)-Werte. Einer davon repräsentiert das, was über den Status des gespeicherten Dateinamens bekannt ist. Der andere repräsentiert das, was über den symbolischen Linkstatus des Dateinamens bekannt ist.  
  
 Weitere Informationen und Codebeispiele finden Sie unter [File System Navigation (C++) (Dateisystemnavigation (C++))](../standard-library/file-system-navigation.md).  
  
## <a name="assign"></a>assign  
  
```  
void assign(const std::experimental::filesystem::path& pval,  
    file_status stat_arg = file_status(),  
    file_status symstat_arg = file_status());
```  
  
 Die Memberfunktion weist „pval“ zu „mypath“, „stat“ zu „mystat“ und „symstat“ zu „mysymstat“ zu.  
  
## <a name="directoryentry"></a>directory_entry  
  
```  
directory_entry() = default;  
directory_entry(const directory_entry&) = default;  
directory_entry(directory_entry&&) noexcept = default;  
explicit directory_entry(const std::experimental::filesystem::path& pval,  
    file_status stat_arg = file_status(),  
    file_status symstat_arg = file_status());
```  
  
 Die als Standard festgelegten Konstruktoren verhalten sich wie erwartet. Der vierte Konstruktor initialisiert „mypath“ für „pval“, „mystat“ für „stat_arg“ und „mysymstat“ für „symstat_arg“.  
  
## <a name="operator"></a>Operator!=  
  
```  
bool operator!=(const directory_entry& right) const noexcept;  
```  
  
 Die Memberfunktion gibt „!(*this == right)“ zurück.  
  
## <a name="operator"></a>operator =  
  
```  
directory_entry& operator=(const directory_entry&) = default;  
directory_entry& operator=(directory_entry&&) noexcept = default;  
```  
  
 Die als Standard festgelegten Memberzuweisungsoperatoren verhalten sich wie erwartet.  
  
## <a name="operator"></a>operator==  
  
```  
bool operator==(const directory_entry& right) const noexcept;  
```  
  
 Die Memberfunktion gibt „mypath == right.mypath“ zurück.  
  
## <a name="operator"></a>Operator <  
  
```  
 
bool operator<(const directory_entry& right) const noexcept;  
```  
  
 Die Memberfunktion gibt „mypath < right.mypath“ zurück.  
  
## <a name="operator"></a>Operator <=  
  
```  
bool operator<=(const directory_entry& right) const noexcept;  
```  
  
 Die Memberfunktion gibt „!(right \< *this)“ zurück.  
  
## <a name="operator"></a>Operator >  
  
```  
bool operator>(const directory_entry& right) const noexcept;  
```  
  
 Die Memberfunktion gibt „right \< *this“ zurück.  
  
## <a name="operator"></a>Operator >=  
  
```  
bool operator>=(const directory_entry& right) const noexcept;  
```  
  
 Die Memberfunktion gibt „!(*this < right)“ zurück.  
  
## <a name="operator-const-pathtype"></a>operator const path_type&  
  
``` 
 operator const std::experimental::filesystem::path&() const; 
```  
  
 Der Memberoperator gibt „mypath“ zurück.  
  
## <a name="path"></a>path  
  
```  
const std::experimental::filesystem::path& path() const noexcept;  
```  
  
 Die Memberfunktion gibt „mypath“ zurück.  
  
## <a name="replacefilename"></a>replace_filename  
  
```  
void replace_filename(
    const std::experimental::filesystem::path& pval,  
    file_status stat_arg = file_status(),  
    file_status symstat_arg = file_status());
```  
  
 Die Memberfunktion ersetzt „mypath“ durch „mypath.parent_path() / pval“, „mystat“ durch „stat_arg“ und „mysymstat“ durch „symstat_arg“.  
  
## <a name="status"></a>Status  
  
```  
file_status status() const; 
file_status status(error_code& ec) const noexcept;  
```  
  
 Beide Memberfunktionen geben „mystat“ möglicherweise zunächst wie folgt geändert zurück:  
  
1.  Bei „status_known(mystat)“ keinen weiteren Schritt ausführen.  
  
2.  Andernfalls gilt bei „!status_known(mysymstat) && !is_symlink(mysymstat)“ dann „mystat = mysymstat“.  
  
## <a name="symlinkstatus"></a>symlink_status  
  
```  
file_status symlink_status() const; 
file_status symlink_status(error_code& ec) const noexcept;  
```  
  
 Beide Memberfunktionen geben „mysymstat“ möglicherweise zunächst wie folgt geändert zurück: Bei „status_known(mysymstat)“ keinen weiteren Schritt ausführen. Andernfalls gilt „mysymstat = symlink_status(mypval)“.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<experimental/filesystem>  
  
 **Namespace:** std::experimental::filesystem  
  
## <a name="see-also"></a>Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [\<filesystem>](../standard-library/filesystem.md)


