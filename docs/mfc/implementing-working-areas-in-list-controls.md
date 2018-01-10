---
title: Implementieren von Arbeitsbereichen in Listensteuerelementen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- list controls [MFC], working areas
- working areas in list control [MFC]
ms.assetid: fbbb356b-3359-4348-8603-f1cb114cadde
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cefb8007fd9b73dda4c0e8a99e9ae9daa1bfcc34
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="implementing-working-areas-in-list-controls"></a>Implementieren von Arbeitsbereichen in Listensteuerelementen
Standardmäßig ordnet ein Listenfeld-Steuerelement alle Elemente in einer Weise standard Raster an. Jedoch wird eine andere Methode unterstützt Arbeitsbereichen, der die Listeneinträge in rechteckige Gruppen nebeneinander anordnet. Für ein Bild eines Steuerelements, das Arbeitsbereiche implementiert, finden Sie unter Verwenden von Listenansicht Steuerelementen im Windows SDK.  
  
> [!NOTE]
>  Arbeitsbereiche sind sichtbar, nur, wenn das Strukturelement-Steuerelement im Symbol oder kleinen Symbols-Modus befindet. Allerdings werden alle aktuellen Arbeitsbereiche beibehalten, wenn die Ansicht für den Bericht oder eine Liste Modus gewechselt wird.  
  
 Arbeitsbereiche können verwendet werden, zum Anzeigen eines leeren Rahmens (auf die Links, oben und/oder rechts von den Elementen) oder dazu führen, dass eine horizontale Bildlaufleiste angezeigt, die angezeigt werden, wenn es normalerweise würde nicht möglich. Häufig werden mehrere Arbeitsbereiche erstellen, auf die Elemente verschoben oder gelöscht werden können. Mit dieser Methode können Sie Bereiche erstellen, in einer einzigen Ansicht, die unterschiedliche Bedeutungen haben. Der Benutzer konnte die Elemente dann kategorisieren, indem sie in einem anderen Bereich platziert. Ein Beispiel hierfür wäre eine Ansicht eines Dateisystems, die einen Bereich für Dateien mit Lese-/Schreibzugriff und einen anderen Bereich für schreibgeschützte Dateien aufweist. Wenn eine Datei in den Bereich "schreibgeschützt" verschoben wurden, würde es automatisch schreibgeschützt sein. Verschieben einer Datei im Nur-Lese Bereich in den Bereich "Lese-/Schreibzugriff" würde die Datei Lese-/Schreibzugriff machen.  
  
 `CListCtrl`stellt mehrere Memberfunktionen zum Erstellen und Verwalten von Arbeitsbereichen in Listensteuerelementen bereit. [GetWorkAreas](../mfc/reference/clistctrl-class.md#getworkareas) und [SetWorkAreas](../mfc/reference/clistctrl-class.md#setworkareas) abzurufen und ein Array von `CRect` Objekte (oder `RECT` Strukturen), der derzeit implementierten Arbeitsbereiche für das Listensteuerelement gespeichert. Darüber hinaus [ruft GetNumberOfWorkAreas](../mfc/reference/clistctrl-class.md#getnumberofworkareas) Ruft die aktuelle Anzahl der Arbeitsbereiche für das Listensteuerelement (standardmäßig 0 (null)).  
  
## <a name="items-and-working-areas"></a>Elemente und Arbeitsbereiche  
 Wenn ein Arbeitsbereich erstellt wird, werden die Elemente, die innerhalb der Arbeitsbereich Mitglieder. Wenn ein Element in einem Arbeitsbereich verschoben wird, wird es entsprechend ein Mitglied der Arbeitsbereich, in dem er verschoben wurde. Ein Element nicht in keinem Arbeitsbereich liegt, wird er automatisch ein Element der ersten Arbeitsbereich (Index 0). Wenn ein Element erstellen und ihn in einem bestimmten Arbeitsbereich platziert werden sollen, müssen Sie das Element zu erstellen, und verschieben Sie sie in den gewünschten Arbeitsbereich mit einem Aufruf von [SetItemPosition](../mfc/reference/clistctrl-class.md#setitemposition). Unten im zweite Beispiel wird diese Technik veranschaulicht.  
  
 Das folgende Beispiel implementiert die vier Arbeitsbereiche (`rcWorkAreas`), gleicher Größe mit einem 10 Pixel breiten Rahmen jeder Arbeitsbereich, in einem Listensteuerelement (`m_WorkAreaListCtrl`).  
  
 [!code-cpp[NVC_MFCControlLadenDialog#20](../mfc/codesnippet/cpp/implementing-working-areas-in-list-controls_1.cpp)]  
  
 Der Aufruf von [ApproximateViewRect](../mfc/reference/clistctrl-class.md#approximateviewrect) wurde versucht, eine Schätzung des Gesamtbereichs erforderlich, um die Anzeige aller Elemente in einer Region zu erhalten. Diese Schätzung wird dann in vier Bereiche unterteilt und mit einem 5 Pixel breiten Rahmen aufgefüllt.  
  
 Im nächste Beispiel weist die vorhandenen Listenelemente für jede Gruppe (`rcWorkAreas`) und die Steuerelementansicht aktualisiert (`m_WorkAreaListCtrl`) um die Auswirkungen abzuschließen.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#21](../mfc/codesnippet/cpp/implementing-working-areas-in-list-controls_2.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CListCtrl](../mfc/using-clistctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

