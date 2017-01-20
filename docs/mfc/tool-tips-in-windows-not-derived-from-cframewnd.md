---
title: "QuickInfos in Fenstern, die nicht von CFrameWnd abgeleitet sind"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Steuerelemente [MFC], QuickInfos"
  - "Erstellen von QuickInfos"
  - "Handlerfunktionen, QuickInfos"
  - "Hilfe, QuickInfos für Steuerelemente"
  - "TOOLTIPTEXT-Struktur"
  - "TTN_NEEDTEXT-Meldung"
ms.assetid: cad5ef0f-02e3-4151-ad0d-3d42e6932b0e
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# QuickInfos in Fenstern, die nicht von CFrameWnd abgeleitet sind
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Diese Artikelfamilie enthält das Einrichten von QuickInfos für die Steuerelemente, die in einem Fenster enthalten sind, die nicht aus [CFrameWnd](../mfc/reference/cframewnd-class.md) abgeleitet wird.  Der Artikel [Symbolleisten\-QuickInfo](../mfc/toolbar-tool-tips.md) setzt Informationen zur QuickInfo für Steuerelemente in `CFrameWnd` fest.  
  
 Themen beschrieben in diesem Artikelfamilieneinschließung:  
  
-   [Aktivieren von QuickInfos](../mfc/enabling-tool-tips.md)  
  
-   [Benachrichtigung der Behandlungs\-TTN NEEDTEXT für QuickInfos](../mfc/handling-ttn-needtext-notification-for-tool-tips.md)  
  
-   [Die TOOLTIPTEXT\-Struktur](../mfc/tooltiptext-structure.md)  
  
 QuickInfos werden automatisch für die Schaltflächen und anderen Steuerelementen angezeigt, die in einem übergeordneten Fenster enthalten werden, das von `CFrameWnd` abgeleitet wird.  Dies ist, da `CFrameWnd` einen Standardhandler für die Benachrichtigung [TTN\_GETDISPINFO](http://msdn.microsoft.com/library/windows/desktop/bb760269) verfügt, die **TTN\_NEEDTEXT** Benachrichtigungen von ToolTip\-Steuerelemente behandelt, die mit Steuerelementen verbunden werden.  
  
 Allerdings wird dieser Standardhandler nicht aufgerufen, wenn die **TTN\_NEEDTEXT**  Benachrichtigung von einem ToolTip\-Steuerelement gesendet wird, die einem Steuerelement in einem Fenster zugeordnet wird, das nicht `CFrameWnd` ist, wie ein Steuerelement in einem Dialogfeld oder einer Formularansicht.  Daher ist es erforderlich, für Sie eine Handlerfunktion für die **TTN\_NEEDTEXT** Benachrichtigung bereitzustellen, um QuickInfos für Steuerelemente anzuzeigen.  
  
 Die Standardquickinfo, die für die Fenster von [CWnd::EnableToolTips](../Topic/CWnd::EnableToolTips.md) bereitgestellt werden, haben nicht den Text, der mit diesen zugeordnet ist.  Um Text abzurufen wird gesendet sodass die QuickInfo, die **TTN\_NEEDTEXT** Benachrichtigung auf das übergeordnete Fenster des ToolTip\-Steuerelements anzeigt bevor das QuickInfo\-Fenster angezeigt wird.  Wenn kein Handler gibt, sodass diese Meldung das **pszText**\-Member der **TOOLTIPTEXT**\-Struktur etwas Wert zugewiesen wird, gibt es keinen Text, der für die QuickInfo angezeigt wird.  
  
## Siehe auch  
 [QuickInfos](../mfc/tool-tips.md)