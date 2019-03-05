---
title: Implementieren von Arbeitsbereichen in Listensteuerelementen
ms.date: 11/04/2016
helpviewer_keywords:
- list controls [MFC], working areas
- working areas in list control [MFC]
ms.assetid: fbbb356b-3359-4348-8603-f1cb114cadde
ms.openlocfilehash: 01b166243c9032a113d46ff297b9f6e53429da21
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57281602"
---
# <a name="implementing-working-areas-in-list-controls"></a>Implementieren von Arbeitsbereichen in Listensteuerelementen

Standardmäßig ordnet einem Steuerelement alle Elemente in einer Weise Standardraster. Allerdings wird eine andere Methode unterstützt, arbeiten Bereiche, die die Listenelemente in rechteckige Gruppen angeordnet. Für ein Bild eines Steuerelements, das Arbeitsbereiche implementiert, finden Sie unter Verwendung Listenansicht-Steuerelemente im Windows SDK.

> [!NOTE]
>  Arbeitsbereiche sind sichtbar, nur, wenn das Strukturelement-Steuerelement im Symbol "oder" kleines Symbol-Modus befindet. Alle aktuellen Arbeitsbereiche werden jedoch beibehalten, wenn die Ansicht in den Bericht oder eine Liste-Modus aktiviert ist.

Arbeitsbereiche können verwendet werden, zum Anzeigen eines leeren Rahmens (auf die Links, oben und/oder rechts von den Elementen) oder dazu führen, dass eine horizontale Schiebeleiste angezeigt, wenn es normalerweise wäre nicht möglich. Eine weitere häufige Verwendung ist die Erstellung mehrerer Arbeitsbereiche auf die Elemente verschoben oder gelöscht werden können. Mit dieser Methode können Sie Bereiche erstellen, in einer einzigen Ansicht, die unterschiedliche Bedeutungen haben. Der Benutzer konnte klicken Sie dann die Elemente kategorisieren, indem Sie sie in einer anderen Region zu platzieren. Ein Beispiel hierfür wäre eine Ansicht eines Dateisystems, die einen Bereich für Dateien mit Lese-/Schreibzugriff und ein weiterer Bereich für schreibgeschützte Dateien aufweist. Wenn ein Element mit Datei in den schreibgeschützten Bereich verschoben wurden, wird es automatisch schreibgeschützt werden. Verschieben einer Datei im Bereich "schreibgeschützt" in den Bereich von Lese-/Schreibzugriff, würde die Datei Lese-/Schreibzugriff machen.

`CListCtrl` stellt mehrere Memberfunktionen zum Erstellen und Verwalten von Arbeitsbereichen in Listensteuerelementen bereit. [GetWorkAreas](../mfc/reference/clistctrl-class.md#getworkareas) und [SetWorkAreas](../mfc/reference/clistctrl-class.md#setworkareas) abzurufen und festzulegen, ein Array von `CRect` Objekte (oder `RECT` Strukturen), der für das Listensteuerelement der derzeit implementierten Arbeitsbereichen gespeichert. Darüber hinaus [ruft GetNumberOfWorkAreas](../mfc/reference/clistctrl-class.md#getnumberofworkareas) Ruft die aktuelle Anzahl von Arbeitsbereichen für das Listensteuerelement (standardmäßig null).

## <a name="items-and-working-areas"></a>Elemente und Arbeitsbereiche

Wenn ein Arbeitsbereich erstellt wird, werden die Elemente, die innerhalb der Arbeitsbereich ihrer Mitglieder. Wenn ein Element in einem Arbeitsbereich verschoben wird, wird es auf ähnliche Weise ein Mitglied über den Arbeitsbereich auf dem er verschoben wurde. Wenn ein Element nicht in keinem Arbeitsbereich liegt, wird es automatisch ein Element der ersten (Index 0) Arbeitsbereich. Wenn ein Element zu erstellen, und lassen Sie sie in einem bestimmten Arbeitsbereich platziert werden sollen, müssen Sie das Element erstellt werden, und verschieben Sie sie in den gewünschten Arbeitsbereich mit einem Aufruf von [SetItemPosition](../mfc/reference/clistctrl-class.md#setitemposition). Das zweite Beispiel unten wird diese Technik veranschaulicht.

Das folgende Beispiel implementiert vier Arbeitsbereiche (`rcWorkAreas`), gleicher Größe mit einem 10 Pixel breiten Rahmen jeder Arbeitsbereich, in einem Listensteuerelement (`m_WorkAreaListCtrl`).

[!code-cpp[NVC_MFCControlLadenDialog#20](../mfc/codesnippet/cpp/implementing-working-areas-in-list-controls_1.cpp)]

Der Aufruf von [ApproximateViewRect](../mfc/reference/clistctrl-class.md#approximateviewrect) wurde versucht, eine Schätzung der Fläche erforderlich, um das Anzeigen aller Elemente in einer Region zu erhalten. Diese Schätzung ist dann in vier Bereiche unterteilt und mit einem 5 Pixel breiten Rahmen aufgefüllt.

Im nächste Beispiel weist die vorhandenen Listenelemente für jede Gruppe (`rcWorkAreas`) und aktualisiert die Ansicht des Steuerelement (`m_WorkAreaListCtrl`) um den Effekt abzuschließen.

[!code-cpp[NVC_MFCControlLadenDialog#21](../mfc/codesnippet/cpp/implementing-working-areas-in-list-controls_2.cpp)]

## <a name="see-also"></a>Siehe auch

[Verwenden von CListCtrl](../mfc/using-clistctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
