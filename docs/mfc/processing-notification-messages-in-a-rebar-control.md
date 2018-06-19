---
title: Verarbeiten von Benachrichtigungsmeldungen in einem Grundleisten-Steuerelement | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- RBN_ notification messages, description of
- CReBarCtrl class [MFC], notification messages sent by
- RBN_ notification messages [MFC]
- notifications [MFC], CReBarCtrl
ms.assetid: 40f43a60-0c18-4d8d-8fab-213a095624f9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a06df0bdfe8d1b81b4285fc86378f3da99882698
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33348415"
---
# <a name="processing-notification-messages-in-a-rebar-control"></a>Verarbeiten von Benachrichtigungsmeldungen in einem Grundleisten-Steuerelement
Erstellen Sie in der übergeordneten Klasse Grundleisten-Steuerelement, ein `OnChildNotify` Handlerfunktion mit einer Switch-Anweisung für jedes Grundleisten-Steuerelement (`CReBarCtrl`) benachrichtigungsmeldungen, die Sie behandeln möchten. Benachrichtigungen werden an das übergeordnete Fenster gesendet, wenn der Benutzer Objekte über die Grundleisten-Steuerelement Änderungen das Layout der rebarbereichen, löscht Lieblingsbands zieht, aus dem Grundleistensteuerelement, und so weiter.  
  
 Die folgenden benachrichtigungsmeldungen können durch das Grundleisten-Steuerelementobjekt gesendet werden:  
  
-   **RBN_AUTOSIZE** gesendet, die von einem Grundleistensteuerelement (erstellt mit der **RBS_AUTOSIZE** Stil) Wenn Infoleiste automatisch angepasst.  
  
-   **RBN_BEGINDRAG** von einem Grundleisten-Steuerelement gesendet wird, wenn der Benutzer beginnt, ziehen ein Band.  
  
-   **RBN_CHILDSIZE** von einem Grundleistensteuerelement gesendet wird, wenn ein Band untergeordnetes Fenster angepasst wird.  
  
-   **RBN_DELETEDBAND wird** von einem Grundleisten-Steuerelement gesendet wird, nachdem ein Band gelöscht wurde.  
  
-   **RBN_DELETINGBAND wird** von einem Grundleisten-Steuerelement gesendet wird, wenn ein Band gelöscht werden sollen.  
  
-   **RBN_ENDDRAG** von einem Grundleisten-Steuerelement gesendet wird, wenn der Benutzer den Ziehvorgang für ein Band.  
  
-   **RBN_GETOBJECT wird** von einem Grundleisten-Steuerelement gesendet (erstellt mit dem **RBS_REGISTERDROP** Stil) Wenn ein Objekt über ein Band in das Steuerelement gezogen wird.  
  
-   **RBN_HEIGHTCHANGE wird** von einem Grundleisten-Steuerelement gesendet wird, wenn seine Höhe geändert wurde.  
  
-   **RBN_LAYOUTCHANGED wird** von einem Grundleisten-Steuerelement gesendet wird, wenn der Benutzer das Layout der Bänder des Steuerelements ändert.  
  
 Weitere Informationen zu dieser Benachrichtigungen, finden Sie unter [Grundleisten-Steuerelementverweis](http://msdn.microsoft.com/library/windows/desktop/bb774375) im Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CReBarCtrl](../mfc/using-crebarctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

