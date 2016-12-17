---
title: "Unvollst&#228;ndige Typen"
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
  - "Arrays [C], Unvollständige Typen"
  - "Unvollständige Typen"
  - "Strukturen, Unvollständig"
  - "Typen [C], Unvollständig"
  - "Unions, Unvollständig"
  - "void-Schlüsselwort [C]"
  - "void-Schlüsselwort [C], Unvollständig"
ms.assetid: 01bc0cf6-9fa7-458c-9371-ecbe54ea6aee
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Unvollst&#228;ndige Typen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein unvollständiger Typ ist ein Typ, der einen Bezeichner beschreibt, dem jedoch die Informationen fehlen, die erforderlich sind, um die Größe des Bezeichners zu bestimmen.  Ein "unvollständiger Typ" kann Folgendes sein:  
  
-   Ein Strukturtyp, dessen Member noch nicht angegeben wurden.  
  
-   Ein Union\-Typ, dessen Member noch nicht angegeben wurden.  
  
-   Ein Arraytyp, dessen Dimension noch nicht angegeben wurde.  
  
 Der void\-Typ ist ein unvollständiger Typ, der nicht abgeschlossen werden kann.  Um einen unvollständigen Typ abzuschließen, müssen Sie die fehlenden Informationen angeben.  Die folgenden Beispiele zeigen, wie Sie die unvollständigen Typen erstellen und abschließen.  
  
-   Um einen unvollständigen Strukturtyp zu erstellen, müssen Sie einen Strukturtyp ohne Angabe seiner Member deklarieren.  In diesem Beispiel zeigt der `ps`\-Zeiger auf einen unvollständigen Strukturtyp mit der Bezeichnung `student`.  
  
    ```  
    struct student *ps;  
    ```  
  
-   Um einen unvollständigen Strukturtyp abzuschließen, müssen Sie denselben Strukturtyp später im gleichen Bereich mit den angegebenen Membern deklarieren, wie in  
  
    ```  
    struct student  
    {  
        int num;  
    }                   /* student structure now completed */  
    ```  
  
-   Um einen unvollständigen Arraytyp zu erstellen, müssen Sie einen Arraytyp ohne Angabe der Wiederholungsanzahl deklarieren.  Beispiel:  
  
    ```  
    char a[];  /* a has incomplete type */  
    ```  
  
-   Um einen unvollständigen Arraytyp abzuschließen, müssen Sie den gleichen Namen später im gleichen Bereich mit der angegebenen Wiederholungsanzahl deklarieren, wie in  
  
    ```  
    char a[25]; /* a now has complete type */  
    ```  
  
## Siehe auch  
 [Deklarationen und Typen](../c-language/declarations-and-types.md)