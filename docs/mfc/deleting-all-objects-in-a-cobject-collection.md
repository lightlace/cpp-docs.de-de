---
title: Löschen aller Objekte in einer CObject-Sammlung
ms.date: 11/04/2016
helpviewer_keywords:
- objects [MFC], deleting in collections
- objects in CObject collections, deleting
- CObject class [MFC], deleting in collection
- collection classes [MFC], deleting all objects
- CObject class collection
- objects in CObject collections
- collection classes [MFC], shared objects
ms.assetid: 81d2c1d5-a0a5-46e1-8ab9-82b45cf7afd2
ms.openlocfilehash: 3e56c08f6165f6662c30e3ecbd6eda45c6696788
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50542583"
---
# <a name="deleting-all-objects-in-a-cobject-collection"></a>Löschen aller Objekte in einer CObject-Sammlung

In diesem Artikel wird erläutert, wie alle Objekte in einer Sammlung löschen (ohne löschen das Auflistungsobjekt selbst).

Zum Löschen aller Objekte in einer Auflistung von `CObject`s (oder abgeleitete Objekte `CObject`), verwenden Sie eine der in diesem Artikel beschriebenen Techniken Iteration [den Zugriff auf alle Mitglieder einer Sammlung](../mfc/accessing-all-members-of-a-collection.md) jedes Objekt in löschen Aktivieren.

> [!CAUTION]
>  Objekte in Sammlungen können freigegeben werden. D. h. die Auflistung speichert einen Zeiger auf das Objekt, aber andere Teile des Programms möglicherweise Verweise auf dasselbe Objekt. Sie müssen nicht auf ein Objekt zu löschen, die verwendet wird, bis alle Teile wurden unter Verwendung des Objekts sein.

In diesem Artikel erfahren Sie, wie die Objekte im gelöscht:

- [Eine Liste](#_core_to_delete_all_objects_in_a_list_of_pointers_to_cobject)

- [Ein array](#_core_to_delete_all_elements_in_an_array)

- [Eine Zuordnung](#_core_to_delete_all_elements_in_a_map)

#### <a name="_core_to_delete_all_objects_in_a_list_of_pointers_to_cobject"></a>  Zum Löschen aller Objekte in einer Liste von Zeigern auf CObject

1. Verwendung `GetHeadPosition` und `GetNext` um die Liste zu durchlaufen.

1. Verwenden der **löschen** Operator, um jedes Objekt gelöscht werden, da es in der Iteration gefunden wird.

1. Rufen Sie die `RemoveAll` Funktion, um alle Elemente aus der Liste entfernen, nachdem die Objekte, die mit diesen Elementen verknüpften gelöscht wurden.

Das folgende Beispiel zeigt, wie Sie zum Löschen aller Objekte aus einer Liste von `CPerson` Objekte. Jedes Objekt in der Liste ist ein Zeiger auf eine `CPerson` -Objekt, das ursprünglich auf dem Heap belegt wurde.

[!code-cpp[NVC_MFCCollections#17](../mfc/codesnippet/cpp/deleting-all-objects-in-a-cobject-collection_1.cpp)]

Der letzte Funktionsaufruf, `RemoveAll`, ist eine Liste-Memberfunktion, die alle Elemente aus der Liste entfernt. Die Memberfunktion `RemoveAt` ein einzelnes Element entfernt.

Beachten Sie, dass des Unterschied zwischen dem Löschen eines Elements-Objekts, und entfernen das Element selbst. Nur ein Element aus der Liste entfernt, wird der Verweis auf das Objekt entfernt. Das Objekt ist immer noch im Arbeitsspeicher vorhanden. Wenn Sie ein Objekt löschen, wird nicht mehr vorhanden, und der verwendete Speicherplatz wird freigegeben. Daher ist es wichtig, ein Element zu entfernen, sofort nach dem Auswählen des Elements Objekt gelöscht wurde, damit die Liste wird nicht versuchen Sie, den Zugriff auf Objekte, die nicht mehr vorhanden sind.

#### <a name="_core_to_delete_all_elements_in_an_array"></a>  So löschen Sie alle Elemente in einem array

1. Verwendung `GetSize` und Index-Ganzzahlwerten, durchläuft das Array.

1. Verwenden der **löschen** Operator, um jedes Element gelöscht werden, da es in der Iteration gefunden wird.

1. Rufen Sie die `RemoveAll` Funktion, um alle Elemente aus dem Array entfernt werden, nachdem sie gelöscht wurden.

   Der Code zum Löschen aller Elemente eines Arrays ist wie folgt aus:

   [!code-cpp[NVC_MFCCollections#18](../mfc/codesnippet/cpp/deleting-all-objects-in-a-cobject-collection_2.cpp)]

Wie Sie mit dem obigen Liste-Beispiel, das Sie aufrufen können `RemoveAll` So entfernen Sie alle Elemente in einem Array oder `RemoveAt` um ein einzelnes Element zu entfernen.

#### <a name="_core_to_delete_all_elements_in_a_map"></a> So löschen Sie alle Elemente in einer Zuordnung

1. Verwendung `GetStartPosition` und `GetNextAssoc` durchläuft das Array.

1. Verwenden der **löschen** Operator, um den Schlüssel und/oder einen Wert für jedes kartenelement gelöscht werden, da es in der Iteration gefunden wird.

1. Rufen Sie die `RemoveAll` Funktion, um alle Elemente aus der Zuordnung entfernen, nachdem sie gelöscht wurden.

   Der Code zum Löschen aller Elemente einer `CMap` Auflistung lautet wie folgt. Jedes Element in der Zuordnung ist eine Zeichenfolge als Schlüssel und ein `CPerson` Objekt (abgeleitet von `CObject`) als Wert.

   [!code-cpp[NVC_MFCCollections#19](../mfc/codesnippet/cpp/deleting-all-objects-in-a-cobject-collection_3.cpp)]

Rufen Sie `RemoveAll` So entfernen Sie alle Elemente in einer Karte oder `RemoveKey` um ein einzelnes Element mit dem angegebenen Schlüssel zu entfernen.

## <a name="see-also"></a>Siehe auch

[Zugreifen auf alle Elemente einer Auflistung](../mfc/accessing-all-members-of-a-collection.md)

