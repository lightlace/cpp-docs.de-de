---
title: "&lt;system_error&gt;"
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
  - "std.<system_error>"
  - "std::<system_error>"
  - "<system_error>"
  - "system_error"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "system_error-Header"
ms.assetid: 5e046c6e-48d9-4740-8c8a-05f3727c1215
caps.latest.revision: 15
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# &lt;system_error&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Fügen Sie der `<system_error>` ein, um die Ausnahmeklasse `system_error` und zugehörige Vorlagen zur Verarbeitung zu definieren von Systemfehlern auf niedriger Ebene.  
  
## Syntax  
  
```  
#include <system_error>  
```  
  
### Objekte  
  
|||  
|-|-|  
|[generic\_category](../Topic/generic_category.md)|Stellt die Kategorie für generische Fehler dar.|  
|[system\_category](../Topic/system_category.md)|Stellt die Kategorie für die Fehler dar, die von Systemüberläufe systemnahe verursacht werden.|  
  
### Typedefs  
  
|||  
|-|-|  
|[generic\_errno](../Topic/generic_errno.md)|Ein Typ, der die Enumeration darstellt, die die symbolische Namen für alle Fehlercodemakros angibt, definierte durch Posix in `<errno.h>`.|  
  
### Funktionen  
  
|||  
|-|-|  
|[make\_error\_code](../Topic/make_error_code.md)|Erstellt ein `error_code`\-Objekt.|  
|[make\_error\_condition](../Topic/make_error_condition.md)|Erstellt ein `error_condition`\-Objekt.|  
  
### Operatoren  
  
|||  
|-|-|  
|[operator\=\=](../Topic/operator==%20\(%3Csystem_error%3E\).md)|Testet, ob das Objekt auf der linken Seite des Operators auf das Objekt auf der rechten Seite ist.|  
|[operator\!\=](../Topic/operator!=%20\(%3Csystem_error%3E\).md)|Testet, ob das Objekt auf der linken Seite des Operators ungleich das Objekt auf der rechten Seite ist.|  
|[Operator implementiert.\<](../Topic/operator%3C%20\(%3Csystem_error%3E\).md)|Testet, ob ein Objekt weniger ist, als das Objekt übergeben für den Vergleich.|  
  
### Enumerationen  
  
|||  
|-|-|  
|[errc](../Topic/errc%20Enumeration.md)|Gibt symbolische Namen für alle Fehlercodemakros an, die von Posix in `<errno.h>` definiert sind.|  
  
### Klassen und Strukturen  
  
|||  
|-|-|  
|[error\_category](../standard-library/error-category-class.md)|Stellt die Zusammenfassung, Common\-Basis für Objekte dar, die eine Kategorie Fehlercodes beschrieben.|  
|[error\_code](../standard-library/error-code-class.md)|Stellt Systemfehler auf niedriger Ebene dar, die implementierungsabhängig sind.|  
|[error\_condition](../standard-library/error-condition-class.md)|Stellt benutzerdefinierte Fehlercodes dar.|  
|[is\_error\_code\_enum](../standard-library/is-error-code-enum-class.md)|Stellt ein Typprädikat dar, das zum [error\_code\-Klasse](../standard-library/error-code-class.md)\-Enumeration testet.|  
|[is\_error\_condition\_enum](../standard-library/is-error-condition-enum-class.md)|Stellt ein Typprädikat dar, das zum [error\_condition\-Klasse](../standard-library/error-condition-class.md)\-Enumeration testet.|  
|[system\_error](../standard-library/system-error-class.md)|Stellt die Basisklasse für alle Ausnahmen dar, die ausgelöst werden, um einen Systemüberlauf zu melden auf niedriger Ebene.|  
  
## Anforderungen  
 **Header:** \<system\_error\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)