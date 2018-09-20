---
title: Eigenschaftenblätter als Assistenten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- property sheets, as wizards
ms.assetid: 1ea66ecb-23b0-484a-838d-58671a2999b5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 73b6b0462012fc54b3bd6f2cb22422f5b1431288
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46374209"
---
# <a name="property-sheets-as-wizards"></a>Eigenschaftenblätter als Assistenten

Ein wesentliches Merkmal von einem Eigenschaftenblatt des Assistenten ist, dass die Navigation mit Schaltflächen "Weiter" oder "zurück, Fertig stellen" und "Abbrechen" anstelle von Registerkarten bereitgestellt wird. Sie aufrufen müssen [CPropertySheet::SetWizardMode](../mfc/reference/cpropertysheet-class.md#setwizardmode) vor dem Aufruf [CPropertySheet:: DoModal](../mfc/reference/cpropertysheet-class.md#domodal) auf das Eigenschaftenblattobjekt, um dieses Feature nutzen.

Der Benutzer erhält die gleiche [CPropertyPage::OnSetActive](../mfc/reference/cpropertypage-class.md#onsetactive) und [CPropertyPage:: OnKillActive](../mfc/reference/cpropertypage-class.md#onkillactive) Benachrichtigungen beim Verschieben von einer Seite zu einer anderen Seite. Weiter "und" Fertig stellen Schaltflächen schließen sich gegenseitig aus; Das heißt, wird nur einer von ihnen zu einem Zeitpunkt angezeigt. Klicken Sie auf der ersten Seite sollte die Schaltfläche "Weiter" aktiviert sein. Wenn der Benutzer auf der letzten Seite ist, sollte die Schaltfläche "Fertig stellen" aktiviert werden. Dies wird nicht automatisch vom Framework durchgeführt. Muss aufgerufen werden [CPropertySheet::SetWizardButton](../mfc/reference/cpropertysheet-class.md#setwizardbuttons) auf der letzten Seite, um dies zu erreichen.

Zum Anzeigen aller die Standardschaltflächen Standardschaltflächen zeigen die Schaltfläche "Fertig stellen", und verschieben die Schaltfläche "Weiter". Verschieben Sie dann die Schaltfläche "zurück" auf, sodass seiner relative Position auf die Schaltfläche "Weiter" verwaltet wird.

## <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#5](../mfc/codesnippet/cpp/property-sheets-as-wizards_1.cpp)]

## <a name="see-also"></a>Siehe auch

[Eigenschaftenblätter](../mfc/property-sheets-mfc.md)

