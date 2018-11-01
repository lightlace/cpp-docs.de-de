---
title: Erstellen von Stack- und Warteschlangenauflistungen
ms.date: 11/04/2016
helpviewer_keywords:
- MFC collection classes [MFC], stack collections
- collections, stack
- stack
- collection classes [MFC], creating
- queue collections
- MFC collection classes [MFC], queue collections
- stack collections
- collections, queue
ms.assetid: 3c7bc198-35f0-4fc3-aaed-6005a0f22638
ms.openlocfilehash: 082308acaeddcb173a0d873c0f50e2e40fd8fe12
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50569221"
---
# <a name="creating-stack-and-queue-collections"></a>Erstellen von Stack- und Warteschlangenauflistungen

In diesem Artikel wird erläutert, wie andere Datenstrukturen, z. B. Erstellung [Stapel](#_core_stacks) und [Warteschlangen](#_core_queues), von MFC-Klassen aufgelistet. Die Beispiele verwenden die von abgeleitete Klassen `CList`, aber Sie können `CList` direkt, wenn Sie Funktionen hinzufügen möchten.

##  <a name="_core_stacks"></a> Stapel

Da die Standardliste Auflistung sowohl eine HEAD- und einem Ende verfügt, ist es einfach, eine Liste der abgeleiteten Auflistung zu erstellen, die das Verhalten eines Stapels Last-in-First-Out imitiert. Ein Stapel ist wie ein Stapel von Fächer, in einem Kantine. Fächer im Stapel hinzugefügt werden, wechseln sie auf den Stapel. Der letzte Komponentenleiste hinzugefügt ist der erste entfernt werden soll. Die Listen-Memberfunktionen Auflistung `AddHead` und `RemoveHead` können verwendet werden, um das Hinzufügen und entfernen Sie Elemente vom Anfang der Liste; daher das zuletzt hinzugefügte Element ist der erste entfernt werden soll.

#### <a name="to-create-a-stack-collection"></a>Zum Erstellen einer Sammlung stack

1. Eine der vorhandenen Klassen, MFC-Liste eine neue Listenklasse abgeleitet, und fügen Sie weitere Member-Funktionen, um die Funktionalität des Stack-Vorgänge unterstützen hinzu.

   Das folgende Beispiel zeigt, wie Memberfunktionen zur push-Elemente auf dem Stapel, einen Blick auf das oberste Element im Stapel, und das oberste Element aus dem Stapel hinzugefügt wird:

   [!code-cpp[NVC_MFCCollections#20](../mfc/codesnippet/cpp/creating-stack-and-queue-collections_1.h)]

Beachten Sie, dass dieser Ansatz das zugrunde liegende macht `CObList` Klasse. Der Benutzer kann alle Aufrufen `CObList` Memberfunktion, ob es für einen Stapel oder nicht sinnvoll.

##  <a name="_core_queues"></a> Warteschlangen

Da die Standardliste Auflistung sowohl eine HEAD- und einem Ende verfügt, ist es auch einfach, eine Liste der abgeleiteten Auflistung zu erstellen, die das Verhalten einer First-in-First-Out-Warteschlange imitiert. Eine Warteschlange ist wie eine Linie von Personen in einem Kantine. Die erste Person in der Zeile wird als erster bereitgestellt werden. Wie kommen mehr Menschen, fahren mit dem Ende der Zeile auf die Reihe zu warten. Die Listen-Memberfunktionen Auflistung `AddTail` und `RemoveHead` können verwendet werden, um das Hinzufügen und Elemente explizit aus der Kopf oder das Ende der Liste zu entfernen; daher das zuletzt hinzugefügte Element ist immer das letzte entfernt werden soll.

#### <a name="to-create-a-queue-collection"></a>Zum Erstellen einer Warteschlange-Sammlung

1. Eine der vordefinierten Listenklassen bereitgestellt, mit der Microsoft Foundation Class-Bibliothek eine neue Listenklasse abgeleitet, und fügen Sie weitere Member-Funktionen zur Unterstützung von der Semantik der Vorgänge für Queue hinzu.

   Das folgende Beispiel zeigt, wie Sie Member-Funktionen, um ein Element am Ende der Warteschlange hinzugefügt und das Abrufen des Elements vom Anfang der Warteschlange anfügen können.

   [!code-cpp[NVC_MFCCollections#21](../mfc/codesnippet/cpp/creating-stack-and-queue-collections_2.h)]

## <a name="see-also"></a>Siehe auch

[Sammlungen](../mfc/collections.md)

