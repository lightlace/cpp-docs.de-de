---
title: "L&#246;schen aller Objekte in einer CObject-Sammlung | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CObject-Klassenauflistung"
  - "CObject-Klasse, Löschen in Auflistung"
  - "Auflistungsklassen, Löschen aller Objekte"
  - "Auflistungsklassen, Freigegebene Objekte"
  - "Objekte [C++], Löschen in Auflistungen"
  - "Objekte in CObject-Auflistungen"
  - "Objekte in CObject-Auflistungen, Löschen"
ms.assetid: 81d2c1d5-a0a5-46e1-8ab9-82b45cf7afd2
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# L&#246;schen aller Objekte in einer CObject-Sammlung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Artikel wird beschrieben, wie Sie die Objekte in einer Auflistung gelöscht \(ohne das Auflistungsobjekt selbst zu deaktivieren\).  
  
 Um alle Objekte in einer Sammlung von `CObject`s \(oder Objekten zu löschen abgeleitet von `CObject`\), verwenden Sie eine der Iterationstechniken, die im Artikel [Zugreifen auf alle Member einer Auflistung](../mfc/accessing-all-members-of-a-collection.md) beschrieben werden um jedes Objekt einzeln zu löschen.  
  
> [!CAUTION]
>  Objekte in Auflistungen können freigegeben werden.  Das heißt, enthält die Auflistung ein Zeiger auf das Objekt, aber andere Teile des Programms haben möglicherweise auch Zeiger zum gleichen Objekt.  Begrenzen Sie, dass kein Objekt löschen, das freigegeben wird, bis alle Bestandteile mithilfe des Objekts haben.  
  
 In diesem Artikel wird gezeigt, wie Sie Objekte in löscht:  
  
-   [Eine Liste](#_core_to_delete_all_objects_in_a_list_of_pointers_to_cobject)  
  
-   [Ein Array](#_core_to_delete_all_elements_in_an_array)  
  
-   [Eine Zuordnung](#_core_to_delete_all_elements_in_a_map)  
  
#### Um alle Objekte in einer Liste von zu Zeigern CObject löschen  
  
1.  Verwendung von `GetHeadPosition` und `GetNext`, durch die Liste durchlaufen.  
  
2.  Verwenden Sie den Operator **löschen**, um jedes Objekt zu löschen, wie es in der Iteration gefunden wird.  
  
3.  Rufen Sie die Funktion `RemoveAll` auf, um alle Elemente aus der Liste entfernen, nachdem die Objekte, die mit den Elementen zugeordnet sind, gelöscht wurden.  
  
 Das folgende Beispiel zeigt, wie Sie die Objekte aus einer Liste von `CPerson`\-Objekten gelöscht.  Jedes Objekt in der Liste ist ein Zeiger auf ein `CPerson`\-Objekt, das ursprünglich auf dem Heap reserviert wurde.  
  
 [!CODE [NVC_MFCCollections#17](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCCollections#17)]  
  
 Der letzte Funktionsaufruf, `RemoveAll`, ist eine Listenmemberfunktion, die alle Elemente aus der Liste entfernt.  Die Memberfunktion `RemoveAt` wird ein einzelnes Element.  
  
 Beachten Sie den Unterschied zwischen dem Löschen des Objekts eines Elements und das Entfernen des Elements selbst.  Ein Element aus der Liste entfernen, entfernt nur den Verweis der Liste auf das Objekt.  Das Objekt ist noch im Arbeitsspeicher.  Wenn Sie ein Objekt löschen, wird es auf vorhanden und der Arbeitsspeicher wird freigegeben.  Daher ist es wichtig, ein Element zu entfernen, nachdem das Objekt des Elements gelöscht wurde, damit die Liste nicht versucht, auf Objekte zugreifen, die nicht mehr vorhanden sind.  
  
#### Um alle Elemente in einem Array löschen  
  
1.  Verwenden Sie `GetSize` und Ganzzahlenindexwerte, um das Array zu durchlaufen.  
  
2.  Verwenden Sie den Operator **löschen**, um die jeweiligen Elemente zu löschen, wie es in der Iteration gefunden wird.  
  
3.  Rufen Sie die Funktion `RemoveAll` auf, um alle Elemente aus dem Array entfernen, nachdem sie gelöscht wurden.  
  
     Der Code zum Löschen aller Elemente eines Arrays ist, wie folgt:  
  
     [!CODE [NVC_MFCCollections#18](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCCollections#18)]  
  
 Wie im Listenbeispiel oben, können Sie `RemoveAll` aufrufen, um alle Elemente in einem Array oder in `RemoveAt` zu entfernen, wenn ein einzelnes Element zu entfernen.  
  
#### Um alle Elemente in einer Zuordnung löschen  
  
1.  Verwenden Sie `GetStartPosition` und `GetNextAssoc`, um das Array zu durchlaufen.  
  
2.  Verwenden Sie den Operator **löschen**, um den Schlüssel und\/oder den Wert für jedes Kartenelement zu löschen, wie es in der Iteration gefunden wird.  
  
3.  Rufen Sie die Funktion `RemoveAll` auf, um alle Elemente aus der Zuordnung zu entfernen, nachdem sie gelöscht wurden.  
  
     Der Code zum Löschen aller Elemente einer Auflistung `CMap` lautet wie folgt.  Jedes Element in der Zuordnung hat eine Zeichenfolge als Schlüssel und `CPerson`\-Objekt \(abgeleitet von `CObject`\) als Wert.  
  
     [!CODE [NVC_MFCCollections#19](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCCollections#19)]  
  
 Sie können `RemoveAll` aufrufen, um alle Elemente in einer Zuordnung oder `RemoveKey` zu entfernen, wenn ein einzelnes Element mit dem angegebenen Schlüssel zu entfernen.  
  
## Siehe auch  
 [Zugreifen auf alle Elemente einer Auflistung](../mfc/accessing-all-members-of-a-collection.md)