---
title: "&lt;new&gt;"
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
  - "std::<new>"
  - "<new>"
  - "std.<new>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "new-Header"
ms.assetid: 218e2a15-34e8-4ef3-9122-1e90eccf8559
caps.latest.revision: 18
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# &lt;new&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Definiert einige Typen und Funktionen, die die Belegung und Freigabe von Speicher unter Programmsteuerung steuern.  Hierin werden außerdem Komponenten für das Berichten von Speicherverwaltungsfehlern definiert.  
  
## Syntax  
  
```  
  
#include <new>  
  
```  
  
## Hinweise  
 Einige der Funktionen, die in diesem Header deklariert sind, können ersetzt werden.  Die Implementierung stellt eine Standardversion bereit, deren Verhalten in diesem Dokument beschrieben ist.  Ein Programm kann jedoch eine Funktion mit derselben Signatur definieren, um die Standardversion zur Linkzeit zu ersetzen.  Die ersetzende Version muss die Anforderungen erfüllen, die in diesem Dokument beschrieben sind.  
  
### Objekte  
  
|||  
|-|-|  
|[nothrow](../Topic/nothrow%20\(%3Cnew%3E\).md)|Stellt ein Objekt bereit, das als Argument für die `nothrow`\-Versionen von **new** und **delete** verwendet werden muss.|  
  
### TypeDefs  
  
|||  
|-|-|  
|[new\_handler](../Topic/new_handler.md)|Ein Typ, der auf eine Funktion verweist, die als neuer Handler geeignet ist.|  
  
### Funktionen  
  
|||  
|-|-|  
|[set\_new\_handler](../Topic/set_new_handler.md)|Installiert eine Benutzerfunktion, die aufgerufen wird, wenn "new" nicht in der Lage ist, Arbeitsspeicher zu belegen.|  
  
### Operatoren  
  
|||  
|-|-|  
|[operator delete](../Topic/operator%20delete%20\(%3Cnew%3E\).md)|Die Funktion, die durch einen Löschausdruck aufgerufen wird, um Speicher für einzelne Objekte freizugeben.|  
|[operator delete&#91;&#93;](../Topic/operator%20delete\(%3Cnew%3E\).md)|Die Funktion, die durch einen Löschausdruck \(delete\-Ausdruck\) aufgerufen wird, um Speicher für ein Array von Objekten freizugeben.|  
|[operator new](../Topic/operator%20new%20\(%3Cnew%3E\).md)|Die Funktion, die durch einen new\-Ausdruck aufgerufen wird, um Speicher für einzelne Objekte zu belegen.|  
|[operator new&#91;&#93;](../Topic/operator%20new\(%3Cnew%3E\).md)|Die Funktion, die durch einen new\-Ausdruck aufgerufen wird, um Speicher für ein Array von Objekten zu belegen.|  
  
### Klassen  
  
|||  
|-|-|  
|[bad\_alloc\-Klasse](../standard-library/bad-alloc-class.md)|Die Klasse beschreibt eine Ausnahme, die ausgelöst wurde, um anzugeben, dass eine Belegungsanforderung nicht erfolgreich war.|  
|[nothrow\_t Class](../standard-library/nothrow-t-structure.md)|Die Klasse wird als Funktionsparameter für den new\-Operator verwendet, um anzugeben, dass die Funktion zum Mitteilen eines Belegungsfehlers keine Ausnahme auslösen, sondern einen NULL\-Zeiger zurückgeben soll.|  
  
## Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)