---
title: file_status-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- file_status
- filesystem/std::experimental::filesystem::v1::file_status
- filesystem/std::experimental::filesystem::v1::file_status::operator=
- filesystem/std::experimental::filesystem::v1::file_status::type
- filesystem/std::experimental::filesystem::v1::file_status::permissions
dev_langs:
- C++
ms.assetid: 9781840e-ad22-44dd-ad79-0fabaa94bac4
caps.latest.revision: 15
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
ms.openlocfilehash: 1095fbeeceb33fd9dedf0ad1217eab1a052f5ba1
ms.contentlocale: de-de
ms.lasthandoff: 04/29/2017

---
# <a name="filestatus-class"></a>file_status-Klasse
Umschließt [file_type](../standard-library/filesystem-enumerations.md#file_type) und Datei-[perms](../standard-library/filesystem-enumerations.md#perms)  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
class file_status;  
```  
  
## <a name="filestatusfilestatus"></a>file_status::file_status  
  
```cpp  
explicit file_status(  
   file_type ftype = file_type::none,  
   perms mask = perms::unknown) noexcept;  
  
file_status(const file_status&) noexcept = default;  
  
file_status(file_status&&) noexcept = default; 

~file_status() noexcept = default; 
```  
  
## <a name="filestatusoperator"></a>file_status::operator=  
  
```cpp  
file_status& operator=(const file_status&) noexcept = default;  
file_status& operator=(file_status&&) nexcept = default;  
```  
  
 Die als Standard festgelegten Memberzuweisungsoperatoren verhalten sich wie erwartet.  
  
## <a name="type"></a>Typ  
  
```cpp  
file_type type() const noexcept  
void type(file_type ftype) noexcept  
```  
  
 Ruft file_type ab oder legt ihn fest.  
  
## <a name="permissions"></a>Berechtigungen  
  
```cpp  
perms permissions() const noexcept  
void permissions(perms mask) noexcept   
```  
  
 Ruft die Dateiberechtigungen ab oder legt sie fest.  
  
 Verwenden Sie den Setter, um Datei mit einem Schreibschutz zu versehen oder entfernen Sie das readonly-Attribut.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Filesystem >  
  
 **Namespace:** Std::experimental::filesystem, Std::experimental::filesystem::v1  
  
## <a name="see-also"></a>Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [Path-Klasse](../standard-library/path-class.md)   
 [\<filesystem>](../standard-library/filesystem.md)


