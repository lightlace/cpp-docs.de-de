---
title: "Behandeln von QuickInfo-Benachrichtigungen"
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
  - "CToolBarCtrl-Klasse, Handlingbenachrichtigungen"
  - "Benachrichtigungen, QuickInfos"
  - "QuickInfos [C++], Benachrichtigungen"
  - "TOOLTIPTEXT-Struktur"
ms.assetid: ddb93b5f-2e4f-4537-8053-3453c86e2bbb
caps.latest.revision: 12
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Behandeln von QuickInfo-Benachrichtigungen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie dem `TBSTYLE_TOOLTIPS` Format angeben, erstellt die Symbolleiste und verwaltet ein QuickInfo\-Steuerelement.  Eine QuickInfo ist ein kleines Popupfenster, das eine Textzeile enthält, die eine Symbolleisten\-Schaltfläche beschreibt.  Die QuickInfo ist ausgeblendet und wird nur angezeigt, wenn der Benutzer den Cursor auf eine Symbolleisten\-Schaltfläche platziert und ihn dort für ungefähr der Hälfte zweites können.  Die QuickInfo wird neben dem Cursor angezeigt.  
  
 Bevor die QuickInfo angezeigt wird, wird die **TTN\_NEEDTEXT** Benachrichtigung auf Besitzerfenster der Symbolleiste gesendet, um den beschreibenden Text für die Schaltfläche ab.  Wenn das Besitzerfenster der Symbolleiste ein Fenster `CFrameWnd` ist, werden QuickInfos ohne zusätzlichen Aufwand angezeigt, da `CFrameWnd` einen Standardhandler für die Benachrichtigung **TTN\_NEEDTEXT** hat.  Wenn das Besitzerfenster der Symbolleiste nicht von `CFrameWnd`, wie einem Dialogfeld oder einer Formularansicht abgeleitet wird, müssen Sie einen Eintrag der Meldungszuordnung des Besitzerfensters hinzufügen und einen Benachrichtigungshandler in der Meldungszuordnung bereitstellen.  Der Eintrag zur Meldungszuordnung des Besitzerfensters ist, wie folgt:  
  
 [!CODE [NVC_MFCControlLadenDialog#40](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCControlLadenDialog#40)]  
  
## Hinweise  
 `memberFxn`  
 Die Memberfunktion, aufgerufen werden, wenn Text für diese Schaltfläche benötigt wird.  
  
 Beachten Sie, dass die ID einer QuickInfo immer 0.  
  
 Neben **TTN\_NEEDTEXT** Benachrichtigung kann ein QuickInfo\-Steuerelement die folgenden Benachrichtigungen an einem ToolBar\-Steuerelement senden:  
  
|Benachrichtigung|Bedeutung|  
|----------------------|---------------|  
|**TTN\_NEEDTEXTA**|ToolTip\-Steuerelement erfordert ASCII\-Text \(nur Windows 95\)|  
|**TTN\_NEEDTEXTW**|ToolTip\-Steuerelement erfordert UNICODE\-Text \(nur Windows NT\)|  
|**TBN\_HOTITEMCHANGE**|Gibt an, dass das heiße \(markiert\) Element geändert wurde.|  
|**NM\_RCLICK**|Gibt dem Benutzer hat mit der rechten Maustaste geklickt auf eine Schaltfläche.|  
|**TBN\_DRAGOUT**|Gibt dem Benutzer hat auf die Schaltfläche geklickt und abgerufen den Zeiger von der Schaltfläche an.  Sie können eine Anwendung, Drag & Drop\-Datenbindung einer Symbolleisten\-Schaltfläche zu implementieren.  Wenn sie diese Benachrichtigung empfängt, wird die Anwendung den Drag & Drop\-Vorgang.|  
|**TBN\_DROPDOWN**|Gibt dem Benutzer geklickt hat auf eine Schaltfläche an, die das **TBSTYLE\_DROPDOWN** Format verwendet.|  
|**TBN\_GETOBJECT**|Gibt den verschob Benutzer den Zeiger über eine Schaltfläche an, die das **TBSTYLE\_DROPPABLE** Format verwendet.|  
  
 Ein Beispiel finden Handlerfunktion und weitere Informationen über das Einrichten von QuickInfos, [QuickInfo](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md).  
  
## Siehe auch  
 [Verwenden von CToolBarCtrl](../mfc/using-ctoolbarctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)