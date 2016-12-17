---
title: "stdext-Namespace"
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
  - "stdext"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_DEFINE_DEPRECATED_HASH_CLASSES-Symbol"
  - "stdext-Namespace"
ms.assetid: 3e94fc89-0584-424f-bc09-081b73379545
caps.latest.revision: 10
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# stdext-Namespace
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Member der [\<hash\_map\>](../standard-library/hash-map.md)\- und [\<hash\_set\>](../standard-library/hash-set.md)\-Headerdateien sind nicht Teil des ISO C\+\+\-Standards. Daher wurden diese Typen und Member aus dem `std`\-Namespace in den `stdext`\-Namespace verschoben, um dem C\+\+\-Standard zu entsprechen.  
  
 Beim Kompilieren mit der Standardoption [\/Ze](../build/reference/za-ze-disable-language-extensions.md) gibt der Compiler eine Warnung für die Verwendung von `std` für Member der \<hash\_map\>\- und \<hash\_set\>\-Headerdateien aus. Verwenden Sie das [warning](../preprocessor/warning.md)\-Pragma, um die Warnung zu deaktivieren.  
  
 Damit den Compiler bei der Verwendung von `std` für Member der \<hash\_map\>\- und \<hash\_set\>\-Headerdateien mit **\/Ze** einen Fehler generiert, fügen Sie die folgende Direktive vor dem Einbeziehen \(\#include\) beliebiger Headerdateien der C\+\+\-Standardbibliothek hinzu.  
  
```  
#define _DEFINE_DEPRECATED_HASH_CLASSES 0  
```  
  
 Beim Kompilieren mit **\/Za** generiert der Compiler einen Fehler.  
  
## Siehe auch  
 [STL\-Übersicht](../standard-library/cpp-standard-library-overview.md)