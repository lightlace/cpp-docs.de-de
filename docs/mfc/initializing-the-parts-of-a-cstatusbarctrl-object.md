---
title: "Initialisieren der Teile eines CStatusBarCtrl-Objekts | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CStatusBarCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStatusBarCtrl-Klasse, Deklarieren von Teilen von"
  - "CStatusBarCtrl-Klasse, Einfacher Modus"
  - "Symbole, Verwenden in Statusleiste"
  - "Einfache Statusleisten"
  - "Statusleisten, Deklarieren von Teilen von"
  - "Statusleisten, Symbole"
  - "Statusleisten, Einfacher Modus"
ms.assetid: 60e8f285-d2d8-424a-a6ea-2fc548370303
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Initialisieren der Teile eines CStatusBarCtrl-Objekts
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Standardmäßig zeigt eine Statusleiste Statusinformationen mit separaten Bereiche an.  Diese Bereiche \(auch als Teile bezeichnet\) können eine Textzeichenfolge, ein Symbol oder beides enthalten.  
  
 Verwenden Sie [SetParts](../Topic/CStatusBarCtrl::SetParts.md), um zu definieren, wieviele Teile und die Länge, die Statusleiste hat.  Nachdem Sie die Teile der Statusleiste erstellt haben, können Sie unter [SetText](../Topic/CStatusBarCtrl::SetText.md) und [SetIcon](../Topic/CStatusBarCtrl::SetIcon.md) aufruft den Text oder das Symbol für einen bestimmten Teil der Statusleiste festlegen.  Nachdem der Teil erfolgreich, wird das Steuerelement neu gezeichnet automatisch eingestellt.  
  
 Im folgenden Beispiel initialisiert ein vorhandenes `CStatusBarCtrl`\-Objekt \(`m_StatusBarCtrl`\) mit vier Bereiche und anschließend ein Symbol \(IDI\_ICON1\) und Text im zweiten Teil fest.  
  
 [!CODE [NVC_MFCControlLadenDialog#31](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCControlLadenDialog#31)]  
  
 Weitere Informationen zum Festlegen des Modus `CStatusBarCtrl` eines Objekts in einfachem, finden Sie unter [Festlegen des Modus CStatusBarCtrl\-Objekts eines](../mfc/setting-the-mode-of-a-cstatusbarctrl-object.md).  
  
## Siehe auch  
 [Verwenden von CStatusBarCtrl](../mfc/using-cstatusbarctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)