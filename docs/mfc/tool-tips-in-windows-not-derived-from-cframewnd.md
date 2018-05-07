---
title: QuickInfos in Fenstern, die nicht von CFrameWnd abgeleitet | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- enabling tool tips [MFC]
- TOOLTIPTEXT structure [MFC]
- Help [MFC], tool tips for controls
- TTN_NEEDTEXT message [MFC]
- controls [MFC], tool tips
- handler functions [MFC], tool tips
ms.assetid: cad5ef0f-02e3-4151-ad0d-3d42e6932b0e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 34eb8f0b7394828782a3d0f9ed1ca44fb5731af6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="tool-tips-in-windows-not-derived-from-cframewnd"></a>QuickInfos in Fenstern, die nicht von CFrameWnd abgeleitet sind
Diese Artikelreihe enthält aktiviert QuickInfos für Steuerelemente in einem Fenster, die nicht von abgeleitet ist [CFrameWnd](../mfc/reference/cframewnd-class.md). Der Artikel [Symbolleisten QuickInfos](../mfc/toolbar-tool-tips.md) enthält Informationen über QuickInfos für Steuerelemente in einem `CFrameWnd`.  
  
 In dieser Familie Artikel behandelten Themen gehören:  
  
-   [Erstellen von QuickInfos](../mfc/enabling-tool-tips.md)  
  
-   [Behandeln der TTN_NEEDTEXT-Benachrichtigung für QuickInfos](../mfc/handling-ttn-needtext-notification-for-tool-tips.md)  
  
-   [TOOLTIPTEXT-Struktur](../mfc/tooltiptext-structure.md)  
  
 QuickInfos werden automatisch angezeigt, für Schaltflächen und andere Steuerelemente in ein übergeordnetes Fenster enthaltenen abgeleitet `CFrameWnd`. Grund hierfür ist, `CFrameWnd` verfügt über einen Standardhandler für das [TTN_GETDISPINFO](http://msdn.microsoft.com/library/windows/desktop/bb760269) Benachrichtigung, die verarbeitet **TTN_NEEDTEXT** Benachrichtigungen vom Tool Tipp Steuerelemente-Steuerelementen zugeordnet.  
  
 Jedoch diese Standard-Handler wird nicht aufgerufen, wenn die **TTN_NEEDTEXT** Benachrichtigung wird gesendet, aus einer einem Steuerelement in einem Fenster, die nicht zugeordnete QuickInfo-Steuerelement eine `CFrameWnd`, z. B. ein Steuerelement in einem Dialogfeld oder eine Formularansicht. Daher ist es erforderlich, eine Ereignishandler-Funktion für bereitzustellen der **TTN_NEEDTEXT** Benachrichtigung, um QuickInfos für die untergeordneten Steuerelemente anzuzeigen.  
  
 Die standardmäßigen QuickInfos für Ihre Windows durch [CWnd:: EnableToolTips](../mfc/reference/cwnd-class.md#enabletooltips) keinen Text zugeordnet. Zum Abrufen von Text für die QuickInfo angezeigt, die **TTN_NEEDTEXT** Benachrichtigung wird an das QuickInfo-Steuerelement des übergeordneten Fensters gesendet, kurz bevor das QuickInfo-Fenster angezeigt wird. Wenn kein Handler für diese Nachricht einige Wert zuzuweisen der **PszText** Mitglied der **TOOLTIPTEXT** -Struktur, die kein Text für die QuickInfo angezeigt werden.  
  
## <a name="see-also"></a>Siehe auch  
 [QuickInfos](../mfc/tool-tips.md)

