---
title: "Eigenschaftenblätter als Assistenten | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: property sheets, as wizards
ms.assetid: 1ea66ecb-23b0-484a-838d-58671a2999b5
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 65aedc5dbeb8a740d5713983f66eefe693864937
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="property-sheets-as-wizards"></a>Eigenschaftenblätter als Assistenten
Ein wichtiges Merkmal eines Eigenschaftenblatts Assistenten ist, dass Navigation weiter oder "Fertig stellen", zurück, und "Abbrechen" Schaltflächen anstelle von Registerkarten zur Verfügung steht. Aufrufen, müssen Sie [CPropertySheet::SetWizardMode](../mfc/reference/cpropertysheet-class.md#setwizardmode) vor dem Aufruf [CPropertySheet:: DoModal](../mfc/reference/cpropertysheet-class.md#domodal) auf das Blatt Eigenschaftenobjekt dieses Feature nutzen.  
  
 Der Benutzer erhält die gleiche [CPropertyPage::OnSetActive](../mfc/reference/cpropertypage-class.md#onsetactive) und [CPropertyPage:: OnKillActive](../mfc/reference/cpropertypage-class.md#onkillactive) Benachrichtigungen beim Verschieben von einer Seite zu einer anderen Seite. Weiter und Fertig stellen Schaltflächen schließen sich gegenseitig aus; d. h. wird nur eine Kopie zu einem Zeitpunkt angezeigt werden. Auf der ersten Seite sollte die Schaltfläche "Weiter" aktiviert sein. Wenn der Benutzer auf die letzte Seite ist, sollte auf "Fertig stellen" aktiviert werden. Dies wird nicht automatisch vom Framework durchgeführt. Müssen Sie anrufen [CPropertySheet::SetWizardButton](../mfc/reference/cpropertysheet-class.md#setwizardbuttons) auf der letzten Seite aus, um dies zu erreichen.  
  
 Zum Anzeigen aller die Standardschaltflächen für Standardschaltflächen anzeigen "Fertig stellen", und verschieben die Schaltfläche "Weiter". Verschieben Sie dann die Schaltfläche "zurück" auf, so dass seiner relative Position auf die Schaltfläche "Weiter" verwaltet wird.  
  
## <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#5](../mfc/codesnippet/cpp/property-sheets-as-wizards_1.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Eigenschaftenblätter](../mfc/property-sheets-mfc.md)

