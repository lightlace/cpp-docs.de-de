---
title: Verknüpfungstypen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- no linkage
- linkage [C++], none
- linkage [C++], types of
- types [C++], linkage
- internal linkage, types of linkage
- external linkage, linkage types
ms.assetid: 41326c7f-4602-4bad-a648-697604858ba0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dfddf0105603311179340a0c6b0b2e8fb328b134
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="types-of-linkage"></a>Verknüpfungstypen
Das Teilen von Namen von Objekten und Funktionen zwischen Übersetzungseinheiten wird als Verknüpfung bezeichnet. Diese Namen können Folgendes aufweisen:  
  
-   Interne Verknüpfung, wobei sie sich nur auf Programmelemente innerhalb ihrer eigenen Übersetzungseinheiten beziehen. Sie werden nicht für andere Übersetzungseinheiten freigegeben.  
  
     Der gleiche Name in einer anderen Übersetzungseinheit bezieht sich möglicherweise auf ein anderes Objekt oder eine andere Klasse. Namen mit interner Verknüpfung werden manchmal auch als lokal in ihren Übersetzungseinheiten bezeichnet.  
  
     Eine Beispieldeklaration eines Namens mit interner Verknüpfung ist:  
  
    ```  
    static int i;   // The static keyword ensures internal linkage.  
    ```  
  
-   Externe Verknüpfung, wobei sie sich auf Programmelemente in jeder Übersetzungseinheit im Programm beziehen können - das Programmelement wird von den Übersetzungseinheiten gemeinsam genutzt.  
  
     Der gleiche Name in einer anderen Übersetzungseinheit bezieht sich auf das gleiche Objekt oder die gleiche Klasse. Namen mit externer Verknüpfung werden manchmal auch als global bezeichnet.  
  
     Eine Beispieldeklaration eines Namens mit externer Verknüpfung ist:  
  
    ```  
    extern int i;  
    ```  
  
-   Keine Verknüpfung, wobei sie auf eindeutige Entitäten verweisen. Der gleiche Name in einem anderen Bereich bezieht sich u. U. nicht auf dasselbe Objekt. Ein Beispiel hierfür ist eine Enumeration. (Beachten Sie jedoch, dass Sie einen Zeiger auf ein Objekt ohne Verknüpfung übergeben können. Dadurch wird das Objekt in anderen Übersetzungseinheiten verfügbar.)  
  
## <a name="see-also"></a>Siehe auch  
 [Programm und Verknüpfung](../cpp/program-and-linkage-cpp.md)