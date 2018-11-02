---
title: Eigenschaftenblätter als Assistenten
ms.date: 11/04/2016
helpviewer_keywords:
- property sheets, as wizards
ms.assetid: 1ea66ecb-23b0-484a-838d-58671a2999b5
ms.openlocfilehash: e8ba740d31681de214d2a497bc2694a94d09d84d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50542622"
---
# <a name="property-sheets-as-wizards"></a>Eigenschaftenblätter als Assistenten

Ein wesentliches Merkmal von einem Eigenschaftenblatt des Assistenten ist, dass die Navigation mit Schaltflächen "Weiter" oder "zurück, Fertig stellen" und "Abbrechen" anstelle von Registerkarten bereitgestellt wird. Sie aufrufen müssen [CPropertySheet::SetWizardMode](../mfc/reference/cpropertysheet-class.md#setwizardmode) vor dem Aufruf [CPropertySheet:: DoModal](../mfc/reference/cpropertysheet-class.md#domodal) auf das Eigenschaftenblattobjekt, um dieses Feature nutzen.

Der Benutzer erhält die gleiche [CPropertyPage::OnSetActive](../mfc/reference/cpropertypage-class.md#onsetactive) und [CPropertyPage:: OnKillActive](../mfc/reference/cpropertypage-class.md#onkillactive) Benachrichtigungen beim Verschieben von einer Seite zu einer anderen Seite. Weiter "und" Fertig stellen Schaltflächen schließen sich gegenseitig aus; Das heißt, wird nur einer von ihnen zu einem Zeitpunkt angezeigt. Klicken Sie auf der ersten Seite sollte die Schaltfläche "Weiter" aktiviert sein. Wenn der Benutzer auf der letzten Seite ist, sollte die Schaltfläche "Fertig stellen" aktiviert werden. Dies wird nicht automatisch vom Framework durchgeführt. Muss aufgerufen werden [CPropertySheet::SetWizardButton](../mfc/reference/cpropertysheet-class.md#setwizardbuttons) auf der letzten Seite, um dies zu erreichen.

Zum Anzeigen aller die Standardschaltflächen Standardschaltflächen zeigen die Schaltfläche "Fertig stellen", und verschieben die Schaltfläche "Weiter". Verschieben Sie dann die Schaltfläche "zurück" auf, sodass seiner relative Position auf die Schaltfläche "Weiter" verwaltet wird.

## <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#5](../mfc/codesnippet/cpp/property-sheets-as-wizards_1.cpp)]

## <a name="see-also"></a>Siehe auch

[Eigenschaftenblätter](../mfc/property-sheets-mfc.md)

