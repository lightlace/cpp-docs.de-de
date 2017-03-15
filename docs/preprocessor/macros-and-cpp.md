---
title: "Makros und C++"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Makros"
  - "Makros, C++"
ms.assetid: 83a344c1-73c9-4ace-8b93-cccfb62c6133
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Makros und C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C\+\+ bietet neue Funktionen, von denen einige die Funktionen ablösen, die vom ANSI\-C\-Präprozessor bereitgestellt werden.  Diese neuen Funktionen erweitern die Typsicherheit und die Voraussagbarkeit der Sprache:  
  
-   In C\+\+ können Objekte, die als **const** deklariert sind, in konstanten Ausdrücken verwendet werden.  Dadurch können Programme Konstanten deklarieren, die Typ\- und Wertinformationen haben, und Enumerationen, die mit dem Debugger symbolisch angezeigt werden können.  Die Verwendung der `#define`\-Präprozessordirektive zum Definieren von Konstanten ist weniger genau.  Einem **const**\-Objekt wird kein Speicherplatz zugeordnet, es sei denn, dass ein Ausdruck im Programm gefunden wird, der die Adresse akzeptiert.  
  
-   Funktionstypmakros werden von der C\+\+\-Inlinefunktion abgelöst.  Im Vergleich zu Makros haben Inlinefunktionen folgende Vorteile:  
  
    -   Typsicherheit.  Inlinefunktionen unterliegen derselben Typüberprüfung wie normale Funktionen.  Makros sind nicht typsicher.  
  
    -   Korrekte Behandlung von Argumenten, die Nebeneffekte haben.  Inlinefunktionen werten vor dem Eintreten in den Funktionstext die Ausdrücke aus, die als Argumente bereitgestellt werden.  Daher ist es nicht möglich, dass ein Ausdruck mit Nebeneffekten unsicher ist.  
  
 Weitere Informationen zu Inlinefunktionen finden Sie unter [inline \_\_inline, \_\_forceinline](../misc/inline-inline-forceinline.md).  
  
 Aus Gründen der Abwärtskompatibilität werden alle Präprozessorfunktionen, die in ANSI C und in früheren C\+\+\-Spezifikationen vorhanden sind, für Microsoft C\+\+ beibehalten.  
  
## Siehe auch  
 [Vordefinierte Makros](../preprocessor/predefined-macros.md)   
 [Makros](../preprocessor/macros-c-cpp.md)