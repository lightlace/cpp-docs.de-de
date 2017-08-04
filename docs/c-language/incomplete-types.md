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
translation.priority.ht:
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: ebc73813c28f5ccd25b28cadf283412a204b57d3
ms.contentlocale: de-de
ms.lasthandoff: 05/18/2017

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
