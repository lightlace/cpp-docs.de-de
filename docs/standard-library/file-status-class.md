---
title: "file_status-Klasse"
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
  - "filesystem/std::tr2::sys::file_status"
  - "filesystem/std::tr2::sys::file_status::perms"
  - "filesystem/std::tr2::sys::file_status::type"
dev_langs: 
  - "C++"
ms.assetid: 9781840e-ad22-44dd-ad79-0fabaa94bac4
caps.latest.revision: 15
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# file_status-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Umschließt ein [file\_type](../Topic/file_type%20Enumeration.md)\-Element.  
  
## Syntax  
  
```  
class file_status;  
```  
  
## file\_status::file\_status  
  
```  
explicit file_status(file_type ftype = file_type::none,    perms mask = perms::unknown) noexcept;file_status(const file_status&) noexcept = default;file_status(file_status&&) noexcept = default;  
```  
  
## file\_status::operator\=  
  
```  
file_status& operator=(const file_status&) noexcept = default;  
file_status& operator=(file_status&&) nexcept = default;  
```  
  
 Die als Standard festgelegten Memberzuweisungsoperatoren verhalten sich wie erwartet.  
  
## Typ  
  
```  
file_type type() const noexcept  
void type(file_type _Ftype) noexcept  
```  
  
 Ruft file\_type ab oder legt ihn fest.  
  
## Berechtigungen  
  
```  
perms permissions() const noexcept  
void permissions(perms_Prms) noexcept   
```  
  
 Ruft die Dateiberechtigungen ab oder legt sie fest.  
  
 Verwenden Sie den Setter, um Datei mit einem Schreibschutz zu versehen oder entfernen Sie das readonly\-Attribut.  
  
## Anforderungen  
 **Header:** filesystem  
  
 **Namespace:** std::tr2::sys  
  
## Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [path\-Klasse \(C\+\+\-Standardvorlagenbibliothek\)](../standard-library/path-class-cpp-standard-template-library.md)   
 [\<filesystem\>](../standard-library/filesystem.md)