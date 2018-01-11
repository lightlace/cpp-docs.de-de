---
title: Erstellen von Stack- und Warteschlangenauflistungen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
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
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: dd3c4d587f64fc89bf25cfd127e6b7efc490df8a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="creating-stack-and-queue-collections"></a>Erstellen von Stack- und Warteschlangenauflistungen
In diesem Artikel wird erläutert, wie andere Datenstrukturen, z. B. erstellen [Stapel](#_core_stacks) und [Warteschlangen](#_core_queues), von MFC-Klassen aufgelistet. Die Beispiele verwenden von abgeleitete Klassen `CList`, Sie können jedoch `CList` direkt, wenn Sie Funktionen hinzufügen möchten.  
  
##  <a name="_core_stacks"></a>Stapel  
 Da der standardmäßige listenauflistung enthalten sowohl einen Anfangs- und Endwert aufweist, ist es einfach, eine Liste der abgeleiteten Auflistung erstellen, die das Verhalten eines Last in First Out Stack imitiert. Ein Stapel ist wie ein Stapel von Fächer in einem Kantine auf. Der Stapel Fächer hinzugefügt werden, fahren oberster Position des Stapels. Der letzte Komponentenleiste hinzugefügt ist der erste entfernt werden soll. Die Listen-Memberfunktionen Auflistung `AddHead` und `RemoveHead` können verwendet werden, um das Hinzufügen und Entfernen von Elementen vom Anfang der Liste; daher das zuletzt hinzugefügte Element ist das erste entfernt werden soll.  
  
#### <a name="to-create-a-stack-collection"></a>So erstellen Sie eine Sammlung Stapel  
  
1.  Leiten Sie eine neue Listenklasse aus einer Liste bestehenden MFC-Klassen und fügen Sie weitere Memberfunktionen zum unterstützen der Funktionalität der Stapelvorgänge hinzu.  
  
     Im folgende Beispiel wird das Hinzufügen von Memberfunktionen zur Elemente sich im Stapel kurzer Blick auf das oberste Element im Stapel, Push-als auch das oberste Element vom Stapel veranschaulicht:  
  
     [!code-cpp[NVC_MFCCollections#20](../mfc/codesnippet/cpp/creating-stack-and-queue-collections_1.h)]  
  
 Beachten Sie, dass dieser Ansatz den zugrunde liegenden stellt `CObList` Klasse. Der Benutzer kann alle Aufrufen `CObList` Memberfunktion, ob für einen Stapel oder nicht sinnvoll.  
  
##  <a name="_core_queues"></a>Warteschlangen  
 Da der standardmäßige listenauflistung enthalten sowohl einen Anfangs- und Endwert aufweist, ist es auch einfach eine Liste der abgeleiteten Auflistung erstellt werden, die das Verhalten einer First in First-Out-Warteschlange imitiert. Eine Warteschlange ist z. B. ein branchenspezifischer Personen in einem Kantine auf. Die erste Person in der Zeile ist der erste versorgt werden. Als weitere Personen stammen, gehen sie bis zum Ende der Zeile, die Warteschlange. Die Listen-Memberfunktionen Auflistung `AddTail` und `RemoveHead` können verwendet werden, um das Hinzufügen und Elemente explizit aus der Kopf oder das Ende der Liste zu entfernen; daher das zuletzt hinzugefügte Element ist immer die letzte entfernt werden soll.  
  
#### <a name="to-create-a-queue-collection"></a>So erstellen Sie eine Warteschlange-Sammlung  
  
1.  Leiten Sie eine neue Listenklasse von einer der vordefinierten Liste-Klassen, die mit der Microsoft Foundation Class-Bibliothek bereitgestellt, und fügen Sie weitere Memberfunktionen, um die Semantik der Warteschlangenvorgänge zu unterstützen.  
  
     Das folgende Beispiel zeigt, wie Sie Member-Funktionen, um ein Element am Ende der Warteschlange hinzugefügt und das Abrufen des Elements vom Anfang der Warteschlange anfügen können.  
  
     [!code-cpp[NVC_MFCCollections#21](../mfc/codesnippet/cpp/creating-stack-and-queue-collections_2.h)]  
  
## <a name="see-also"></a>Siehe auch  
 [Sammlungen](../mfc/collections.md)

