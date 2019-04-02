---
title: Verwenden der Schaltfläche „Anwenden“
ms.date: 11/04/2016
helpviewer_keywords:
- Apply button in property sheet
- property sheets, Apply button
ms.assetid: 7e977015-59b8-406f-b545-aad0bfd8d55b
ms.openlocfilehash: 30ee549a334a684deeb4a845f2fc49ee8bbe11db
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58770836"
---
# <a name="handling-the-apply-button"></a>Verwenden der Schaltfläche „Anwenden“

Eigenschaftenblätter haben eine Funktion, die keine Standarddialogfelder: Sie ermöglichen den Benutzer, die Änderungen zu übernehmen, die sie vorgenommen haben, bevor Sie das Eigenschaftenblatt zu schließen. Dies erfolgt mithilfe der Schaltfläche "Übernehmen". Dieser Artikel beschreibt die Methoden, die Sie verwenden können, um diese Funktion ordnungsgemäß zu implementieren.

Modale Dialogfelder wenden diese Einstellungen in der Regel auf ein externes Objekt ein, klickt der Benutzer auf OK, um das Dialogfeld zu schließen. Das gleiche gilt für ein Eigenschaftenblatt: Wenn der Benutzer auf "OK" klickt, werden die neuen Einstellungen im Eigenschaftenblatt wirksam.

Allerdings sollten Sie dem Benutzer ermöglichen, Einstellungen zu speichern, ohne das Eigenschaftendialogfeld für Blatt schließen zu müssen. Dies ist die Funktion der Schaltfläche "anwenden". Schaltfläche "anwenden" gilt die aktuellen Einstellungen in allen von den Eigenschaftenseiten für das externe Objekt statt nur die aktuellen Einstellungen der aktuellen Seite anwenden.

Standardmäßig ist die Schaltfläche "anwenden" immer deaktiviert. Sie müssen Code schreiben, um die Schaltfläche "anwenden" jeweils richtigen Zeitpunkt zu aktivieren, und Sie müssen Code schreiben, implementieren Sie die Auswirkungen der anwenden, wie nachstehend beschrieben.

Wenn Sie nicht, die die Funktionalität für dem Benutzer zu bieten möchten, ist es nicht erforderlich, Schaltfläche "anwenden" zu entfernen. Sie können sie deaktiviert zu lassen, da häufig von Anwendungen, die Standardeigenschaft Blatt-Unterstützung in zukünftigen Versionen von Windows verwenden.

Aufrufen, um eine Seite als geändert melden, und aktivieren die Schaltfläche "Übernehmen", `CPropertyPage::SetModified( TRUE )`. Wenn eine der Seiten, die geändert wird, bleibt die Schaltfläche "anwenden" aktiviert ist, unabhängig davon, ob die derzeit aktive Seite geändert wurde.

Rufen Sie [CPropertyPage::SetModified](../mfc/reference/cpropertypage-class.md#setmodified) jedes Mal, wenn der Benutzer alle Einstellungen auf der Seite ändert. Eine Möglichkeit zum erkennen, wenn ein Benutzer eine Einstellung auf der Seite ändert ist Handler für wertänderungen von Benachrichtigungen für jedes der Steuerelemente auf der Eigenschaftenseite implementieren, z.B. **EN_CHANGE-Ereignis** oder **BN_CLICKED**.

Um die Auswirkungen der Schaltfläche "anwenden" implementieren, muss das Eigenschaftenblatt der Besitzer oder ein anderes externes Objekt in der Anwendung, zum Anwenden der aktuellen Einstellungen auf den Eigenschaftenseiten informieren. Zur gleichen Zeit, sollte das Eigenschaftenblatt die Schaltfläche "anwenden" deaktivieren, indem Aufrufen `CPropertyPage::SetModified( FALSE )` für alle Seiten, die die Änderungen auf das externe Objekt angewendet.

Ein Beispiel dieses Prozesses finden Sie im allgemeinen MFC-Beispiel [PROPDLG](../overview/visual-cpp-samples.md).

## <a name="see-also"></a>Siehe auch

[Eigenschaftenblätter](../mfc/property-sheets-mfc.md)
