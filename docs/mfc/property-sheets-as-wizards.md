---
title: Eigenschaftenblätter als Assistenten | Microsoft Docs
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
ms.openlocfilehash: 634359763f24e02987664fe3de1094e3e7fec64c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33347330"
---
# <a name="property-sheets-as-wizards"></a>Eigenschaftenblätter als Assistenten
Ein wichtiges Merkmal eines Eigenschaftenblatts Assistenten ist, dass Navigation weiter oder "Fertig stellen", zurück, und "Abbrechen" Schaltflächen anstelle von Registerkarten zur Verfügung steht. Aufrufen, müssen Sie [CPropertySheet::SetWizardMode](../mfc/reference/cpropertysheet-class.md#setwizardmode) vor dem Aufruf [CPropertySheet:: DoModal](../mfc/reference/cpropertysheet-class.md#domodal) auf das Blatt Eigenschaftenobjekt dieses Feature nutzen.  
  
 Der Benutzer erhält die gleiche [CPropertyPage::OnSetActive](../mfc/reference/cpropertypage-class.md#onsetactive) und [CPropertyPage:: OnKillActive](../mfc/reference/cpropertypage-class.md#onkillactive) Benachrichtigungen beim Verschieben von einer Seite zu einer anderen Seite. Weiter und Fertig stellen Schaltflächen schließen sich gegenseitig aus; d. h. wird nur eine Kopie zu einem Zeitpunkt angezeigt werden. Auf der ersten Seite sollte die Schaltfläche "Weiter" aktiviert sein. Wenn der Benutzer auf die letzte Seite ist, sollte auf "Fertig stellen" aktiviert werden. Dies wird nicht automatisch vom Framework durchgeführt. Müssen Sie anrufen [CPropertySheet::SetWizardButton](../mfc/reference/cpropertysheet-class.md#setwizardbuttons) auf der letzten Seite aus, um dies zu erreichen.  
  
 Zum Anzeigen aller die Standardschaltflächen für Standardschaltflächen anzeigen "Fertig stellen", und verschieben die Schaltfläche "Weiter". Verschieben Sie dann die Schaltfläche "zurück" auf, so dass seiner relative Position auf die Schaltfläche "Weiter" verwaltet wird.  
  
## <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#5](../mfc/codesnippet/cpp/property-sheets-as-wizards_1.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Eigenschaftenblätter](../mfc/property-sheets-mfc.md)

