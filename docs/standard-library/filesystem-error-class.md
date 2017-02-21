---
title: "filesystem_error-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "filesystem/std::tr2::sys::filesystem_error"
dev_langs: 
  - "C++"
ms.assetid: c53aac27-c1fa-43e4-8967-48ea8ba1f172
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# filesystem_error-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Basisklasse für alle Ausnahmen, die ausgelöst werden, um einen Systemüberlauf auf niedriger Ebene zu melden.  
  
## Syntax  
  
```  
class filesystem_error    : public system_error;  
```  
  
## Hinweise  
 Die Klasse fungiert als Basisklasse für alle Ausnahmen, die ausgelöst werden, um einen Fehler in \<filesystem\>\-Funktionen zu melden. Sie speichert ein Objekt vom Typ „string“, das hier zur Veranschaulichung den Namen „mymesg“ erhält. Sie speichert außerdem zwei Objekte vom Typ „path“ namens „mypval1“ und „mypval2“.  
  
## filesystem\_error::filesystem\_error  
  
```  
filesystem_error(const string& what_arg, error_code ec);  
filesystem_error(const string& what_arg,  
    const path& pval1, error_code ec);  
filesystem_error(const string& what_arg,  
    const path& pval1, const path& pval2, error_code ec);  
```  
  
 Der erste Konstruktor erstellt die Meldung aus „what\_arg“ und „ec“. Der zweite Konstruktor erstellt die Meldung aus „pval1“, die in „mypval1“ gespeichert wird. Der dritte Konstruktor erstellt die Meldung auch aus „pval1“, die in „mypval1“ gespeichert wird, sowie aus „pval2“, die wiederum in „mypval2“ gespeichert wird.  
  
## filesystem\_error::path1  
  
```  
const path& path1() const noexcept;  
  
```  
  
 Die Memberfunktion gibt „mypval1“ zurück.  
  
## filesystem\_error::path2  
  
```  
const path& path2() const noexcept;  
  
```  
  
 Die Memberfunktion gibt „mypval2“ zurück.  
  
## filesystem\_error::what  
  
```  
const char *what() const noexcept;  
```  
  
 Die Memberfunktion gibt einen Zeiger auf ein NTBS zurück, das vorzugsweise aus „runtime\_error::what\(\)“, „system\_error::what\(\)“, „mymesg“, „mypval1.native\_string\(\)“ und „mypval2.native\_string\(\)“ besteht.  
  
## Anforderungen  
 **Header:** Dateisystem  
  
 **Namespace:** std::tr2::sys  
  
## Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [system\_error\-Klasse](../standard-library/system-error-class.md)   
 [\<filesystem\>](../standard-library/filesystem.md)   
 [\<exception\>](../standard-library/exception.md)