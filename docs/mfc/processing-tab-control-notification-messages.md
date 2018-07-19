---
title: Verarbeiten von Benachrichtigungsmeldungen des Registersteuerelements | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- notifications [MFC], tab controls
- CTabCtrl class [MFC], processing notifications
- notifications [MFC], processing in CTabCtrl
- processing notifications [MFC]
- tab controls [MFC], processing notifications
ms.assetid: 758ccb7a-9e73-48f8-9073-23f7cb09918c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 462d9177b1f6300eb356d052cbdfff3b85db86a1
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2018
ms.locfileid: "36928061"
---
# <a name="processing-tab-control-notification-messages"></a>Verarbeiten von Benachrichtigungsmeldungen des Registersteuerelements
Benutzer klicken auf Registerkarten oder Schaltflächen, das Registerkarten-Steuerelement ([CTabCtrl](../mfc/reference/ctabctrl-class.md)) sendet benachrichtigungsmeldungen an das übergeordnete Fenster. Behandeln Sie diese Nachrichten, wenn Sie darauf reagieren möchten. Klickt der Benutzer auf eine Registerkarte, sollten Sie z. B. gesteuert werden auf der Seite vor der Anzeige voreingestellt.  
  
 WM_NOTIFY-Meldungen aus dem Registerkarten-Steuerelement in Ihrer Klasse Ansichts- oder Dialogfeldobjekt verarbeiten. Verwenden des Eigenschaftenfensters zum Erstellen einer [OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify) Handlerfunktion mit einer Switch-Anweisung basierend auf der benachrichtigungsmeldung behandelt wird. Eine Liste der Benachrichtigungen, die ein Registerkarten-Steuerelement an das übergeordnete Fenster senden kann, finden Sie unter der **Benachrichtigungen** Abschnitt [Steuerelement Registerkartenverweis](http://msdn.microsoft.com/library/windows/desktop/bb760548) im Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CTabCtrl](../mfc/using-ctabctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

