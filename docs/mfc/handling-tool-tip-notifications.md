---
title: Behandeln von QuickInfo-Benachrichtigungen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- TOOLTIPTEXT structure [MFC]
- CToolBarCtrl class [MFC], handling notifications
- notifications [MFC], tool tips
- tool tips [MFC], notifications
ms.assetid: ddb93b5f-2e4f-4537-8053-3453c86e2bbb
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6d6ec102d38e91389fddb3faf4eb83ace9ba7129
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="handling-tool-tip-notifications"></a>Behandeln von QuickInfo-Benachrichtigungen
Geben Sie bei der `TBSTYLE_TOOLTIPS` Stil, die Symbolleiste erstellt und verwaltet ein QuickInfo-Steuerelement. Eine QuickInfo ist ein kleines Popupfenster, das eine Textzeile, beschreibt eine Symbolleisten-Schaltfläche enthält. Die QuickInfo wird ausgeblendet, erscheint nur, wenn der Benutzer fügt den Cursor auf einer Symbolleisten-Schaltfläche und bleibt es zumeist Sekunde. Die QuickInfo wird angezeigt, in der Nähe des Cursors.  
  
 Bevor die QuickInfo angezeigt wird, die **TTN_NEEDTEXT** Benachrichtigung auf der Symbolleiste Besitzerfenster gesendet, um den beschreibenden Text für die Schaltfläche abzurufen. Wenn die Symbolleiste Besitzerfenster ist eine `CFrameWnd` Fenster Tool Tipps ohne zusätzlichen Aufwand, angezeigt werden, da `CFrameWnd` verfügt über einen Standardhandler für die **TTN_NEEDTEXT** Benachrichtigung. Wenn die Symbolleiste Besitzerfenster nicht abgeleitet ist `CFrameWnd`, z. B. ein Dialogfeld oder Formular anzeigen, müssen Sie Hinzufügen eines Eintrags zur meldungszuordnung Ihres Besitzerfensters und geben Sie eine Benachrichtigung-Ereignishandler in der meldungszuordnung. Der Eintrag meldungszuordnung Ihres Besitzerfensters lautet wie folgt:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#40](../mfc/codesnippet/cpp/handling-tool-tip-notifications_1.cpp)]  
  
## <a name="remarks"></a>Hinweise  
 `memberFxn`  
 Die Memberfunktion aufgerufen werden, wenn diese Schaltfläche Text erforderlich ist.  
  
 Beachten Sie, dass die Id einer QuickInfo immer 0.  
  
 Zusätzlich zu den **TTN_NEEDTEXT** Benachrichtigung ein QuickInfo-Steuerelement Benachrichtigungen senden kann die folgenden zu einem Toolbar-Steuerelement:  
  
|Benachrichtigung|Bedeutung|  
|------------------|-------------|  
|**TTN_NEEDTEXTA**|QuickInfo-Steuerelement erfordert ASCII-Text (nur Windows 95)|  
|**TTN_NEEDTEXTW**|QuickInfo-Steuerelement erfordert Unicode-Text (nur Windows NT)|  
|**TBN_HOTITEMCHANGE**|Gibt an, dass die im laufenden Systembetrieb (markierte) Element geändert wurde.|  
|**NM_RCLICK**|Gibt an, dass der Benutzer eine Schaltfläche geklickt wurde.|  
|**TBN_DRAGOUT**|Gibt an, der Benutzer den Zeiger deaktiviert die Schaltfläche und auf die Schaltfläche geklickt hat. Er ermöglicht es einer Anwendung zum Implementieren von Drag und drop aus einer Symbolleisten-Schaltfläche. Beim Empfang dieser benachrichtigungs startet die Anwendung das Drag und drop-Vorgangs.|  
|**TBN_DROPDOWN**|Gibt an, der Benutzer geklickt hat eine Schaltfläche, verwendet der **TBSTYLE_DROPDOWN** Stil.|  
|**TBN_GETOBJECT**|Gibt an, der Benutzer den Zeiger verschoben, über eine Schaltfläche, verwendet der **TBSTYLE_DROPPABLE** Stil.|  
  
 Eine Beispiel-Handler-Funktion und Weitere Informationen zu QuickInfos finden Sie unter [QuickInfos](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CToolBarCtrl](../mfc/using-ctoolbarctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

