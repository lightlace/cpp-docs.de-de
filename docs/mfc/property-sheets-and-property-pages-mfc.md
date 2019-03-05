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
ms.openlocfilehash: 7ff2851cc4ed04a64f1a49d68b6e3143b5edccd8
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57278760"
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
