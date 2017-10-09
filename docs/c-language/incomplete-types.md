---
title: "Unvollständige Typen | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- void keyword [C], incomplete
- types [C], incomplete
- incomplete types
- unions, incomplete
- arrays [C], incomplete types
- void keyword [C]
- structures, incomplete
ms.assetid: 01bc0cf6-9fa7-458c-9371-ecbe54ea6aee
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: 2dd7ab170717cb0e20d71ad4e62e2cbc03483fbf
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="incomplete-types"></a>Unvollständige Typen
Ein unvollständiger Typ ist ein Typ, der einen Bezeichner beschreibt, dem jedoch die Informationen fehlen, die erforderlich sind, um die Größe des Bezeichners zu bestimmen. Ein "unvollständiger Typ" kann Folgendes sein:  
  
-   Ein Strukturtyp, dessen Member noch nicht angegeben wurden.  
  
-   Ein Union-Typ, dessen Member noch nicht angegeben wurden.  
  
-   Ein Arraytyp, dessen Dimension noch nicht angegeben wurde.  
  
 Der void-Typ ist ein unvollständiger Typ, der nicht abgeschlossen werden kann. Um einen unvollständigen Typ abzuschließen, müssen Sie die fehlenden Informationen angeben. Die folgenden Beispiele zeigen, wie Sie die unvollständigen Typen erstellen und abschließen.  
  
-   Um einen unvollständigen Strukturtyp zu erstellen, müssen Sie einen Strukturtyp ohne Angabe seiner Member deklarieren. In diesem Beispiel zeigt der `ps`-Zeiger auf einen unvollständigen Strukturtyp mit der Bezeichnung `student`.  
  
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
  
-   Um einen unvollständigen Arraytyp zu erstellen, müssen Sie einen Arraytyp ohne Angabe der Wiederholungsanzahl deklarieren. Zum Beispiel:  
  
    ```  
    char a[];  /* a has incomplete type */  
    ```  
  
-   Um einen unvollständigen Arraytyp abzuschließen, müssen Sie den gleichen Namen später im gleichen Bereich mit der angegebenen Wiederholungsanzahl deklarieren, wie in  
  
    ```  
    char a[25]; /* a now has complete type */  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 [Deklarationen und Typen](../c-language/declarations-and-types.md)
