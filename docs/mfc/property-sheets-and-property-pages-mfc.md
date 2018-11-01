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
ms.openlocfilehash: 971b8cde1560e54f87269e8b85a41cdec55c091d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50445395"
---
# <a name="property-sheets-and-property-pages-mfc"></a>Eigenschaftenblätter und Eigenschaftenseiten (MFC)

Eine MFC [Dialogfeld](../mfc/dialog-boxes.md) wurden auf einen Blick "Registerkarte Dialogfeld" durch die Aufnahme Eigenschaftenblätter und Eigenschaftenseiten. Ein "Eigenschaftenblatt" in MFC aufgerufen, wird diese Art von Dialogfeld, ähnlich wie in vielen Dialogfeldern in Microsoft Word, Excel und Visual C++ enthält einen Stapel von Registerkarten Sheets, ähnlich wie ein Stapel von Dateien-Ordner, der von vorne nach hinten oder eine Gruppe von überlappenden Fenstern angezeigt. Steuerelemente auf die Front-Registerkarte sind sichtbar. nur die bezeichnete Registerkarte wird auf die rückseitigen Registerkarten angezeigt. Eigenschaftenblätter sind besonders nützlich für das Verwalten einer großen Anzahl von Eigenschaften oder Einstellungen, die recht ordentlich zu mehreren Gruppen gehören. In der Regel kann ein Eigenschaftenblatt eine Benutzeroberfläche vereinfachen und Ersetzen Sie dabei mehrere separate Dialogfelder.

Ab MFC 4.0 werden die Eigenschaftenblätter und Eigenschaftenseiten implementiert, über die allgemeinen Steuerelemente angezeigt, die die im Lieferumfang von Windows 95 und Windows NT, Version 3.51 und höher.

Eigenschaftenblätter werden mit den Klassen implementiert [CPropertySheet](../mfc/reference/cpropertysheet-class.md) und [CPropertyPage](../mfc/reference/cpropertypage-class.md) (beschrieben der *MFC-Referenz*). `CPropertySheet` definiert das Dialogfeld allgemeine, die mehrere "Seiten" auf der Grundlage enthalten können `CPropertyPage`.

Informationen zum Erstellen und Verwenden von Eigenschaftenseiten, finden Sie im Thema [Eigenschaftenblätter](../mfc/property-sheets-mfc.md).

## <a name="see-also"></a>Siehe auch

[Dialogfelder](../mfc/dialog-boxes.md)<br/>
[Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)<br/>
[Eigenschaftenblätter und Eigenschaftenseiten in MFC](../mfc/property-sheets-and-property-pages-in-mfc.md)<br/>
[Datenaustausch](../mfc/exchanging-data.md)<br/>
[Erstellen eines nicht modalen Eigenschaftenblatts](../mfc/creating-a-modeless-property-sheet.md)<br/>
[Verwenden der Schaltfläche „Anwenden“](../mfc/handling-the-apply-button.md)

