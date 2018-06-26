---
title: Die Schaltfläche "anwenden" | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Apply button in property sheet
- property sheets, Apply button
ms.assetid: 7e977015-59b8-406f-b545-aad0bfd8d55b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: acbbd4ec8e075abbcbbeeaf199cae0d3a8d3c41a
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2018
ms.locfileid: "36930451"
---
# <a name="handling-the-apply-button"></a>Verwenden der Schaltfläche „Anwenden“
Eigenschaftenblätter haben eine Funktion, die keine Dialogfelder "standard": Benutzer können zum Anwenden von Änderungen sie vorgenommen haben, bevor das Eigenschaftenblatt schließen. Dies erfolgt mithilfe der Schaltfläche "anwenden". Dieser Artikel beschreibt die Methoden beschrieben, die Sie verwenden können, um diese Funktion ordnungsgemäß zu implementieren.  
  
 Modale Dialogfelder wenden diese Einstellungen in der Regel auf ein externes Objekt, klickt der Benutzer auf OK, um das Dialogfeld zu schließen. Dasselbe gilt für ein Eigenschaftenblatt: Wenn der Benutzer auf OK klickt, werden die neuen Einstellungen im Eigenschaftenblatt wirksam.  
  
 Möglicherweise möchten jedoch der Benutzer auf Einstellungen zu speichern, ohne das Blatt Eigenschaftendialogfeld zu schließen. Dies ist die Funktion der Schaltfläche "anwenden". Schaltfläche "anwenden" gilt die aktuellen Einstellungen in allen von den Eigenschaftenseiten für das externe Objekt, statt nur die aktuellen Einstellungen der aktiven Seite anwenden.  
  
 Standardmäßig ist die Schaltfläche "anwenden" stets deaktiviert. Sie müssen Code schreiben, um die Schaltfläche "anwenden" zu den entsprechenden Zeitpunkten zu aktivieren, und Sie müssen Code schreiben, um die Auswirkung der übernehmen, implementieren wie nachstehend beschrieben.  
  
 Wenn Sie nicht die Funktionalität für dem Benutzer bieten möchten, ist es nicht erforderlich, entfernen die Schaltfläche "anwenden". Sie können sie deaktiviert zu lassen, da Anwendungen gemeinsam sind, die Standardeigenschaft Unterstützung zur Verfügung, in zukünftigen Versionen von Windows verwenden.  
  
 Aufrufen, um eine Seite als geändert gemeldet, und aktivieren die Schaltfläche "anwenden", `CPropertyPage::SetModified( TRUE )`. Wenn eine der Seiten, die geändert wird, bleibt die Schaltfläche "anwenden" aktiviert ist, unabhängig davon, ob die derzeit aktive Seite geändert wurde.  
  
 Rufen Sie [CPropertyPage::SetModified](../mfc/reference/cpropertypage-class.md#setmodified) sobald sich der Benutzer alle Einstellungen auf der Seite ändert. Eine Möglichkeit zum erkennen, wenn ein Benutzer eine Einstellung auf der Seite ändert implementieren, z. B. Änderung Benachrichtigungshandler für jedes der Steuerelemente auf der Eigenschaftenseite werden **EN_CHANGE** oder **BN_CLICKED**.  
  
 Um die Auswirkung der Schaltfläche "anwenden" zu implementieren, muss das Eigenschaftenblatt Besitzer oder einem anderen externen Objekt in der Anwendung, zum Anwenden der aktuellen Einstellungen auf den Eigenschaftenseiten mitteilen. Zur gleichen Zeit sollten Eigenschaftenblatt Schaltfläche "anwenden" deaktivieren, durch den Aufruf `CPropertyPage::SetModified( FALSE )` für alle Seiten, die die Änderungen auf das externe Objekt angewendet.  
  
 Ein Beispiel dieses Prozesses finden Sie im allgemeinen MFC-Beispiel [PROPDLG](../visual-cpp-samples.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Eigenschaftenblätter](../mfc/property-sheets-mfc.md)

