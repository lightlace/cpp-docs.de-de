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
ms.openlocfilehash: 9a1d42d129ab7b7d2e98ae1126b8f32f68b1f356
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2018
ms.locfileid: "36931826"
---
# <a name="processing-notification-messages-in-a-rebar-control"></a>Verarbeiten von Benachrichtigungsmeldungen in einem Grundleisten-Steuerelement
Erstellen Sie in der übergeordneten Klasse Grundleisten-Steuerelement, ein `OnChildNotify` Handlerfunktion mit einer Switch-Anweisung für jedes Grundleisten-Steuerelement (`CReBarCtrl`) benachrichtigungsmeldungen, die Sie behandeln möchten. Benachrichtigungen werden an das übergeordnete Fenster gesendet, wenn der Benutzer Objekte über die Grundleisten-Steuerelement Änderungen das Layout der rebarbereichen, löscht Lieblingsbands zieht, aus dem Grundleistensteuerelement, und so weiter.  
  
 Die folgenden benachrichtigungsmeldungen können durch das Grundleisten-Steuerelementobjekt gesendet werden:  
  
-   RBN_AUTOSIZE gesendet, von einem Grundleistensteuerelement (erstellt mit dem Format RBS_AUTOSIZE) Wenn die Infoleiste automatisch angepasst.  
  
-   RBN_BEGINDRAG, die von einem Grundleisten-Steuerelement, wenn der Benutzer beginnt, ziehen ein Band gesendet werden.  
  
-   RBN_CHILDSIZE, die von einem Grundleisten-Steuerelement beim Ändern der Größe des Bands untergeordnetes Fenster gesendet werden.  
  
-   RBN_DELETEDBAND wird gesendet, von einem Grundleistensteuerelement, nachdem ein Band gelöscht wurde.  
  
-   RBN_DELETINGBAND wird gesendet, von einem Grundleisten-Steuerelement, wenn ein Band gelöscht werden sollen.  
  
-   RBN_ENDDRAG, die von einem Grundleisten-Steuerelement, wenn der Benutzer den Ziehvorgang für ein Band gesendet werden.  
  
-   RBN_GETOBJECT wird gesendet, von einem Grundleistensteuerelement (erstellt mit dem Format RBS_REGISTERDROP) Wenn ein Objekt über ein Band in das Steuerelement gezogen wird.  
  
-   RBN_HEIGHTCHANGE wird gesendet, von einem Grundleisten-Steuerelement, wenn seine Höhe geändert wurde.  
  
-   RBN_LAYOUTCHANGED wird gesendet, von einem Grundleisten-Steuerelement, wenn der Benutzer das Layout der Bänder des Steuerelements ändert.  
  
 Weitere Informationen zu dieser Benachrichtigungen, finden Sie unter [Grundleisten-Steuerelementverweis](http://msdn.microsoft.com/library/windows/desktop/bb774375) im Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CReBarCtrl](../mfc/using-crebarctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

