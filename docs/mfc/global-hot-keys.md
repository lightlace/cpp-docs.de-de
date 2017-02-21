---
title: "Globale Abk&#252;rzungstasten | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Zugriffstasten [C++], Abkürzungstasten"
  - "CHotKeyCtrl-Klasse, Globale Abkürzungstasten"
  - "Globale Abkürzungstasten"
  - "Tastenkombinationen [C++], Abkürzungstasten"
ms.assetid: e0b95d14-c571-4c9a-9cd1-e7fc1f0e278d
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Globale Abk&#252;rzungstasten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine globale Zugriffstaste ist einem bestimmten nonchild Fenster verknüpft.  Sie ermöglicht dem Benutzer, um das Fenster von Teilen des Systems zu aktivieren.  Eine globale Anwendung legt eine Zugriffstaste für ein bestimmtes Fenster fest, indem sie die [WM\_SETHOTKEY](http://msdn.microsoft.com/library/windows/desktop/ms646284) Meldung zu diesem Fenster gesendet werden.  Wenn `m_HotKeyCtrl` das [CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)\-Objekt ist und `pMainWnd` ein Zeiger auf das zu aktivierende ist Fenster, wenn die Zugriffstaste gedrückt wird, können Sie den folgenden Code verwenden, um die Zugriffstaste zuzuordnen, die im Steuerelement mit dem Fenster angegeben wurde, auf den durch `pMainWnd` gezeigt wurde.  
  
 [!CODE [NVC_MFCControlLadenDialog#18](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCControlLadenDialog#18)]  
  
 Sobald der Benutzer eine globale Zugriffstaste drückt, erhält das angegebene Fenster [WM\_SYSCOMMAND](http://msdn.microsoft.com/library/windows/desktop/ms646360) eine Meldung, die **SC\_HOTKEY** als der Befehlstyp angibt.  Diese Meldung können auch das Fenster, das sie erhält.  Da dieser Meldung keine Informationen zur genauen Schlüssel enthält, die gedrückt wurde, mithilfe dieser Methode lässt das Unterscheiden zwischen verschiedenen Abkürzungstasten, die möglicherweise dem gleichen Fenster angefügt werden.  Die Abkürzungstaste\-Steuerelement bleibt bis die Anwendung gültig, die **WM\_SETHOTKEY** Beendigungen gesendet.  
  
## Siehe auch  
 [Verwenden von CHotKeyCtrl](../mfc/using-chotkeyctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)