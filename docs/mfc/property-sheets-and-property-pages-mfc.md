---
title: Eigenschaftenblätter und Eigenschaftenseiten (MFC)
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], tabs
- property pages [MFC], property sheets
- CPropertyPage class [MFC], property sheets and pages
- CPropertySheet class [MFC], property sheets and pages
- property sheets, propert pages
ms.assetid: de8fea12-6c35-4cef-8625-b8073a379446
ms.openlocfilehash: 5d4fd1c957b7f4d0d6ad10379a448309743aa11a
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685077"
---
# <a name="property-sheets-and-property-pages-mfc"></a>Eigenschaftenblätter und Eigenschaftenseiten (MFC)

Ein MFC- [Dialogfeld](../mfc/dialog-boxes.md) kann einen "Registerkarten Dialogfeld" durch die Einbindung von Eigenschaften Blättern und Eigenschaften Seiten aufnehmen. Diese Art von Dialogfeld, ähnlich vielen Dialogfeldern in Microsoft Word, Excel und Visual C++, wird in MFC als "Eigenschaften Blatt" bezeichnet und enthält einen Stapel von Blättern im Registerkarten Format, ähnlich wie ein Stapel von Datei Ordnern, die von vorne nach hinten oder einer Gruppe von kaskadierenden Fenstern angezeigt werden. Steuerelemente auf der Registerkarte "Front" sind sichtbar. auf den hinteren Registerkarten ist nur die Registerkarte beschriftet sichtbar. Eigenschaften Blätter sind besonders nützlich, um eine große Anzahl von Eigenschaften oder Einstellungen zu verwalten, die in verschiedene Gruppen unterteilt sind. In der Regel kann ein Eigenschaften Blatt eine Benutzeroberfläche vereinfachen, indem mehrere separate Dialogfelder ersetzt werden.

Ab MFC-Version 4,0 werden Eigenschaften Blätter und Eigenschaften Seiten mithilfe der allgemeinen Steuerelemente implementiert, die in Windows 95 und Windows NT, Version 3,51 und höher, enthalten sind.

Eigenschaften Blätter werden mit den Klassen [CPropertySheet](../mfc/reference/cpropertysheet-class.md) und [CPropertyPage](../mfc/reference/cpropertypage-class.md) (beschrieben in der *MFC-Referenz*) implementiert. `CPropertySheet` definiert das gesamte Dialogfeld, in dem mehrere "Seiten" basierend auf `CPropertyPage` enthalten sein können.

Weitere Informationen zum Erstellen und arbeiten mit Eigenschaften Blättern finden Sie im Thema [Eigenschaften Blätter](../mfc/property-sheets-mfc.md).

## <a name="see-also"></a>Siehe auch

[Dialogfelder](../mfc/dialog-boxes.md)<br/>
[Arbeiten mit Dialog Feldern in MFC](../mfc/life-cycle-of-a-dialog-box.md)<br/>
[Eigenschaftenblätter und Eigenschaftenseiten in MFC](../mfc/property-sheets-and-property-pages-in-mfc.md)<br/>
[Datenaustausch](../mfc/exchanging-data.md)<br/>
[Erstellen eines nicht modalen Eigenschaftenblatts](../mfc/creating-a-modeless-property-sheet.md)<br/>
[Verwenden der Schaltfläche „Anwenden“](../mfc/handling-the-apply-button.md)
